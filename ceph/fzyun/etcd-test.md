fio --rw=write --ioengine=sync --fdatasync=1 --directory=/mnt --size=22m --bs=2300 --name=mytest
fio --rw=write --ioengine=sync --fdatasync=1 --directory=/data/test --size=22m --bs=2300 --name=mytest

这个参数对顺序写有很大影响
rbd_op_threads
