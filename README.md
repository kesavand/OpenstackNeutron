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
ML2 Plugin allows different implementation methods using mechanism drivers.
Although ML2 is the sole core plugin, it can support multiple type drivers and mechanism drivers.

Neutron Agents
--------------
The Neutron agents implement very specific networking functionality. Examples include DHCP Agent, L3 Agent 


https://cloudbuilder.in/blogs/2015/03/31/openstack-neutron-plugins-and-agents/
