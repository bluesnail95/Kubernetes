(1)关闭防火墙

```
$systemctl disable firewalld
$systemctl stop firewalld
```

(2)安装etcd和Kubenetes

```
$yum install -y etcd kubernetes
```

遇到的错误：
![Kubernetes安装(1).jpg](img/Kubernetes安装/Kubernetes安装(1).jpg)

```
error: rpmdb: BDB0113 Thread/process 16864/140542777837376 failed: BDB1507 Thread died in Berkeley DB library
error: db5 error(-30973) from dbenv->failchk: BDB0087 DB_RUNRECOVERY: Fatal error, run database recovery
error: cannot open Packages index using db5 -  (-30973)
error: cannot open Packages database in /var/lib/rpm
CRITICAL:yum.main:

Error: rpmdb open failed

```
解决方案：
https://blog.csdn.net/liyinwang/article/details/70048346

(3)启动服务

```
$systemctl start etcd
$systemctl start docker
$systemctl start kube-apiserver
$systemctl start kube-controller-manager
$systemctl start kube-scheduler
$systemctl start kubelet
$systemctl start kube-proxy
```

![Kubernetes安装(1).jpg](img/Kubernetes安装/Kubernetes安装(2).jpg)


参考资料：
https://linux.cn/thread-14305-1-1.html

https://blog.csdn.net/zjcjava/article/details/81877632

https://blog.csdn.net/wiborgite/article/details/52858387

https://blog.csdn.net/hxpjava1/article/details/79323236


