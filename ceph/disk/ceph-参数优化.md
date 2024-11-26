# 修改下面的参数
rbd_cache_writethrough_until_flush=false
rbd_op_threads=2
osd_mclock_profile=high_client_ops

# 系统参数
fs.aio-max-nr=1048576

# 磁盘参数 设置 nr_requests 是 512
nr_requests 512




