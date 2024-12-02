# nr_requests 和 queue_depth
操作系统中nr_requests参数，可以提高系统的吞吐量，似乎越大越好，
但是该请求队列的也不能过大，因为这样会消耗大量的内存空间。该值的调整需要综合多处因素，
比如: 文件系统、sheduler类型、io的特点。
命令: echo xxx > /sys/block//queue/nr_requests，
nr_requests的大小设置至少是/sys/block//device/queue_depth的两倍，所以，修改nr_requtests的时候要注意

# 设置 nr_requests 是 512
cat /sys/block/sdb/queue/nr_requests
512