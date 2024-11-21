查看 网络命名空间
ip netn
查看  网络信息
ip netns exec qdhcp-c03f56d1-c7c9-43d0-b700-c78f20ec2c53 ip addr
ip netns exec qdhcp-c03f56d1-c7c9-43d0-b700-c78f20ec2c53 bash 


ovs-vsctl list-ports br0
phy-br-ex


ovs-vsctl list interface vth1
ovs-vsctl list interface bond1


ovs-ofctl dump-ports br-ex


ovs-ofctl show br-ex

ovs-ofctl dump-flows br-ex

ovs-ofctl dump-flows br-e

ovs容器中执行
ip route show

ip route get 192.168.78.1


ovs-ofctl dump-ports-desc br-int


ovs-appctl fdb/show br-ex
