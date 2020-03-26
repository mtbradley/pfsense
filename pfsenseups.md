## Connecting to pfsense UPS master server from Synology NAS
Configuration:
- Synology NAS (example: LAN IP is 192.168.0.5)
- pfsense server / firewall (example shown: LAN IP is 192.168.0.1)
- UPS connected via USB to pfsense server (Testing: CyberPower branded UPS)

## Configure pfsense to connect to UPS via usb
**Install nut from package manager**
<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/pfsense_ups_config_package.png">

## Configure Synology NAS to connect to pfsense for UPS information
**Synology NAS OS version at time of testing was: 4.4.1.1216 (2020/02/14)**
<img src="https://raw.githubusercontent.com/mtbradley/pfsense/master/ups/synology_nas_ups_version.png" width="200">



