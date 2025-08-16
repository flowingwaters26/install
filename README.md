## INSTALL SCRIPT 
Install
```
apt update -y && apt upgrade -y && apt install -y && sysctl -w net.ipv6.conf.all.disable_ipv6=1 && wget https://raw.githubusercontent.com/flowingwaters26/install/main/sogoksetup.sh && chmod +x sogoksetup.sh && ./sogoksetup.sh
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
