# 📕
------

### 1. 下载相关资源
* OpenClash安装包：  
  > https://github.com/vernesong/OpenClash/releases  
无特殊要求选最新稳定版即可，e.g：luci-app-openclash_X.XX.XXX-beta_all.ipk  

* mihomo内核：  
  > https://github.com/MetaCubeX/mihomo/releases  
无特殊要求选最新稳定版即可，e.g：mihomo-linux-armv7-vX.XX.XX.gz  

* OpenClash内核：  
  > https://github.com/vernesong/OpenClash/releases/tag/Clash  
无特殊要求选最新稳定版即可，e.g：clash-linux-armv7.tar.gz  

* 拷贝机场的Clash订阅链接：  
  > https://cordcloud.biz/user  
  订阅中心 -> GENERAL -> Clash -> 拷贝订阅链接  


### 2. 安装依赖
* SSH登录路由器后台：  
  > ssh root@192.168.8.1  

* 执行更新：  
  > opkg update  

* 安装依赖：  
  > opkg install luci luci-base iptables dnsmasq-full coreutils coreutils-nohup bash curl jsonfilter ca-certificates ipset ip-full iptables-mod-extra iptables-mod-tproxy kmod-tun kmod-inet-diag kmod-nft-tproxy luci-compat libcap libcap-bin ruby ruby-yaml unzip  

* 创建目录：  
  > mkdir -p /etc/openclash/core  

* 安装mihomo内核：  
  a) 解压下载的mihomo-linux-armv7-vX.XX.XX.gz文件，并将解压得到的二进制文件重命名为clash_meta  
  b) 通过SCP将clash_meta文件上传至路由器/etc/openclash/core目录下，并修改权限：
  > chmod 755 /etc/openclash/core/clash_meta  

* 安装OpenClash内核：  
  a) 解压下载的clash-linux-armv7.tar.gz文件，得到clash二进制文件  
  b) 通过SCP将clash文件上传至路由器/etc/openclash/core目录下，并修改权限：  
  > chmod 755 /etc/openclash/core/clash  


### 3. 安装OpenClash
* 登录路由器OpenWrt界面：  
  > http://192.168.8.1/cgi-bin/luci  

* 上传并安装OpenClash软件包：  
  系统 -> 软件包 -> 上传软件包
  选择OpenClash的IPK安装包并安装  


### 4. 配置OpenClash
* 进入OpenWrt::OpenClash主界面：  
  服务 -> OpenClash  

* 订阅链接导入原复制的Clash订阅链接即可  

* 覆写设置 -> 常规设置 里可配置链路自动检测切换  


------
