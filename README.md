# MinerProxy
Mining proxy/矿池代理，在本地或者vps服务器上安装矿池代理，集中管理矿机，可以统一钱包地址和矿机，集中反抽水（后续版本提供），支持TCP和SSL方式连接

<img width="700" height="540" src="https://github.com/MinerProxy/MinerProxy/blob/main/minerproxy.jpg?raw=true"/> 

MinerProxy 使用说明
=====================

MinerProxy保证绝不抽取您任何费用，请放心使用！！
MinerProxy接收您的主动捐赠，让软件越做越好，所有捐赠行为均取决您的选择！

##目前ETH,ERG等代理##
##支持开启多个进程，多个端口代理不同矿池和币种##

MinerProxy支持本地局域网安装，可集中管理您的矿机，做到一键更改矿池和钱包地址。
MinerProxy支持VPS安装，为您存放在不同地域不同钱包的矿机提供矿池代理服务。
MinerProxy技术上不仅仅是矿池代理，支持提交份额、本地和矿池算力统计，并提供
掉线提醒等功能等。您可以将MinerProxy用作一台您自己搭建的稳定矿池来使用，
更多功能请下载软件体验。

将压缩文件解压之后，运行MinerProxy.exe文件。
选择代理矿池，点击开始按钮，即开始进行矿池代理，矿机按照下面方式连接即可：
//注意将{host}改为运行代理的矿机IP地址或者主机名
//将{wallet}更改为您自己的钱包，{worker}更改为您自己的矿机名称
//比如我的IP地址为192.168.1.8，那么gm需要这样连接：
miner --algo ethash --server 192.168.1.8:3333 --user 0xabcxxxxxxxxxxx.myworker

GMiner连接
========
TCP端口方式：
miner --algo ethash --server {host}:3333 --user {wallet}.{worker}
SSL加密连接方式：
miner --algo ethash --server {host}:14333 --user {wallet}.{worker} --ssl

NBMiner连接
========
TCP端口方式：
nbminer -a ethash -o stratum+tcp://{host}:3333 -u wallet.worker -log
SSL加密连接方式：
nbminer -a ethash -o stratum+ssl://{host}:14333 -u wallet.worker -log

T-REX连接
=======
TCP端口方式：
t-rex.exe -a ethash -o stratum+tcp://{host}:3333 -u {wallet} -p x -w {worker}
SSL加密连接方式：
t-rex.exe -a ethash -o stratum+ssl://{host}:14333 -u {wallet} -p x -w {worker} --no-strict-ssl

各种挖矿软件，OS系统
==============
挖矿软件请在矿池管理添加一个矿池，矿池地址如下：
TCP方式： {host}:3333
SSL方式:    {host}:14333


更多帮助和建议，请移步github网站：
https://github.com/MinerProxy/MinerProxy

下载地址：
https://github.com/MinerProxyMinerProxy/releases

交流QQ群：583118085 （矿工反抽水联盟）
TG电表群：https://t.me/joinchat/_lOxUK1hNfdiMzY9


版本更新说明：
===============
V1.0.19 2021-10-16
  1. 修复矿池连接不派发工作导致矿机空转不掉线错误
  2. 增加并发线程数量(单机支持5000并发)
  3. 修复内存泄露问题，增加服务程序稳定性
  4. 修复掉线邮件通知在没有打开清理掉线矿机不发送问题
  5. 增加掉线HTTP GET接口
  6. 增加自定义窗口名称
  7. 增加矿机访问密码，并增加统一访问密码，杜绝非法访问
  8. 增加是否记录日志文件，是否显示日志（对于大量增加吞吐效率）
10. 增加矿池分时统计功能（10分钟，60分钟，6小时，24小时）
11.增加自动黑名单（非挖矿协议访问自动禁止IP 5分钟访问）
12.更多功能，请查看具体软件更改。

V1.0.18 2021-10-10
  1. 修复客户端有反水导致假掉线问题
  2. 修复内存有泄露问题，提高服务器稳定性
  3. 移除SSL2端口

V1.0.17 2021-10-08
  1. 修复连接客户端过多之后CPU占用过高的问题，目前CPU几乎不占用

V1.0.14 2021-10-08
  1. 紧急修复连接服务器超时错误之后，系统会崩溃重启

V1.0.12 2021-10-05
  1. 增加掉线邮件提醒功能
  2. 矿机列表增加掉线时长提示
  3. 增加托管服务设置（功能暂未完成，等后续版本）
  4. 增加程序崩溃应急自启动功能，保证稳定运行
  5. 日志存放修改到logs目录，按每天一个文件方式
  6. 注意本次更新会覆盖邮件设置，请重新设置，后续更新将不会再出现

V1.0.10 2021-10-04
1. 发布第一个稳定版本
2. 详细功能，请参考软件
