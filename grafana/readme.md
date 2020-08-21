部署
```sh
$ kubectl apply -f grafana-namespace.yaml
$ kubectl apply -f grafana-deploy.yaml
$ kubectl apply -f grafana-svc.yaml
```

查看状态

```sh
$ kubectl get pods -n grafana
NAME                       READY   STATUS              RESTARTS   AGE
grafana-7789685957-jffpn   0/1     ContainerCreating   0          4m22s

$ kubectl describe pod  grafana-7789685957-jffpn -n grafana
...
Events:
  Type    Reason     Age        From                   Message
  ----    ------     ----       ----                   -------
  Normal  Scheduled  <unknown>  default-scheduler      Successfully assigned kube-ops/grafana-7789685957-jffpn to worker2-node
  Normal  Pulling    4m36s      kubelet, worker2-node  Pulling image "grafana/grafana:laster"
```
pod 状态为 ContainerCreating 的原因为正在拉取镜像


```sh
# 查看映射端口
$ kubectl get svc -n kube-ops
NAME      TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
grafana   NodePort   10.102.236.77   <none>        3000:30669/TCP   2d17h
```

open url : http://localhost:30669 显示如下，账号为 admin 密码为 admin321

![grafana login](https://www.qikqiak.com/k8s-book/docs/images/grafana-login.png)

第一次登录成功后，显示如下
![grafana index](https://www.qikqiak.com/k8s-book/docs/images/grafana-index.png)


[Grafana的安装使用](https://www.qikqiak.com/k8s-book/docs/56.Grafana的安装使用.html)