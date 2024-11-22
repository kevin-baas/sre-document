# Éú³É key
ceph auth get-or-create client.fzyun-ebs mon 'profile rbd' osd 'profile rbd pool=fzyun-ebs-g1,profile rbd pool=fzyun-ebs-g2,profile rbd pool=fzyun-ebs-g3' mgr 'profile rbd pool=fzyun-ebs-g1,profile rbd pool=fzyun-ebs-g2,profile rbd pool=fzyun-ebs-g3'
