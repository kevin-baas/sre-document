#创建 replicated rule
ceph osd crush rule create-replicated hdd_rule default  host hdd
#查看 rule
ceph osd crush rule list
#查看 hdd_rule
ceph osd crush rule dump hdd_rule