
ceph osd crush rule create-replicated nvme default  host nvme
ceph osd crush rule create-replicated hdd default  host hdd

ceph osd crush rule dump nvme

ceph osd pool create test-pool 2048 2048
rbd pool init test-pool
ceph osd pool application enable test-pool rbd
#ceph osd pool set ssd-pool crush_rule ssd_rule


# ���� 5 �� OSD ��pg_num����Ϊ 128
# 5 �� 10 �� OSD ��pg_num����Ϊ 512
# 10 �� 50 �� OSD ֮�佫pg_num����Ϊ 1024

ceph osd pool create volumes-nvme 2048 2048
ceph osd pool set volumes-nvme pg_autoscale_mode off
ceph osd pool set volumes-nvme crush_rule nvme
ceph osd pool application enable volumes-nvme rbd

# �����洢��
rbd create test-pool/test0 --size 40G --object-size 4M --image-feature layering --stripe-unit 4M --stripe-count 1
rbd create volumes-nvme/test0 --size 40G --object-size 4M --image-feature layering --stripe-unit 4M --stripe-count 1
rbd create fzyun-ebs/test0 --size 40G --object-size 4M --image-feature layering --stripe-unit 4M --stripe-count 1

rbd create volumes/test0 --size 40G --object-size 4M --image-feature layering --stripe-unit 4M --stripe-count 1


# ӳ���

rbd map volumes/test0
rbd map volumes-nvme/test0
rbd map fzyun-baas/test0
rbd map fzyun-ebs/test0
rbd map test-pool/test0

# �鿴����
rados -p volumes-nvme ls|grep test0|xargs -t -i ceph osd map volumes-nvme {}

#��������
nerdctl run --privileged -v $PWD:/pwd docker.fzyun.io/fzyun/sysbench fio --filename=/mnt/tmp.1 --output=fio1.log /libaio.fio


fio --name=test --rw=randwrite --ioengine=libaio --iodepth=64 --bs=4k --direct=1 --numjobs=64 --runtime=60 --size=10g --group_reporting --filename=/mnt/1