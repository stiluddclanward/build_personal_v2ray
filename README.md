# 搭建 V2ray 科学上网的简便教程，适用于多平台配置，仅需3分钟完成。

## v2ray个人搭建教程

也许您渴望深入学习技术资料，也许您想要自由畅游互联网世界，也许您期望保障您的在线请求的隐私与安全...

为了实现这一切，您需要一个代理工具，它能够帮助您突破网络封锁。市面上虽然有一些第三方代理工具，但它们并不总是安全和稳定的选择。因此，最佳方式是自行搭建一个完全属于您自己的代理工具。

V2ray 是一种相对稳定、安全、跨平台的代理工具，非常适合这个任务。

您可以轻松自己搭建它，过程也相当简单，下文将详细介绍。

在开始之前，您需要拥有一台位于国外的服务器，并在其中安装和配置好 V2ray。
## 如何购买性价比高的墙外服务器？

在搭建之前需要一台境外的云服务器，而 [vultr](https://www.vultr.com/?ref=9356007-8H) 服务商比较稳定，安全，相当于境内的阿里云。

值得说的一点是， [vultr](https://www.vultr.com/?ref=9356007-8H) 给新用户的福利相当给力，充值 10 美元就可以获取 100 美元，你可以点击 [vultr 专属赠送新用户 100 美元](https://www.vultr.com/?ref=9356007-8H) 进去抢先注册。

右上角有注册按钮，你也可以切换成中文界面：

<img width="1446" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119019442-be0cc500-b98c-11eb-895b-0d6300dce93d.png">

![](https://user-images.githubusercontent.com/84239400/119019760-0d52f580-b98d-11eb-9837-aba0990f1dfb.png)

接着使用邮箱和密码就可以注册了。

![](https://user-images.githubusercontent.com/84239400/119020042-4ee3a080-b98d-11eb-8341-bfc30f4b103c.png)

进去之后你可以看到这个页面，说明你已经通过 [vultr 专属优惠链接](https://www.vultr.com/?ref=9356007-8H) 获得了 100 美元赠送的资格：

![](https://user-images.githubusercontent.com/84239400/119020173-733f7d00-b98d-11eb-8ecc-a1afeb556fe6.png)

现在你只要选择支付宝充值 10 美元以上，就可以获得额外赠送的 100 美元。

![](https://user-images.githubusercontent.com/84239400/119020280-966a2c80-b98d-11eb-9113-8f5f0b75c5ea.png)

接下来就可以在这个平台选购云服务器了。

点击页面左边菜单栏的 「Products」进入服务器选购页面。

### Choose Server 选择服务器

选择 Cloud Compute 即可：

![](https://user-images.githubusercontent.com/84239400/119020373-af72dd80-b98d-11eb-8478-02d735b82709.png)

### Server Location

服务器的位置，可以选择美国地区，比如纽约：

![](https://user-images.githubusercontent.com/84239400/119020467-cadde880-b98d-11eb-8927-d3d837bbc20c.png)

### Server Type

服务器类型，Ubuntu 8 x64 系统：

<img width="1297" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/144575029-080f1a8c-4733-43d1-a000-c3d884f17378.png">

### Server Size

内存，选择最便宜的完全够用，而且性价比高，注意不要选择IPv6 ONLY的，要不然无法搭建使用。

<img width="1240" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/144575352-989d7239-99fb-4b81-a416-c50623ac25ff.png">

选择完了之后，下面的其它东西都不需要填，直接点击右下角 Deploy Now 就可以了：

![](https://user-images.githubusercontent.com/84239400/144575658-70cf1056-aff3-4972-a0f8-06f551157821.png)

这时候你就拥有了自己的一台云服务器了：

<img width="1261" alt="VPN搭建教程" src="https://user-images.githubusercontent.com/84239400/119021075-86068180-b98e-11eb-82a9-71edb9934f23.png">


点击 Cloud Instance ，可以看到你服务器的 IP 地址和密码：

<img width="1308" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119021183-a20a2300-b98e-11eb-8ff4-7f18d3e3bb80.png">


## 连接到你的服务器

### windows 系统连接到 vultr 服务器

windows 可以下载[PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)工具。

打开之后选择 session，将你在 vultr 网上得到的服务器 ip 复制过来，输入到这里：

![](https://user-images.githubusercontent.com/84239400/119023900-037fc100-b992-11eb-85ea-525a61a69657.png)

Port 默认 22，Connection Type 选择 SSH，接着点击 Open，连接进去之后输入你云服务器的密码。

### Linux 和 MacOS 连接到 vultr 服务器

Linux 和 MacOS 可以打开终端，使用如下命令连接：

```
ssh root@xx.xx.xxx.xx
```

`xx.xx.xxx.xx`就是你的服务器上的 IP 地址。

连接进去之后输入 yes 后按回车，接着输入你云服务器的密码，即可使用云服务器。

<img width="772" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119024049-32963280-b992-11eb-8c05-db6df1f7fbfa.png">

OK，现在你已经准备完毕，接下来开始搭建，很快就能搞定！

# 一键搭建v2ray命令

## 安装 curl 命令：

```
apt update
apt install curl
```

## 接着，执行一键脚本安装 v2ray：

```
bash <(curl -sL https://raw.githubusercontent.com/sucong426/build_personal_v2ray/main/v2ray.sh)
```

稍等安装完之后会显示 v2ray 的 ID 和端口号。

## 启动 v2ray

```
systemctl start v2ray
systemctl enable v2ray
```

很快，你的服务器的代理工具 v2ray 就运行起来了，你可以通过如下命令来查看你的 v2ray 配置信息：

```
vi /etc/v2ray/config.json 
```

# 用户使用 v2ray 实现科学上网

## Windows使用v2ray

点击[v2ray官方软件](https://github.com/v2fly/v2ray-core/releases)，选择 windows 的软件包，下载解压，执行 v2ray.exe，将服务器中的得到的 v2ray 端口和id 复制进去，就可以实现代理了。

## macOS使用v2ray

下载 [v2rayX](https://github.com/Cenmrev/V2RayX/releases)，执行后打开 Config：

![](https://user-images.githubusercontent.com/84239400/144606594-e26b0af9-d43b-4ca6-84a6-ee45ccad2e4f.png)

把你服务器的地址，v2ray的id和端口号，复制进去，加密方式选择 none：


<img width="535" alt="截屏2021-12-03 下午9 01 37" src="https://user-images.githubusercontent.com/84239400/144606911-388e94ae-65da-46a2-8ad1-0c2c07b670b3.png">

这样就可以实现代理了。

# 运行效果

使用油管看高清视频很顺滑，没有卡顿：
<img width="1628" alt="截屏2021-12-03 下午9 05 22" src="https://user-images.githubusercontent.com/84239400/144607388-062152f3-2030-41ae-8573-123ee267a29f.png">

google搜索速度快，秒出结果：


<img width="1001" alt="截屏2021-12-03 下午9 06 48" src="https://user-images.githubusercontent.com/84239400/144607509-22016fd1-a292-45bf-a5ef-ae87bee36650.png">
