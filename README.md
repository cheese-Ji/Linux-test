# Linux-test
Linux-text-projet安装
```
git clone https://github.com/linux-test-project/ltp.git
 ```
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/a48b9a1c-e3fb-4025-90a0-b5313868533b)

重置root用户密码，创建一个新密码后回车确认
```
cd ltp
sudo passwd root
```
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/d4d45e21-090f-4485-8e02-862e5b3c2408)

```
su
```

进入root
```
apt install gcc git make pkgconf autoconf automake bison flex m4 linux-headers-$(uname -r) libc6-dev
```
安装必须用到的编译工具pkgconf、autoconf、automake、bison、flex、m4

![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/8af21b79-329b-473b-ace6-2f74dada5c95)
```
make autotools
make install
```
编译

![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/314e65f8-2114-42b1-8562-8ec8c8a339cb)
```
./configure
```

配置文件，现在您可以继续编译并运行单个测试或编译并安装整个测试套件。
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/bf08e3b4-a7e1-48c8-be06-6b3d0f327dd1)

注意：ltp 的默认安装路径是/opt/ltp，所以接下来的执行测试步骤都需要在/opt/ltp目录下完成（这个一定要特别注意，我当时就误到这了，在/home/ltp目录下折腾半天总是测试报错,报错提示：
 FATAL: LTP not installed correctly
 
 INFO:  Follow directions in INSTALL!
 
## 执行LTP测试的方式主要有两种：

1.运行默认测试集（default set of tests）

 ```
 cd /opt/ltp
 ./runltp -p -l result.log
 ```
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/279c62cb-bebe-4535-9800-9551f53d6bee)

全部执行大概需要2-3小时，执行结果存放在/opt/ltp/results文件夹中，文件名为result.log

查看结果

```
cd /opt/ltp/results
vim result.log
```
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/0f65acc8-5bcc-4d2b-860a-5723897ca291)




