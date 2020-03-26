## Connecting to pfsense UPS master server from Synology NAS
Configuration:
- Synology NAS (example: LAN IP is 192.168.0.5)
- pfsense box / firewall (example shown: LAN IP is 192.168.0.1)
- UPS connected via USB to pfsense server (Testing: CyberPower branded UPS)

## Configure pfsense to connect to UPS via usb

**Install nut from package manager**
<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/pfsense_ups_config_package.png" width="800">

**Configure UPS NUT package**

<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/pfsense_ups_config_1_of_2.png" width="800">
<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/pfsense_ups_config_2_of_2.png" width="800">

**You may need to restart the pfsense system before it will recognise the UPS**

Alternatively you can SSH into the pfsense box and run the following command:
`/etc/rc.d/devfs restart`

## Configure Synology NAS to connect to pfsense for UPS information

**Synology NAS OS version at time of testing was: 4.4.1.1216 (2020/02/14)**

<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/synology_nas_ups_version.png" width="200">

**Enable "Network UPS slave" in "External Device" of Synology control panel**

<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/synology_nas_ups_slave.png" width="800">

## Optional: Advanced Synology configuration changes

Advanced UPS configuration changes can be made to the Synology NAS - using SSH (has to be enabled first) in Control Panel > Network & File Services > Telnet / SSH. 

UPS configuration files are located in `/etc/config/ups/`

