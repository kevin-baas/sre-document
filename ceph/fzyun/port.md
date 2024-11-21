openstack port list -c id -c project_id --status DOWN --device-owner network:dhcp -c device_owner -c device_id -c fixed_ips
#设置端口ip
openstack port set --fixed-ip subnet=5e21af50-a5d8-4601-944e-44208134fbfe,ip-address=192.168.79.102 3a2ada9a-5b93-4681-b55f-22615b90e42f
#取消端口ip
openstack port unset --fixed-ip subnet=5e21af50-a5d8-4601-944e-44208134fbfe,ip-address=192.168.79.100 3a2ada9a-5b93-4681-b55f-22615b90e42f
