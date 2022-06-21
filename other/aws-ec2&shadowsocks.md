# 亚马逊 AWS-EC2 搭建 Shadowsocks  服务记录

* 在公司网络环境是可以翻墙的，不需要自己搭建。但因为最近一段时间疫情影响不得不居家办公，又基于国内文章质量产生诸多不便，所以根据 aws ec2 和 shadowsocks 手动搭建环境。

## 关键词简介

* AWS（Amazon Web Services）：是亚马逊（Amazon）公司旗下的全球最全面、应用最广泛的云平台。类似国内的阿里云、腾讯云、华为云...

* EC2（Elastic Compute Cloud）：亚马逊弹性计算云，是一个让使用者可以租用云端电脑运行所需应用的系统。EC2借由提供Web服务的方式让使用者可以弹性地运行自己的Amazon机器映像档，使用者将可以在这个虚拟机器上运行任何自己想要的软件或应用程序。

* SS（Shadowsocks）：是一种基于Socks5代理方式的加密传输协议，也可以指实现这个协议的各种开发包。为了避免关键词过滤，网民会根据谐音将 ShadowsocksR 称为 "酸酸乳"（SSR），将 Shadowsocks 称为 "酸酸"（SS）。另外，因为 Shadowsocks(R) 的标志均为纸飞机，所以专门提供 Shadowsocks(R) 或类似服务（如V2Ray）的网站则就被称为了 "机场"。

## 1. 环境准备

### 1.1 AWS-EC2

* 个人邮箱。

* 需要能够完成美元支付的信用卡（注册需要支付 1 美元费用，一年期满后没有超限使用是会退还），一般标有 visa 或者 mastercard 标的都可以（包括双标信用卡），银联信用卡虽然可以绑定，但是不能支付。我使用的是 visa 卡。

#### 创建账号

* 注册：进入 [aws官网](https://aws.amazon.com/cn/) 右上角黄色 "注册按钮" 填写个人信息完成注册。

* 登陆：注册完成后点击登陆按钮进行登陆。![image](https://user-images.githubusercontent.com/69457959/174732844-8ddafb2d-1ff7-4b8c-a6df-8f85ee29b3a3.png)


#### 创建实例

* 选择地区：创建实例时候根据需求选择对应地区（没有特殊需求的就选亚太地区）。![1655793558710](https://user-images.githubusercontent.com/69457959/174733231-62f26ce9-ce26-4072-ba6b-f4505fcf1c40.png)

* 创建实例：启动实例时选择操作系统映像可以选自己熟悉的操作系统，有些镜像是需要收费的推荐选择 Ubuntu、Debian。![image](https://user-images.githubusercontent.com/69457959/174733658-2dda3ecb-77e5-493e-b195-303ec4cd69a6.png)![image](https://user-images.githubusercontent.com/69457959/174733792-d0084992-c927-4222-ad37-a34196a850a0.png)

* 实例配置：密钥对需要下载到本地之后使用 putty 连接时会使用。![image](https://user-images.githubusercontent.com/69457959/174734739-a6d30f9e-fdb3-42e6-86c0-7dfcee2c8f03.png)![image](https://user-images.githubusercontent.com/69457959/174734968-97c5198f-535a-4c22-86d5-3b098fa3b594.png)![image](https://user-images.githubusercontent.com/69457959/174735079-2e44c488-8bb5-4c61-a164-f0dac739c28a.png)

### 1.2 Putty

* putty：Putty是一个免费的、Windows x86平台下的Telnet、SSH和rlogin客户端，但是功能丝毫不逊色于商业的Telnet类工具。

* 根据自己的操作系统[下载](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)并安装。

## 服务搭建（基于Ubuntu18）

* putty 连接：因为 putty 仅支持 .ppk 为后缀的密钥对，如果密钥对是 .pem 格式需要先使用 puttygen.exe 将密钥转为 .ppk 格式。（在加载 .pem 时候文件名后缀选择为所有）![image](https://user-images.githubusercontent.com/69457959/174736478-9de55c53-e50b-4448-a665-a2c7999f73ee.png)![image](https://user-images.githubusercontent.com/69457959/174736860-f720a67b-3ab4-4452-90e0-3134a8840882.png)![image](https://user-images.githubusercontent.com/69457959/174737285-5a495192-09d4-4e2e-ac25-dfcff833e96e.png)

* 创建Shadowsocks服务端：

## Windows&Android 连接测试
