etcdctl endpoint health --endpoints=https://127.0.0.1:2379 \ 
--cacert=/etc/ssl/etcd/ssl/ca.pem --cert=/etc/ssl/etcd/ssl/admin-ds3-master01.pem --key=/etc/ssl/etcd/ssl/admin-ds3-master01-key.pem

etcdctl member list --write-out=table --endpoints=https://127.0.0.1:2379 --cacert=/etc/ssl/etcd/ssl/ca.pem --cert=/etc/ssl/etcd/ssl/admin-ds3-master01.pem --key=/etc/ssl/etcd/ssl/admin-ds3-master01-key.pem


etcdctl member add etcd3 --peer-urls=https://10.4.1.19:2380 --write-out=table \
--endpoints=https://10.4.1.18:2380,https://10.4.1.17:2380 \
--cacert=/etc/ssl/etcd/ssl/ca.pem --cert=/etc/ssl/etcd/ssl/admin-ds3-master01.pem --key=/etc/ssl/etcd/ssl/admin-ds3-master01-key.pem


etcdctl member remove 896e7850b346d9f7 --peer-urls=https://10.4.1.19:2380 --write-out=table \
--endpoints=https://10.4.1.18:2380,https://10.4.1.17:2380 \
--cacert=/etc/ssl/etcd/ssl/ca.pem --cert=/etc/ssl/etcd/ssl/admin-ds3-master01.pem --key=/etc/ssl/etcd/ssl/admin-ds3-master01-key.pem



#环境变量
/etc/etcd.env

systemctl start etcd