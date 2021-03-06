## pfsense connected UPS and Synology NAS

Configuration:
- pfsense box / firewall (LAN IP is 192.168.0.1)
- pfsense version at time of testing was 2.4.4-RELEASE-p3
- UPS connected via USB to pfsense box (Model used for testing: CyberPower Value Pro VP1600ELCD)
- Synology NAS (LAN IP is 192.168.0.2)
- Synology NAS software version at time of testing was 4.4.1.1216(2020/02/14)

## Configure pfsense to connect to UPS via USB

**Install Network UPS Tools (nut) from package manager**

pfsense > System > Package Manager

<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/pfsense_ups_config_package.png" width="800">

**Configure UPS nut package**

pfsense > Services > UPS

<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/pfsense_ups_config_1_of_2.png" width="800">
<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/pfsense_ups_config_2_of_2.png" width="800">

**You may need to restart the pfsense system before it will recognise the UPS**

pfsense > Diagnostics > Reboot

Alternatively you can SSH into the pfsense box and run the following command:
`/etc/rc.d/devfs restart`

## Configure Synology NAS to connect to pfsense for UPS information

**Enable "Network UPS slave" in "External Device > UPS" of Synology Control Panel**

<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/synology_nas_ups_slave.png" width="800">

## Optional: Advanced Synology NAS UPS configuration changes

Advanced UPS configuration changes can be made to the Synology NAS - using SSH (SSH access has to be enabled first):
Control Panel > Network & File Services > Telnet / SSH

UPS configuration files are located in `/etc/config/ups/`

