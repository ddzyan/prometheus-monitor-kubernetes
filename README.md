# prometheus-monitor-kubernetes
如何使用prometheus来监控kubernetes集群

# 架构
![img](https://i.loli.net/2020/08/21/9odDtVin7pEwhjc.png)

# prometheus部署
请参考prometheus文件夹，根据README步骤apply

export 采用了 kube-state-metrics，他可以提供如下指标：
1. 调用了多少个 replicas, 现在可用的有几个？
2. 多少个Pod是running/stopped/terminated状态？
3. Pod重启次数
4. 有多少个job在运行中 

# prometheus-server部署
请参考prometheus-server文件夹，根据README步骤apply

# grafana 部署
请参考 grafana 文件夹，根据README步骤apply

# 参考文章
[Prometheus监控k8s(一)——监控框架调研](https://www.servicemesher.com/blog/prometheus-monitor-k8s-1/)

[Prometheus监控k8s(二)——监控部署](https://www.servicemesher.com/blog/prometheus-monitor-k8s-2/)

[Prometheus监控k8s(三)——业务指标采集](https://www.servicemesher.com/blog/prometheus-monitor-k8s-3/)


