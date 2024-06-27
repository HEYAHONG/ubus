# 说明

本分支主要为一些在非openwrt系统上使用ubus提供一些说明,主要用于开发环境(如ubuntu)。

注意：为模拟openwrt上的运行环境，ubusd将运行于root账户，且操作ubus需要root权限。

# 编译

## 库依赖

- libjson-c:操作json
- lua:用于lua语言的相关模块。
- libubox:Openwrt的C语言工具库。

## 步骤

- 创建目录(`mkdir build`)并进入目录(`cd build`)。
- 采用CMake创建工程文件(`cmake ../`)。
- 构建(`cmake --build .`)
- 安装到系统(`sudo cmake --build . -t install`)

# 安装

默认情况下，ubusd不会自动启动,可将ubus设置为自动启动方便调试。

对于采用systemd作为init的系统，可进行如下操作：

- 使能ubus:`sudo systemctl enable ubus`
- 启动ubus:`sudo systemctl start ubus`
- 停止ubus:`sudo systemctl stop ubus`
- 重启ubus:`sudo systemctl restart ubus`
