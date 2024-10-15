# ASSIGNMNENT OF VLAN AND VLAN TRUNKING
# PROJECT INTERVLAN COMMUNICATION OF SCHOOL NETWORK

## TO ASSIGN VLAN TO DIFFERENT END DEVICES AND CONFIGURE THE SWITCH FOR INTER VLAN COMMUNICATION

THIS PROJECT IS A NETWORK SIMULATION OF A SCHOOL WITH MULTIPLE DEPARTMENT AND MULTIPLE END HOST. MY MAIN GOAL WITH THIS PROJECT IS TO ASSIGN VLAN SETTING FOR END DEVICES ON DIFFERENT SWITCH AND ENABLE INTER VLAN ROUTING BETWEEN DEVICES

### Skills Learned

- Advanced understanding of VLAN CONCEPTS AND VLAN CONFIGURATION
- ADVANCED UNDERSTANDING OF VLAN AND INTER VLAN COMMUNICATION
- ABILITTY TO IDENTIFY COMMUNICATION BETWEEN MULTIPLE VLANS
- ENHANCED KNOWLEDGE OF SUBNETTING WITH IPV4 ADDRESS
- ABILITY TO FIND RESOURCES TO HELP ME WITH SWITCH CONFIGURATION

### Tools Used

- PACKET TRACER FOR NETWORK SIMULATION
- ENDPOINT DEVICES THAT ARE PART OF DIFFERENT VLANS
- CISCO ROUTER AND SWITCH FOR NETWORK COMMUNICATION
## Steps
##Identify Departments and Devices:
-Start by determining the departments (e.g., Admin, Faculty, Students) that need segmentation. Identify the devices (e.g., computers, printers) for each VLAN.



## Create VLANs:
-Assign a unique VLAN ID to each department. For example:

-VLAN 10 for Admin

-VLAN 20 for Faculty

-VLAN 30 for Students




## Configure the Switch for VLANs:
Enter global configuration mode on the switch.

Use the following commands to create VLANs:


Switch(config)# vlan 10

Switch(config-vlan)# name Admin


Switch(config)# vlan 20

Switch(config-vlan)# name Faculty


Switch(config)# vlan 30

Switch(config-vlan)# name Students


## Assign VLANs to Switch Ports:
Assign devices to their respective VLANs by configuring the switchports.

Avoid using VLAN 1 for security reasons.

Example configuration for ports:

Switch(config)# interface FastEthernet 0/1

Switch(config-if)# switchport mode access

Switch(config-if)# switchport access vlan 10



Switch(config)# interface FastEthernet 0/2

Switch(config-if)# switchport mode access

Switch(config-if)# switchport access vlan 20



Switch(config)# interface FastEthernet 0/3

Switch(config-if)# switchport mode access

Switch(config-if)# switchport access vlan 30




## Configure Trunk Ports Between Switches:
To allow VLAN traffic between switches, configure trunk ports on each switch:

Switch(config)# interface FastEthernet 0/24

Switch(config-if)# switchport mode trunk

Switch(config-if)# switchport trunk allowed vlan 10,20,30



## Enable Inter-VLAN Routing:
If using a router, configure router-on-a-stick to route between VLANs:

Enter the router’s subinterface configuration for each VLAN:


Router(config)# interface FastEthernet 0/0.10

Router(config-subif)# encapsulation dot1Q 10

Router(config-subif)# ip address 192.168.10.1 255.255.255.0



Router(config)# interface FastEthernet 0/0.20

Router(config-subif)# encapsulation dot1Q 20

Router(config-subif)# ip address 192.168.20.1 255.255.255.0



Router(config)# interface FastEthernet 0/0.30

Router(config-subif)# encapsulation dot1Q 30

Router(config-subif)# ip address 192.168.30.1 255.255.255.0




## Test Connectivity:
Verify that devices within the same VLAN can communicate.

Test inter-VLAN communication by pinging devices from different VLANs to confirm routing is functional.


## Troubleshoot and Optimize:
Review the configuration and make sure the trunking, VLAN assignments, and routing are set up correctly. Ensure each department’s traffic remains secure and properly segmented.

