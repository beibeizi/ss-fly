# 快速搭建ssr脚本
网上流传的那份加密方式失效因此更改一份保存在此方便使用  

##支持系统  
CentOS 6+  
Debian 7+  
Ubuntu 12+  

## 操作步骤
1.安装  git  
2.输入  git clone -b master https://github.com/beibeizi/ss-fly  
3.输入  ss-fly/ss-fly.sh -i 密码 端口  
端口不填默认为1024  
默认加密方式为aes-256-gcm  

修改配置文件：vim /etc/shadowsocks.json  
停止ss服务：ssserver -c /etc/shadowsocks.json -d stop  
启动ss服务：ssserver -c /etc/shadowsocks.json -d start  
重启ss服务：ssserver -c /etc/shadowsocks.json -d restart  
卸载ss服务：ss-fly/ss-fly.sh -uninstall  


## 开启bbr加速
输入  ss-fly/ss-fly.sh -bbr  
判断是否成功  
输入  sysctl net.ipv4.tcp_available_congestion_control  
返回 net.ipv4.tcp_available_congestion_control = bbr cubic reno 则成功  
