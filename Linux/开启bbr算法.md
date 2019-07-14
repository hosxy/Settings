### 1、要求
linux 内核要 >= 4.9,可使用 `uname -r` 查看 <br>

### 2、开启
使用root权限执行以下命令：
``` bash
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
sysctl -p
```
### 3、验证
执行：
``` bash
sysctl net.ipv4.tcp_available_congestion_control
```
显示类似：
```
net.ipv4.tcp_available_congestion_control = bbr cubic reno
```
执行：
``` bash
lsmod | grep bbr
```
显示类似：
```
tcp_bbr                20480  14
```
