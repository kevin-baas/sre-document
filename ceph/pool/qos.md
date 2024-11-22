# qos

# 设置 fzyun-ebs-g1
rbd config pool set fzyun-ebs-g1 rbd_qos_read_iops_limit 200
rbd config pool set fzyun-ebs-g1 rbd_qos_read_bps_limit 209715200
rbd config pool set fzyun-ebs-g1 rbd_qos_write_iops_limit 200
rbd config pool set fzyun-ebs-g1 rbd_qos_write_bps_limit 209715200

# 设置 fzyun-ebs-g2
rbd config pool set fzyun-ebs-g2 rbd_qos_read_iops_limit 400
rbd config pool set fzyun-ebs-g2 rbd_qos_read_bps_limit 419430400
rbd config pool set fzyun-ebs-g2 rbd_qos_write_iops_limit 400
rbd config pool set fzyun-ebs-g2 rbd_qos_write_bps_limit 419430400

# 设置 fzyun-ebs-g3
rbd config pool set fzyun-ebs-g3 rbd_qos_read_iops_limit 800
rbd config pool set fzyun-ebs-g3 rbd_qos_read_bps_limit 838860800
rbd config pool set fzyun-ebs-g3 rbd_qos_write_iops_limit 800
rbd config pool set fzyun-ebs-g3 rbd_qos_write_bps_limit 838860800

# 查看参数
rbd config pool get fzyun-ebs-g3 rbd_qos_read_iops_limit


