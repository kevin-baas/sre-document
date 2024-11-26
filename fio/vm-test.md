# 格式化
mkfs.ext4 /dev/sdb
# 创建目录
mkdir /mnt/test
# 挂载
mount /dev/sdb /mnt/test
# 多线程测试
fio --name=test --rw=randwrite --ioengine=libaio --iodepth=64 --bs=4k --direct=1 --numjobs=64 --runtime=60 --size=10g --group_reporting --directory=/mnt/test
