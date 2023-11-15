# Zabbix installation

## Zabbix server installation

1. [Install Apache](https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-20-04)
2. [Install MySql actual 07.2023](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04) You can also see the MySQL installation in the Template repository.
3. [Install Zabbix Server](https://www.zabbix.com/download?zabbix=6.4&os_distribution=ubuntu&os_version=22.04&components=server_frontend_agent&db=mysql&ws=apache). Select your OS and other settings.
4. Go to http://yourserverIP/zabbix and finish installation. Provide credentials for the database.
5. The Zabbix fronintend interface may not be displayed or may break because language packs are not installed on your virtual machine or container! 
It should be something like this:

`apt-get install -y language-pack-en`

6. Restart


## Zabbix agent installation

1. [Install Zabix agent](https://www.zabbix.com/download?zabbix=6.4&os_distribution=ubuntu&os_version=22.04&components=agent&db=&ws=). Select your OS
2. Change the parameters in the file(/etc/zabbix/zabbix_agentd.conf) on the Zabbix server IP [Source](https://www.devopsschool.com/blog/how-to-install-configure-zabbix-agent/)

`ServerActive=<serverIP>`
`Server=<serverIP>`
`Hostname=Zabbix server`

3. Restart
4. Create host.[Link](https://www.zabbix.com/documentation/current/en/manual/config/hosts/host]
5. To do green avability ZBX. You need set up any check(active or passive, I forget which one). Example you can find in video(Zabbix basic concepts) on [this page below](https://www.zabbix.com/download?zabbix=6.4&os_distribution=ubuntu&os_version=22.04&components=agent&db=&ws=)

# Zabbix monitoring

## Simple ping

Choose `ICMP Ping` in templates

## MySql monitoring

Follow this [guide](https://www.zabbix.com/documentation/current/en/manual/guides/monitor_mysql#create-mysql-user)