# OpenstackNeutron

Openstack Networkign (Neutron) Components


Neutron Server :
----------------
This is the main server that handles the api requests from horizon/cli .
The neutron server runs in the controller node.

Neutron Plugins:
---------------
Plugins are pluggable python classes that are invoked while responding to API requests.
Plugins are classified in to two types
1. Core Plugins - handle L2 conenctivity and ip address management
2. service plugins - handles Routing (L3), firewall and load-balancing services etc

Note: plugin code is executed as part of Neutron Server on the Controller node.

The most important core plugin is the ML2 plugin. This supports a wide variety of L2 functionaalities
such as VLAN, VXLAN and GRE etc. These technologies are referred to as Type drivers.

And these technologies in turn can be implemented using various methods like Open vSwitch or via network hardware. 
ML2 Plugin allows different implementation methods using mechanism (mech) drivers.

Although ML2 is the sole core plugin, it can support multiple type drivers and mechanism drivers.

Type drivers
-------------

An ML2 type driver maintains type-specific network state, validates provider
network attributes, and describes network segments using provider attributes.
Provider attributes include network interface labels, segmentation IDs, and network
types. Supported network types include local, flat, vlan, gre, and vxlan.

Linux Bridge vs OpenVswitch type drivers
----------------------------------------
The LinuxBridge type driver supports local, flat, vlan, and vxlan network types,
while the Open vSwitch driver supports all of those as well as the gre network type.

Mechanism Drivers
-----------------
An ML2 mechanism driver is responsible for taking information established by
the type driver and ensuring that it is properly implemented. Multiple mechanism
drivers can be configured to operate simultaneously, and can be described using
three types of models:
• Agent-based: This includes LinuxBridge, Open vSwitch, and others
• Controller-based: This includes OpenDaylight, VMWare NSX, and others
• Top-of-Rack: This includes Cisco Nexus, Arista, Mellanox, and others
Mechanism drivers to be discussed in this book include:
• LinuxBridge
• Open vSwitch
• L2 Population

Neutron Agents
--------------
The Neutron agents implement very specific networking functionality. Examples include DHCP Agent, L3 Agent 

Neutron Architecture:
---------------------

![alt text](https://github.com/kesavand/OpenstackNeutron/blob/master/Neutron.jpg)



![alt text](https://github.com/kesavand/OpenstackNeutron/blob/master/NeutronArchitecture.PNG)


