# SetSpeedTest

## 项目说明
主要用于对常规项目ip列表进行自动化维护的一个工具脚本集
--------------------------------------------------------------
项目: SetSpeedTest 自动更新 Hosts
版本: 1.0.0
原始项目说明：https://github.com/XIU2/CloudflareSpeedTest 主要用于对cf的ip列表进行维护的一个多平台脚本工具。

SetSpeedTest项目说明: 主要使用开源项目https://github.com/XIU2/CloudflareSpeedTest中的技术原理，对指定需要加速的域名访问地址进行查询获取当前网络环境下最快访问ip，然后用于修改host值，本脚本可以放在启动文件夹下，每次启动即可运行自动更改host访问ip增加访问效率。


使用本脚本前需要先内置需要测试域名的IP列表，ip.txt存放ipv4地址，ipv6.txt存放ipv6地址。
项目下已经内置常用访问需要加速的域名，该域名如果全部被墙则功能无效。
--------------------------------------------------------------

## 使用方式

本项目主要对常用网络项目的ip-list进行维护，如cf好人等等。

1、首先 `git clone  https://github.com/aspnmy/SetSpeedTest.git` 到本地
2、然后配置./conf/conf.json,配置要自动化部署的项目ip模型及脚本名。
3、运行根目录下的SetSpeedTest.sh,[win系统可以运行SetSpeedTest.bat]，就能对配置表中配置的ip模型进行自动优选部署。

## 进阶使用

多模型使用，如需对多个ip模型进行优化部署，请使用多模型脚本muilt_SetSpeedTest.sh，或者在自己系统上搭建计划任务，单独运行SetSpeedTest.sh脚本对应不同的ip模型。

## 配合DNS线路进行优化

进一步优化使用，可以配合运营商的DNS线路进行自动优化部署，首先你要有运营商DNS的访问key。可使用项目
https://github.com/aspnmy/SetDnsSpeedTest.git

### 配置参数说明
配置路径./conf/conf.json
```
    "colname": "windows",
    "ip_model": "Cloudflare",
    "ipv4": "true",
    "ipv6": "false"
```
colname:系统架构，可选参数有(win,linux,x86_64,x86)
ip_model:ip模型，可选参数有(Cloudflare,github,stream等)
ipv4：true或false，默认true
ipv6：true或false，默认false

### 目录结构
```
├─conf
└─dist
    ├─ip_model
    └─shell
```