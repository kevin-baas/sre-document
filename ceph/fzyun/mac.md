fa:16:3e:ae:7e:4c

查看mac地址

ovs-ofctl dump-ports-desc br-int|grep c6948584


设置mac地址：
ovs-vsctl set interface vi0 mac=\"mac地址\"
ovs-vsctl set interface tapd6a51068-f4 mac=\"fa:16:3e:80:70:cb\"

fa:16:3e:48:de:07	