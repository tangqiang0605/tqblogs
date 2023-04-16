1. 抓包工具
2. 只能查看包，不能修改、发送包。
3. 支持协议 http、tcp、udp。

1. 包
2. 详情
3. 源代码

菜单
1. 帮助、说明文档
2. 捕获，一般不用。使用显示过滤器。

捕获过滤表达式
协议
方向：默认 "src or dst"
host：默认 host

多个表达式使用 not、and、or 等连接。

host 192.168.5.231 and port 80 and http

not port 80 and !http

host 192.168.5.231

dst 192.168.5.231

src 192.168.5.231

net 192.168.5.0/23

显示过滤表达式
ip. addr== 192.168.1.1
协议. 协议字段: https://www.wireshark.org/docs/dfref/
tcp. portt