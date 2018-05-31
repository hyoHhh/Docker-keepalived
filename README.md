### Keepalived
---
Keepalived是一个基于VRRP协议来实现的服务高可用方案,可以利用其来避免单点故障。

### 变量
---
- VRID          VRRP的ID,多节点要设置一致。
- INTERFACE     绑定的网卡
- VIRTUAL_IP    VIP地址
- VIRTUAL_MASK  VIP的网段
- CHECK_IP      检查的ip地址
- CHECK_PORT    检查的端口号

### 版本
---
- 1.2 (docker tags: 1.3.9, latest) : keepalived版本为1.3.9

### 使用
---
```bash
docker pull lework/keepalived:v1.3.9
docker run -tid --name keepalived --restart=always --net=host --cap-add=NET_ADMIN \
  -e VRID=53 \
  -e INTERFACE=ens33 \
  -e VIRTUAL_IP=192.168.77.140 \
  -e VIRTUAL_MASK=24 \
  -e CHECK_IP=any \
  -e CHECK_PORT=22 \
  lework/keepalived:v1.3.9
```
