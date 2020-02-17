# OpenWrt-CL
参照 P3TERX 和 KFERMercer 修改的自用 OpenWrt CI 文件。

# 特点
1、源码采用官方 OpenWrt 和Lean package 包的结合方式。

2、Merge-upstream.yml 用来自动由 openwrt 和Lean 的package 文件夹下载最新源码。

    A、默认是每天固定时间触发。
    
    B、默认由 https://github.com/openwrt/openwrt.git 更新源码。
    
    C、默认由 https://github.com/coolsnowwolf/lede/trunk/package/lean/ 抓取 package 文件夹。

3、OpenWrt-CI.yml 用来编译固件。
    A、默认是点击 “star” 触发编译。
    
    B、环境变量
       SSH_ACTIONS: true     --> 是否开启 SSH
       UPLOAD_BIN_IPK: true  --> 是否将IPK文件也打包上传
       UPLOAD_FIRMWARE: true --> 是否上传固件
       
    C、固件定制，请参照文件内说明   
 
# 使用说明
将文件放在项目的 .github/workflows 目录下即可。

https://github.com/yfdoor
