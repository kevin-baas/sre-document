#���� replicated rule
ceph osd crush rule create-replicated hdd_rule default  host hdd
#�鿴 rule
ceph osd crush rule list
#�鿴 hdd_rule
ceph osd crush rule dump hdd_rule