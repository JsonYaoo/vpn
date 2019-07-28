
如果你想要查询一些权威的资料，上 Google 搜索有用的内容，超流畅 1080p 高清观看Youtube，畅游全网，而且完全拥有自己的服务器，那么本文将从购买vultr vps，到搭建属于你自己的 ss(Shadowrocks) 服务器，并且开启 BBR 加速上网，10分钟几个步骤轻松搞定。

首先我们需要购买一台境外的服务器，接着我们在这台云服务器里面安装代理服务，那么以后我们上网的时候就可以通过它来中转，轻松畅快的畅游全网了。

# 优惠购买vultr

在使用了[一些服务器之后](https://wistbean.github.io/cloud-server.html)，我觉得 [vultr](https://www.vultr.com/?ref=7772384-4F) 的性价比超高，最低 $2.5/月 ，就可以拥有一台 1TB 月流量的服务器了，根本用不完。


而且现在 [vultr](https://www.vultr.com/?ref=7772384-4F) 优惠力度很大，**充值 10 美元送 50 美元**。

## 注册vultr

点击 [vultr官网送 50 美元优惠](https://www.vultr.com/?ref=7772384-4F) 进行注册：

![注册vultr](https://wistbean.github.io/images/vultr-register.png)

在这里输入你的邮箱和密码，接着点击按钮「Create Account」创建账号，然后 vultr 会给你的注册邮箱发送一份验证邮件，激活就好了。

接着就可以登录 vultr 官网了：

![登录vultr](https://wistbean.github.io/images/vultr-login.png)



## vultr 购买流程

vultr 现在有 16 个境外节点，选择一个离你最近的就好了。

![登录vultr](https://wistbean.github.io/images/vultr-location.png)
![购买vultr](https://wistbean.github.io/images/vultr-buy.gif)

登录进去之后选择左边的 billing 的菜单进行充值，vultr提供的支付方式简直完美，支持信用卡，比特币，paypal，支付宝，微信支付，在这里可以进行充值支付。

![vultr充值](https://wistbean.github.io/images/vultr00.png)

充值完成之后，就可以左侧的 Sevrers 菜单，接着可以点击 `deploy one` 或者右侧的 + 号来选购你要的服务器：

![vultr充值](https://wistbean.github.io/images/vultr01.png)

### 选择服务器的机房位置，一般来说离你越近越好，速度会快那么一丢丢：

![vultr服务器位置](https://wistbean.github.io/images/vultr02.png)

### 选择服务器的系统类型，选择 CentOS 版本：

![vultr系统类型](https://wistbean.github.io/images/vultr03.png)

### 选择服务器的价格和具体配置，自己用的话选最低的就够用了：

![vultr配置](https://wistbean.github.io/images/vultr04.png)

### 确认购买

其它步骤可以忽略，然后点击右下角的 Deploy Now：

![vultr](https://wistbean.github.io/images/vultr05.png)

### 拥有一台服务器

点击之后你就拥有一台属于你自己的服务器了：

![vultr](https://wistbean.github.io/images/vultr06.png)

点击你的服务器，进去之后你就可以看到你的服务器的ip地址和账号密码了：

![vultr](https://wistbean.github.io/images/vultr07.png)


以上信息等会用来从你的电脑连接到你的服务器上。

# 使用vultr搭建ss服务器

## 下载Linux连接工具

需要在你的电脑连接到你的服务器，那么就需要连接工具，连接工具有很多个，根据你的需要，以下随意下载一个连接工具即可：

- [PUTTY Windows版本下载](https://www.ssh.com/a/putty-0.70-installer.msi)
- [PUTTY MAC版本下载](https://www.ssh.com/ssh/putty/mac/)
- [SecureCRT](https://pan.baidu.com/s/11W4WHjCjmiNw6einQNrcPg) ,提取码：tyux

接着打开连接工具，然后输入你刚刚购买的服务器 ip 地址，账户名，和密码就可以连接了。接下来就可以操作你的服务器了。

![服务器CentOS系统](https://wistbean.github.io/images/linux-panel.png)

## 开始搭建ss

连接到你的 vultr 服务器之后，接下来就可以使用几个命令让你快速搭建一个属于自己的 ss 服务器：

### 输入以下命令，然后回车：
     yum install wget
### 接着执行安装shadowsocks：
    wget –no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
### 获取 shadowsocks.sh 读取权限：
    chmod +x shadowsocks.sh
### 设置你的 ss 密码和端口号：

输入`./shadowsocks.sh 2>&1 | tee shadowsocks.log`后就可以设置密码和端口号了：

![设置密码](https://wistbean.github.io/images/ss1.png)
### 选择加密方式
设置完密码和端口号之后，我们选择加密方式，这里选择 7 ，使用`aes-256-cfb`的加密模式：
![vultr ss服务器](https://wistbean.github.io/images/ss2.png)
接着按任意键进行安装。
### 安装ss完成
等一会之后，就安装完成了，它会给你显示你需要连接 vpn 的信息：
![vultr ss服务器](https://wistbean.github.io/images/ss3.png)
可以看到需要连接 ss 的 ip地址，密码，端口，和加密方式。

搞定，将这些信息保存起来，那么这时候你就可以使用它们来科学上网啦。


# 开始使用vultr的ss

## windows使用Shadowsocks

windows点击下载：[Shadowsocks windows客户端](https://pan.baidu.com/s/19m0AfTkPDSRj0bfYrGpbIg)

打开 Shadowsocks 客户端，输入ip地址，密码，端口，和加密方式。接着点击确定，**右下角会有个小飞机按钮，右键-->启动代理**。

![vultr的ss](https://wistbean.github.io/images/ss4.png)

这时候就可以科学上网了。

![google](https://wistbean.github.io/images/vpn18.png)

## Android使用Shadowsocks

Android点击下载：[Shadowsocks Android客户端](https://pan.baidu.com/s/1coAkZn-GuYHu5eIKaHECxA)

打开apk安装，接着打开APP，输入ip地址，密码，端口，和加密方式。即可科学上网。

## iPhone使用Shadowsocks

iPhone要下载的app需要在appstore下载，但是需要用美区账号才能下载，而且这个APP需要钱。在这里提供一种解决方案，就是可以再搭建一个[IPsec/L2TP VPN](https://wistbean.github.io/ipsec,l2tp_vpn.html#%E4%BD%BF%E7%94%A8-IPsec-L2TP-%E8%84%9A%E6%9C%AC%E6%90%AD%E5%BB%BA),专门给你的iPhone使用。
使用 IPsec/L2TP 脚本搭建
安装 wget ：
yum install wget
使用脚本：
wget https://git.io/vpnsetup-centos -O vpnsetup.sh && sudo sh vpnsetup.sh
稍等一会安装成功会提供一个 VPN 需要的信息：
Server IP: xxx.xx.xx.xx
IPsec PSK: xxxx
Username: xxxx
Password: xxxx
这时候就搭建成功了，快吧？
接着就可以上外网了：

![google](https://wistbean.github.io/images/pic8.png)

不过速度并不是快到飞起来，所以接下来就可以使用 BBR 加速了。也很简单，几个命令就搞定了。

# vultr使用BBR加速上网


## 安装 BBR

    wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh

## 获取读写权限

    chmod +x bbr.sh

## 启动BBR安装

    ./bbr.sh

接着按任意键，开始安装，坐等一会。安装完成一会之后它会提示我们是否重新启动vps，我们输入 y 确定重启服务器。

重新启动之后，输入 `lsmod | grep bbr` 如果看到 tcp_bbr 就说明 BBR 已经启动了。

再访问一下 Youtube，1080p 超高清，秒开，很顺畅不卡顿，超爽！

![youtube](https://wistbean.github.io/images/ss7.png)

---

# 相关

- [搬瓦工快速手动搭建SS(Shadowsocks)服务器简明详细教程](https://wistbean.github.io/banwagong-ss.html)
- [我用了十几台云服务器VPS后，告诉你哪家云服务产商性价比高,性能稳定](https://wistbean.github.io/cloud-server.html)


