fio --name=test --rw=randwrite --ioengine=libaio --iodepth=64 --bs=4k --direct=1 --numjobs=64 --runtime=60 --size=1g --group_reporting --directory=/mnt