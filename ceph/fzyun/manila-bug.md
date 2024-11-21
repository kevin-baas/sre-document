如果重新部署 deploy 主节点 ，manila会在 service 项目里 创建多个重复的网络： manila_service_network 
导致 manila-share 这个服务无法启动
后台报错：Ambiguous service networks
需要在 service 项目删除多余的manila_service_network