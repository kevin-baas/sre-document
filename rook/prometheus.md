查看监控地址
kubectl get svc -n poseidon

curl http://10.233.53.34:9283/metrics | grep -v '#' | head
curl http://10.233.53.34:9283/metrics |more

# 添加任务
- job_name: 'ceph'
  honor_labels: true
  static_configs:
    - targets:
        - 192.168.61.21:9283
          labels:
          instance: ceph

- job_name: 'ceph_cluster'
  honor_labels: true
  scrape_interval: 5s
  static_configs:
    - targets: ['192.168.1.5:9283']
      labels:
      instance: ceph