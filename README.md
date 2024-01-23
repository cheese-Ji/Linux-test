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

全部执行大概需要2-3小时，执行结果存放在/opt/ltp/results文件夹中，文件名为result.log（此时运行的runltp会生成指定的测试列表并调用测试驱动
Pan来测试，最后对每个测试用例的执行结果进行统计，整体测试结果返回给runltp）

查看结果

```
cd /opt/ltp/results
vim result.log
```
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/0f65acc8-5bcc-4d2b-860a-5723897ca291)

2.运行一部分testcase
```
 cd /opt/ltp/runtest
 vim your_command_file(your_command_file是自定义文件名）
```
如运行以下四个用例，命令文件由两部分组成，一是test case标签“tag",另一个是你希望执行的具体的"test case"脚本名以及一些参数：

![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/8b2018b8-3938-41f2-b4ad-501141052b43)

运行用例，保存到result.02.log中

```
./runltp -p -l result.02.log -f your_command_file
```
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/3bb0abd2-923d-4404-b9bf-d5fd46f2f31a)

运行结果如下：

![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/2e343974-dd28-414f-89f8-a30af3f3ca84)

## 测试结果输出类型：
1.BROK :测试执行中途发生错误而使测试遭到破坏
2.CONF :测试环境不满足而跳过执行
3.WARN :测试中途发生异常
4.INFO :输出通用测试信息
5.PASS :成功
6.FAIL :失败

 查看自己Linux内核版本：
 ```
cat /proc/version
```

![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/58c701ba-c8e7-4e51-bfa9-3b11da06228b)

