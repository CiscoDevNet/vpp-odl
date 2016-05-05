# Opendaylight VPP vBridge Manager 

<img src="https://raw.githubusercontent.com/CiscoDevNet/vpp-odl/master/images/fdio-vpp.png" alt="alt text" width=400px height=200px>

OpenDaylight (ODL) is an open source application development and delivery platform. Vector Packet Processor (VPP) is an open source, high performance dataplane development platform. VPP vBridge Manager is an ODL application enabling users to define VPP-based virtual bridge domain(s) for L2 connectivity. 


## Team:

- Dave Wallace
- Daniel Malachovsky
- Robert Varga
- Chris Metz
- Andrej Vanko
- Ed Warnicke
- Alex Zverev

### Project Link:

[Click Here](https://github.com/CiscoDevNet/vpp-odl) 

### Social Tags:

SDN, Opendaylight, Open Source, FD.io, VPP, Honeycomb, NETCONF, YANG, REST

### Project Kick-off Date:

November 2015

### Current Status:

Implemented. 

## Application Overview:

FD.io is a new industry consortium operating under the auspices of the Linux Foundation. The objective of this consortium is to develop and support innovative open source technologies aimed at simple, efficient and high performance solutions for network dataplanes.  

Vector Packet Processor (VPP) is the first project that the FD.io consortium will focus on. VPP is a new open source dataplane development platform providing high-performance packet forwarding and processing in networks. The initial application supported by VPP is virtual packet switching. A VPP looks and acts like any packet switching device with one or more multiple interfaces for connecting other devices and hosts.  The difference is that the VPP devices are virtual (software-only) instantiations configured as a single- or multi-device virtual network typically deployed in a cloud or data center environment.

Note: Honeycomb is a lightweight stripped-down version of ODL. It runs co-resident with VPP nodes and provides a simple but powerful set of APIs based on ODL used for VPP programming. In the figures and discussion below, it is assumed that there is honeycomb agent associated with each VPP node. The ODL controller is communicating via netconf or restconf with the honeycomb agent. More information on the Honeycomb agent can be found [here](https://www.youtube.com/watch?v=ZqH9nwh83DI).  

A bridge domain is a set of interfaces belonging to one or multiple switching devices configured as a Layer 2 network broadcast domain. In this application of VPP, interfaces on one or more VPP nodes are assigned to a virtual bridge domain (vBD). If the VPP nodes with assigned interfaces belonging to the same vBD reside in separate IP networks (a common scenario in cloud networks) then a tunnel is established between the VPP nodes to transport L2 traffic.

Figure 1 illustrates the general architecture of this solution. 
![](https://raw.githubusercontent.com/CiscoDevNet/vpp-odl/master/images/VPP-app-arch.png)
*Figure 1. VPP vBridge Domain App Solution*

Hosts #1 and #2 are connected to VPP Nodes #1 and #2 respectively. VPP vBridge Domain Manager is an ODL application enabling VPP interface assignments to defined virtual bridge domains. If the VPP nodes reside in separate IP networks, then an inter-VPP tunnel is automatically setup. The result is that Hosts #1, Hosts#2 and any other devices attached via an VPP interface to the same virtual bridge domain can talk to each other via L2.

VPP vBridge Domain Manager performs two basic functions: VPP Inventory and Bridge Domain Management. 

VPP Inventory is used to:

- Configure connections from the application (thru the ODL controller) to each VPP node

- Gather and display VPP interfaces

Bridge Domain Manager is used to:

- Configure a vBD

- Assign VPP interfaces to a vBD

- Show both the overlay and underlay topologies. 

In summary the VPP vBridge Manager App provides a web browser interface for managing VPP-based virtual Bridge Domains.

### VPP vBridge Manager Application Video

[Click here](https://www.youtube.com/watch?v=vs1XzOOpaCo)
 
### Code

[Click Here](https://wiki.fd.io/view/Honeycomb) 

### References

[ODL MD-SAL](https://wiki.opendaylight.org/view/OpenDaylight_Controller%3aMD-SAL)

[YANG Tutorial](http://www.slideshare.net/tailfsystems/netconf-yang-tutorial)

[Running Honeycomb](https://wiki.fd.io/view/Honeycomb/Running_Honeycomb)

[FD.io View](https://wiki.fd.io/view/)

[FD.io Technology](https://fd.io/technology)

[Honeycomb vBD Project Proposal](https://wiki.opendaylight.org/images/6/63/HoneycombVBD.pdf)
