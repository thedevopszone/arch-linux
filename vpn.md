# VPN Vlient

```
sudo pacman -Sy networkmanager networkmanager-openvpn network-manager-applet openvpn

sudo systemctl enable NetworkManager
sudo systemctl start NetworkManager

sudo mkdir -p /etc/sysctl.d/

sudo vi /etc/sysctl.d/40-ipv6.conf
net.ipv6.conf.all.disable_ipv6=1
net.ipv6.conf.default.disable_ipv6=1
net.ipv6.conf.lo.disable_ipv6=1
net.ipv6.conf.tun0.disable_ipv6=1
net.ipv6.conf.wlp3s0.disable_ipv6=1

sudo systemctl restart systemd-sysctl
sudo systemctl restart NetworkManager

cd /etc/openvpn
kixz.ovpn

nmcli connection import type openvpn file kixz.ovpn

sudo systemctl restart systemd-sysctl
sudo systemctl restart NetworkManager

dnsleaktest.com

```
