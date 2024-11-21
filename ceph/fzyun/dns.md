#查看错误
systemctl list-units|grep kolla
systemctl list-units|grep designate
systemctl status kolla-designate_backend_bind9-container.service


#查看dns状态
resolvectl status
#列出 openstack 网络
openstack network list
#查看 openstack 网络
openstack network show 
