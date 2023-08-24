**中文** | [上游源代码](https://github.com/P3TERX/Actions-OpenWrt)

# Actions-OpenWrt(多设备固件云编译)

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/fichenx/OpenWrt/blob/main/LICENSE)
![GitHub Stars](https://img.shields.io/github/stars/fichenx/OpenWrt.svg?style=flat-square&label=Stars&logo=github)
![GitHub Forks](https://img.shields.io/github/forks/fichenx/OpenWrt.svg?style=flat-square&label=Forks&logo=github)
![GitHub download](https://img.shields.io/github/downloads/fichenx/OpenWrt/total.svg?style=flat-square&label=Download&logo=github)

## 项目说明 [![](https://img.shields.io/badge/-项目基本介绍-FFFFFF.svg)](#项目说明-)
- 固件来源：[![Lean](https://img.shields.io/badge/Lede-Lean-ff69b4.svg?style=flat&logo=appveyor)](https://github.com/coolsnowwolf/lede)[![immortalwrt](https://img.shields.io/badge/immortalwrt-immortalwrt-ff69b4.svg?style=flat&logo=appveyor)](https://github.com/immortalwrt/immortalwrt) [![P3TERX](https://img.shields.io/badge/OpenWrt-P3TERX-blueviolet.svg?style=flat&logo=appveyor)](https://github.com/P3TERX/Actions-OpenWrt) [![Flippy](https://img.shields.io/badge/Package-Flippy-orange.svg?style=flat&logo=appveyor)](https://github.com/unifreq/openwrt_packit)  [![breakings](https://img.shields.io/badge/OpenWrt-breakings-orange.svg?style=flat&logo=appveyor)](https://github.com/breakings/OpenWrt)[![fichenx](https://img.shields.io/badge/Build-fichenx-32C955.svg?style=flat&logo=appveyor)](https://github.com/fichenx/OpenWrt)
- 项目使用 Github Actions 拉取 [Lean](https://github.com/coolsnowwolf/lede) 和[immortalwrt](https://github.com/immortalwrt/immortalwrt) 的 Openwrt 源码仓库进行云编译
- 提供适配于NEWIFI D2、Redmi AX6、 ARMv8 电视盒子（斐讯N1、Tanix-TX3）的 OpenWrt 固件
- Redmi AX6固件分为 原厂分区版和合并分区版，合并分区版固件较大，使用前需对Redmi AX6进行合并分区。
- 固件集成的所有 ipk 插件全部打包在 Packages 文件中，可以在 [Releases](https://github.com/haiibo/OpenWrt/releases) 内进行下载
- 项目编译的固件插件为最新版本，最新版插件可能有 BUG，如果之前使用稳定则无需追新
- 第一次使用请采用全新安装，避免出现升级失败以及其他一些可能的 BUG

# 维护自用固件
## 1、NEWIFI D2
- 使用源码：https://github.com/coolsnowwolf/lede
- 内核：5.4
- 默认IP：192.168.124.1
- 用户名：root
- 密码：password

![newifi3](https://github.com/fichenx/OpenWrt/assets/86181542/a1768d5b-1646-4c6d-8e07-893943415dc5)

### 编译插件：
- 主题：Design
- 系统：磁盘管理、文件传输
- 服务：微信推送、openclash、SmartDNS、KMS服务器、Upnp、
- 网络存储：usb打印服务器、硬盘休眠、FTP服务器、网络共享
- VPN：N2N VPN、NPS内网穿透
- 网络：多线多拨、负载均衡、Turbo ACC 网络加速。

## 2、Redmi AX6
- 使用源码（lede原厂分区）：https://github.com/coolsnowwolf/lede
- 因无线驱动问题，暂时维持源码版本在20230501
- 内核（lede原厂分区）：5.10
- 使用源码（lede合并分区）：https://github.com/coolsnowwolf/lede
- 因无线驱动问题，暂时维持源码版本在20230501
- 内核（lede合并分区）：5.10
- 使用源码（immortalwrt合并分区）：https://github.com/immortalwrt/immortalwrt
- 内核（immortalwrt合并分区）：5.15
- 默认IP：192.168.123.1
- 用户名：root
- 密码：password
- 
![AX6](https://github.com/fichenx/OpenWrt/assets/86181542/a640d3d9-b935-40ca-9e16-3cc94bdc6a58)

### 编译插件：
- 主题：Argon、Design
- 系统：文件传输
- 服务：上网时间控制、SmartDNS、网络唤醒、Upnp、KMS服务器、微信推送、动态DNS、bypass（lede原厂分区、lede合并分区）、KoolProxyR plus+（lede合并分区）、 openclash（lede合并分区、immortalwrt合并分区）、Watchcat(lede合并分区、immortalwrt合并分区)、passwall（immortalwrt合并分区）、helloword（immortalwrt合并分区）
- VPN：N2N VPN、nps内网穿透（lede合并分区、immortalwrt合并分区）
- 网络：多线多拨、负载均衡(lede原厂分区、lede合并分区)、Turbo ACC 网络加速（lede原厂分区、lede合并分区）。


## 3、ARMV8
- 使用源码：https://github.com/coolsnowwolf/lede 
- 内核：5.4、5.10、5.15、6.1
- 默认IP：192.168.123.2
- 用户名：root
- 密码：password
![armv8](https://github.com/fichenx/OpenWrt/assets/86181542/a7ff319a-8875-4f58-a185-af6c1af979fc)

### 编译插件：
- 主题：Argon、Design
- 系统：Argon主题设置、文件传输、磁盘管理、晨晶宝盒
- 服务：PassWall、ikoolproxy、bypass、ShadowSocksR Plus+、上网时间控制、微信推送、openclash、动态DNS、SmartDNS、watchcat、网络唤醒、uhttpd、Upnp、KMS服务器、MWAN3 分流助手
- docker：DockerMan
- 网络存储：filebrowser、NFS管理、usb打印服务器、硬盘休眠、打印服务器、minidlna、网络共享、Aria2、MJPG-streamer、FTP服务器、MiniDLNA
- VPN：N2N VPN、IPsec VPN服务器、PPTP VPN服务器、Frps、Frp内网穿透、NPS内网穿透
- 网络：SQM Qos、socat、Turbo ACC 网络加速、u多线多拨、负载均衡。


---------------------------

## 感谢

- [OpenWrt](https://github.com/openwrt/openwrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
- [immortalwrt OpenWrt](https://github.com/immortalwrt/immortalwrt)
- [unifreq/openwrt_packit](https://github.com/unifreq/openwrt_packit)
- [P3TERX/Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)
- [ophub/flippy-openwrt-actions](https://github.com/ophub/flippy-openwrt-actions)
- [breakings/OpenWrt](https://github.com/breakings/OpenWrt)
- [ActionsRML/delete-workflow-runs](https://github.com/ActionsRML/delete-workflow-runs)
- [dev-drprasad/delete-older-releases](https://github.com/dev-drprasad/delete-older-releases)

## License

[MIT](https://github.com/fichenx/OpenWrt/blob/main/LICENSE) © [**尘事尘飞**]
