>  如果不想通过SSH推送，在config文件里面，将origin配置地址改成https://...

### SSh设置

将config的路径配置成ssh的路径

![image-20231212175959151](SSH设置.assets/image-20231212175959151.png)

### 然后去生成安全证书

>  ssh-keygen -t rsa -Cgit@github.com:fanshuaiyao/remote_test.git

![image-20231212180323115](SSH设置.assets/image-20231212180323115.png)

### 生成的密钥在这里，复制密钥

![image-20231212180459895](SSH设置.assets/image-20231212180459895.png)

### 在github中设置密钥

![image-20231212180618186](SSH设置.assets/image-20231212180618186.png)

这样就可以使用ssh来push了

![image-20231212181039009](SSH设置.assets/image-20231212181039009.png)

