# ��ʽ��
mkfs.ext4 /dev/sdb
# ����Ŀ¼
mkdir /mnt/test
# ����
mount /dev/sdb /mnt/test
# ���̲߳���
fio --name=test --rw=randwrite --ioengine=libaio --iodepth=64 --bs=4k --direct=1 --numjobs=64 --runtime=60 --size=10g --group_reporting --directory=/mnt/test
