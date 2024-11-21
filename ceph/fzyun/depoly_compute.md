# 如果没有在删除主机的情况下，重装kolla节点
#查看原来的compute的id
cat /var/lib/docker/volumes/nova_compute/_data/compute_id
#查看计算节点的UUID
echo "7468878b-5cfb-4ed3-87ae-d531dbdb2fcc" > /var/lib/docker/volumes/nova_compute/_data/compute_id