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
