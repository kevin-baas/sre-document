rbd bench --io-type write --io-size 4096 --io-threads 1 fzyun-baas/csi-vol-26bbee59-0d39-11ef-b24d-9a74671362c9
rbd config image set fzyun-baas/csi-vol-26bbee59-0d39-11ef-b24d-9a74671362c9 rbd_qos_iops_limit 5
rbd config pool set fzyun-baas rbd_qos_iops_limit
rbd config pool set rbd_qos_write_iops 1000
rbd config pool set rbd_qos_read_iops 1000

rbd config pool set fzyun-baas-stage rbd_qos_iops_limit 2000

rbd config pool set fzyun-baas rbd_qos_iops_limit 2000

