# SkyFrp
于ZeroDream-CN/SakuraFrp二开 此项目基于 Frp 二次开发定制的版本，可实现多用户管理、限速等商业化功能
Sakura Frp 是一个基于 frp 的二次开发项目，在原版的基础上增加了限速、流控以及对接网站的功能，可实现商业化运营。
此项目为 [fatedier/frp](https://github.com/fatedier/frp) 衍生项目，如需了解原版 Frp，请前往官方仓库。
此软件需要配合 [SkyPanel] 面板使用。

## 安装
安装可选两种方式，下载 Release 页面上已经编译好的版本或者自行编译。

编译方法（编译过程需要科学上网）：

```bash
git clone https://github.com/sirvffg/SkyFrp.git
cd SakuraFrp/
make
```

## 配置

```bash
[common]
# Frp 绑定地址，默认 0.0.0.0 无需修改
bind_addr = 0.0.0.0

# Frp 运行端口
bind_port = 2333

# Kcp 模式运行端口，需要和上面的相同
kcp_bind_port = 2333

# 管理端口，默认 8233
dashboard_port = 8233

# 管理用户名，必须是 admin
dashboard_user = admin

# 管理密码，请确保和你在面板上设置的管理密码相同
dashboard_pwd = admin123456

# HTTP 映射端口
vhost_http_port = 80

# HTTPS 映射端口
vhost_https_port = 443

# Frp 服务器日志
# log_file = ./frps.log

# Frp Token 特权密码
# 请注意：此处的 token 是给 Frp 连接时进行鉴权用的，Frps 服务端请求面板 API 时使用的 TOKEN 在下方 api_token 处配置。
token = SakuraFrpToken

# UDP 穿透端口
bind_udp_port = 7001

# 以下项目无需修改
max_pool_count = 50
tcp_mux = true
authentication_timeout = 0
log_level = debug
log_max_days = 3

# 是否启用 Api 功能，默认 true
api_enable = true

# Api 服务器地址，格式为 http(s)://你的域名/api/
api_baseurl = http://example.com.com/api/

# Api 密码
# 此处的 API_TOKEN 需与面板的 /api/index.php 文件顶部设置的 API_TOKEN 相同，格式为：token|节点ID
# 节点 ID 在面板上添加的时候可以看到，添加节点 ID 是为了判断用户是否有权限使用对应节点
api_token = SakuraFrpToken|节点ID
```
