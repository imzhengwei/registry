## registry
---
### Pull the image from registry.k8s.io and push it to Alibaba Cloud image repository.

#### 1.在github中创建Dockerfile文件，以etcd为例。
```dockerfile
FROM registry.k8s.io/etcd:3.5.6-0

LABEL top.housheng.maintainer="zhengwei"
```

#### 2.在阿里云中的容器镜像服务中创建etcd的仓库名称，仓库类型可选公开或者私有，点击下一步。
![1](https://github.com/houshengtop/cuddly-giggle/blob/main/registryk8sio/1.png)

#### 3.在创建镜像仓库页面中选择代码源为Github，命名空间为自己在github中创建的项目，仓库中选择创建的仓库名，构建设置选择海外机器构建和不使用缓存，配置完毕后选择创建镜像仓库。
![2](https://github.com/houshengtop/cuddly-giggle/blob/main/registryk8sio/2.png)


#### 4.在创建好的镜像仓库中选择构建，然后再选择添加规则，在打开的创建规则中选择类型、分支、构建上下文目录、Dockerfile文件名和镜像版本，其中Dockerfile文件名要以github中的名字为准，版本就填写Dockerfile文件里填写的版本，填写完毕后点击确定。
![3](https://github.com/houshengtop/cuddly-giggle/blob/main/registryk8sio/3.png)

#### 5.镜像构建，点击立即构建即可在registry.k8s.io仓库中拉取镜像，当构建状态显示成功，就表示镜像拉取成功到了阿里云镜像仓库中。
![4](https://github.com/houshengtop/cuddly-giggle/blob/main/registryk8sio/4.png)
