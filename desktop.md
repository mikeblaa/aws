# Fedora 29

```shell
dnf -y group install "Fedora Workstation"
systemctl set-default graphical.target
systemctl default
dnf -y install xrdp tigervnc-server
systemctl enable --now xrdp
firewall-cmd --permanent --add-port=3389/tcp
firewall-cmd --reload
chcon --type=bin_t /usr/sbin/xrdp
chcon --type=bin_t /usr/sbin/xrdp-sesman
```

# CentOS 7

https://www.itzgeek.com/how-tos/linux/centos-how-tos/install-xrdp-on-centos-7-rhel-7.html
https://www.itzgeek.com/how-tos/linux/centos-how-tos/install-gnome-gui-on-centos-7-rhel-7.html

```shell
yum -y group install "GNOME Desktop"
systemctl set-default graphical.target
systemctl default
rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
yum -y install xrdp tigervnc-server
systemctl enable --now xrdp
firewall-cmd --permanent --add-port=3389/tcp
firewall-cmd --reload
chcon --type=bin_t /usr/sbin/xrdp
chcon --type=bin_t /usr/sbin/xrdp-sesman
```

XRDP

https://devopscube.com/how-to-setup-gui-for-amazon-ec2-rhel-7-instance/

```shell
sudo yum -y update
sudo yum groupinstall -y "Server with GUI"
sudo systemctl set-default graphical.target
sudo systemctl default

sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-1.el7.nux.noarch.rpm
sudo yum install -y xrdp tigervnc-server
chcon --type=bin_t /usr/sbin/xrdp
chcon --type=bin_t /usr/sbin/xrdp-sesman
sudo systemctl enable --now xrdp
sudo firewall-cmd --permanent --add-port=3389/tcp
sudo firewall-cmd --reload
sudo passwd ec2-user
sudo su
passwd
```

NX

```shell
sudo rpm -i nomachine_6.3.6_1_x86_64.rpm
sudo firewall-cmd --permanent --add-port=4000/tcp
sudo firewall-cmd --permanent --add-port=4810/udp
sudo firewall-cmd --reload
```
