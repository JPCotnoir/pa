After physically connecting the Pineapple to your laptop, you must set up a static IP from your operating system or connect to the open access point on the Pineapple to finish set up

# Windows
---
1. Open Networking & Sharing Center
2. Select the WiFi Pineapple
3. Double-Click Internet Protocol Version 4 (TCP/IP)
4. Enter the following settings:
	- IP Address: 172.16.42.42
	- Subnet Mask: 255.255.0.0
	- Default Gateway: Blank
	- Preferred DNS: 8.8.8.8
	- Alternate DNS: 8.8.4.4
*Use any DNS server you'd like however it's recommended to use Google's for simplicity reasons*

# Linux
---
1. Once the device has fully booted, open your computers networking settings.

2. Find the new USB Ethernet device, and configure it to use the following IPv4 settings:

	- IP: 172.16.42.42
	
	- Netmask: 255.255.255.0
	
	- Gateway: Unset, or 0.0.0.0

### Command Line Configuration

1. Determine hardware name (eth0,dev0, etc.)
2. Enter the following commands:
	`$ sudo ip link set eth0 down`
	`$ sudo ip addr add 172.16.42.42/255.255.255.0 dev eth0`
	`$ sudo ip link set eth0 up`
	**Note the "eth0" will be the name determined in Step 1.**

# Setup over WiFi
---
The Pineapple will serve and open wireless network name `Pineapple_XXXX` with `XXXX` being the last 4 characters of the devices MAC address. Connect to this network to receive a DCHP IP from the device. 

After connecting to the AP, during the setup process, the device will prompt you to push a button so ensure you're next to the device.

## Logging In
---
After setup, the Pineapple will automatically remove the setup network and you will have to manually connect to the network created during the setup and then navigate to http://172.16.42.1:1471

After navigating to the web management portal, use *root* as the username and the password you created during the setup process.





