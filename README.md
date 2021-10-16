# hrzimage
this repo is for storage images that i can not download
# how to use
1. 在仓库创建一个目录，目录中新建一个Dokckfile文件
2. Dockerfile文件中 写入以下两行
```dockerfile
FROM 你的镜像地址:版本标签#k8s.gcr.io/kube-apiserver:v1.17.3
MAINTAINER hrz 972199518@qq.com
```
3. 阿里云镜像
 > https://cr.console.aliyun.com/cn-shenzhen/instance/dashboard
理论上一个镜像就要执行上面一次

# reference
https://mp.weixin.qq.com/s/kf0SrktAze3bT7LcIveDYw


---
> https://cr.console.aliyun.com/repository/cn-hangzhou/hrz-images

1. 登录阿里云Docker Registry
$ docker login --username=黄荣拯 registry.cn-hangzhou.aliyuncs.com
用于登录的用户名为阿里云账号全名，密码为开通服务时设置的密码。

您可以在访问凭证页面修改凭证密码。

2. 从Registry中拉取镜像
$ docker pull registry.cn-hangzhou.aliyuncs.com/hrz-images/kueb-apiserver:[镜像版本号]
3. 将镜像推送到Registry
$ docker login --username=黄荣拯 registry.cn-hangzhou.aliyuncs.com
$ docker tag [ImageId] registry.cn-hangzhou.aliyuncs.com/hrz-images/kueb-apiserver:[镜像版本号]
$ docker push registry.cn-hangzhou.aliyuncs.com/hrz-images/kueb-apiserver:[镜像版本号]
请根据实际镜像信息替换示例中的[ImageId]和[镜像版本号]参数。

4. 选择合适的镜像仓库地址
从ECS推送镜像时，可以选择使用镜像仓库内网地址。推送速度将得到提升并且将不会损耗您的公网流量。

如果您使用的机器位于VPC网络，请使用 registry-vpc.cn-hangzhou.aliyuncs.com 作为Registry的域名登录。

5. 示例
使用"docker tag"命令重命名镜像，并将它通过专有网络地址推送至Registry。

$ docker images
REPOSITORY                                                         TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
registry.aliyuncs.com/acs/agent                                    0.7-dfb6816         37bb9c63c8b2        7 days ago          37.89 MB
$ docker tag 37bb9c63c8b2 registry-vpc.cn-hangzhou.aliyuncs.com/acs/agent:0.7-dfb6816
使用 "docker push" 命令将该镜像推送至远程。

$ docker push registry-vpc.cn-hangzhou.aliyuncs.com/acs/agent:0.7-dfb6816
