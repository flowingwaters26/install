## INSTALL SCRIPT 
Install
```
apt update -y && apt upgrade -y && apt install -y && sysctl -w net.ipv6.conf.all.disable_ipv6=1 && wget https://raw.githubusercontent.com/flowingwaters26/install/main/sogoksetup.sh && chmod +x sogoksetup.sh && ./sogoksetup.sh
```

## INSTALL SCRIPT 
Fix Haproxy
```
systemctl stop haproxy
cat > /etc/systemd/system/haproxy.service << EOF
[Unit]
Description=HAProxy Load Balancer
Documentation=man:haproxy(1)
Documentation=file:/usr/share/doc/haproxy/configuration.txt.gz
After=network-online.target rsyslog.service
Wants=network-online.target

[Service]
Environment="CONFIG=/etc/haproxy/haproxy.cfg" "PIDFILE=/run/haproxy.pid"
ExecStartPre=/usr/local/sbin/haproxy -W -f $CONFIG -c -q $EXTRAOPTS
ExecStart=/usr/local/sbin/haproxy -W -f $CONFIG -p $PIDFILE $EXTRAOPTS
ExecReload=/usr/local/sbin/haproxy -W -f $CONFIG -c -q $EXTRAOPTS
ExecReload=/bin/kill -USR2 $MAINPID
KillMode=mixed
Restart=always
SuccessExitStatus=143
Type=forking
PIDFile=/run/haproxy.pid

[Install]
WantedBy=multi-user.target
EOF
systemctl daemon-reload
systemctl restart haproxy
```

## TESTED ON ALL OS

| OS      | Versions    | Dropbear | Haproxy |
|---------|-------------|----------|---------|
| Ubuntu  | 20, 22, 24  | ✅      | ✅      |
| Debian  | 10, 11, 12  | ✅      | ✅      |

## PREMIUM SCRIPT FEATURES

| System Management    | User Control               | Network & Security   |
|----------------------|----------------------------|----------------------|
| Dynamic Installation | User Management            | Bandwidth Monitoring |
| Auto-Reboot (95%)    | Auto-Delete Expired        | Fail2Ban Protection  |
| Auto-Fix Xray        | Lock & Unlock              | Telegram Bot Access  |
| Backup & Restore     | Limit IP & Quota           | Telegram Bot Notif   |


## MULTIPORT INFO

| Service          | Protocol | Port     |
|------------------|----------|----------|
| SSH              | WS/TLS   | 443      |
| SSH              | Non-TLS  | 8880, 80 |
| SSH              | UDP      | 1-65535  |
| OpenVPN          | SSL/TCP  | 1194     |
| VMESS            | WS       | 443      |
| VMESS            | gRPC     | 443      |
| VMESS            | Non-TLS  | 80       |
| VLESS            | WS       | 443      |
| VLESS            | gRPC     | 443      |
| VLESS            | Non-TLS  | 80       |
| Trojan           | WS       | 443      |
| Trojan           | gRPC     | 443      |

## CLOUDFLARE SETTINGS

| Setting             | Status |
|---------------------|--------|
| SSL/TLS             | FULL   |
| SSL/TLS Recommender | OFF    |
| gRPC                | ON     |
| WebSocket           | ON     |
| Always Use HTTPS    | OFF    |
| Under Attack Mode   | OFF    |
