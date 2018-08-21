# zabbix-template-mdraid

Created and tested for zabbix server v 3.4

Used for monitoring Linux md RAID status via zabbix-agent service installed on monitored host. It is doing autodiscovery of md devices and then create approprite Items and Triggers.

1. Install and configure zabbix-agent on host
2. Import Template to your zabbix server
3. Configure Host and assign Template on zabbix server

## Zabbix-agent installation: 
CentOS/RHEL 7:
```
rpm -Uvh http://repo.zabbix.com/zabbix/3.4/rhel/7/x86_64/zabbix-release-3.4-2.el7.noarch.rpm
yum install zabbix-agent
```
## Zabbix-agent configuration:
```
cd /etc/zabbix/zabbix-agentd.d/
wget https://github.com/lukaskaplan/zabbix-template-mdraid/blob/master/userparameter_md.conf

setenforce 0 
systemctl enable zabbix-agent
systemctl start zabbix-agent
service zabbix-agent status
```

