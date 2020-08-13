# alpine-sshd

Alpine-sshd  

默认密码：root:root  

```
docker run -d -p 10022:22 --name alpine-sshd peng4740/alpine-sshd
```

自定义密码为：root:123456  
-e PWD=123456  

```
docker run -d -e PWD=123456 -p 10022:22 --name alpine-sshd peng4740/alpine-sshd
```