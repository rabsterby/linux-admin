# Oracle cloud manage server on Oracle Linux 7.9

## SSL

### Certbot

#### Install advanced repo

`sudo rpm -ivh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm`

#### Install snapd

`sudo yum install snapd`

#### Enable snapd

`sudo systemctl enable --now snapd.socket`

#### Install certbot

`sudo snap install --classic certbot`

#### Make Certificate and configure apache

`sudo certbot certonly --apache`

### Manage firewall rules

#### add permanent rule to public zone for udp on 8080 port 

`sudo firewall-cmd --permanent --zone=public --add-port=8080/udp`

then reload firewall

`sudo firewall-cmd --reload`

#### All IPTABLE rules

`sudo iptables -L`

#### add filter rule to IPTABLE for tcp on 80 port 

`sudo iptables -t filter -A INPUT -p tcp --dport 80 -j ACCEPT`


#### scan ip for open ports

sudo nmap -sS 152.67.64.24

#### Install NodeJs & nvm

`sudo yum install nodejs`

##### Install nvm

`curl -o https://raw.githubusercontent.com/creationix/nvm/v0.33.6/install.sh | bash`

#### Error on bcrypt compile

`sudo yum install -y gcc-c++ make`

 
