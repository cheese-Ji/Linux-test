# Linux-test

git clone https://github.com/linux-test-project/ltp.git
   

#Linux-text-projet安装
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/a48b9a1c-e3fb-4025-90a0-b5313868533b)

cd ltp


sudo passwd root
#重置root用户密码，创建一个新密码后回车确认
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/d4d45e21-090f-4485-8e02-862e5b3c2408)

su
#进入root

apt install gcc git make pkgconf autoconf automake bison flex m4 linux-headers-$(uname -r) libc6-dev
#安装必须用到的编译工具
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/8af21b79-329b-473b-ace6-2f74dada5c95)

make autotools
#编译
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/314e65f8-2114-42b1-8562-8ec8c8a339cb)

./configure
#配置文件，现在您可以继续编译并运行单个测试或编译并安装整个测试套件。
![image](https://github.com/cheese-Ji/Linux-test/assets/155931600/bf08e3b4-a7e1-48c8-be06-6b3d0f327dd1)



