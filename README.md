# OpenWrt-CL
- 参照 P3TERX 和 KFERMercer 修改的自用 OpenWrt CI 文件。

## 特点
- 可以采用官方 OpenWrt 和Lean package 包的结合方式。

- OpenWrt-C-CI.yml: 无需 fork 源码，直接使用该文件就可以执行编译。
  - 默认是点击 “star” 触发编译。
  - 环境变量
  ```
    - REPO_URL: https://github.com/openwrt/openwrt.git      --> 源码选择
    - SSH_ACTIONS: false                                    --> 是否开启SSH
    - UPLOAD_BIN_IPK: false                                 --> 是否上传IPK
    - UPLOAD_FIRMWARE: true                                 --> 是否上传固件
    - PACKAGE_INCLUDE: false                                --> 是否包含Lean's package
  ```
   - 固件定制，请参照文件内说明
  
- OpenWrt-P-CI.yml: 需要 fork 源码到自己的仓库。
- Merge-upstream.yml：搭配 ***OpenWrt-P-CI.yml*** 使用，用来自动由 openwrt 和Lean 的package 文件夹下载最新源码。
  - 默认是每天固定时间触发。
  - 默认由 https://github.com/openwrt/openwrt.git 更新源码。
  - 默认由 https://github.com/coolsnowwolf/lede/trunk/package/lean/ 抓取 package 文件夹。
 
## 使用说明
 - 将相应文件放在项目的 .github/workflows 目录下即可。
