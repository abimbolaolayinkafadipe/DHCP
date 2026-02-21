Network Design, Configuration, and Security Implementation
I was given the chance to build and set up a full enterprise-style network for a non-disclosed company after moving to a new area and entering a new work environment. Because it required not just practical configuration skills but also organized planning, security awareness, and the capacity to implement scalable networking solutions under practical limits, this experience turned into a pivotal point in my technical development. In order to complete the project, a segmented network with Class A private addressing had to be designed, VLANs had to be implemented, Layer 2 and Layer 3 switching had to be configured, inter-VLAN routing had to be enabled, and centralized DHCP and DNS services had to be deployed. Delivering this solution successfully confirmed my abilities to work autonomously in a new setting and bolstered my confidence as a network engineer.

Network Design Objectives

Creating a safe, scalable, and manageable internal network that could accommodate several departments while reducing broadcast traffic and streamlining administration was the project's main goal. Clear user group separation, effective IP address management, and the capacity to grow without completely revamping the network were all necessary for the organization. Performance, security, and dependability were all given similar weight.
I created a topology with two Layer 2 access switches linked to a single multilayer switch (MLS) serving as the core and routing device in order to satisfy these needs. Reduced complexity at the access layer, centralized control, and effective traffic flow were all guaranteed by this hierarchical method.

Addressing Strategy and Class A Subnetting

Using Class A private addressing (10.0.0.0/8) and allocating subnets from the 10.60.0.0 range was a crucial architectural choice. The subnets selected were 10.60.0.0.

10.60.16.0
10.60.32.0
10.60.64.0

/20 subnet mask was used to size each subnet, giving each VLAN more than 4,000 useable IP addresses. This strategy had a number of benefits:

1.	Scalability
Large subnets allowed the network to expand without needing to be readdressed right away. Without using up all of the IP space, departments could add more users, devices, or services.

2.	Network Planning was Simplified
The addressing scheme was simple to comprehend, document, and troubleshoot because of the consistency in subnet increments. This enhanced long-term maintainability and decreased administrative overhead.


3.	Summarized Route
Future route summarization, which increases routing efficiency and decreases the size of the routing table if the network grows, was made possible by the structured addressing.

4.	Security in Private Addressing
The overall security posture was strengthened by using RFC 1918 private addressing, which guaranteed that internal IP addresses were not made public.

VLAN segmentation and inter-VLAN routing were made possible by this addressing technique.

Logical Network Architecture and VLAN Segmentation
I created four VLANs, each mapped to a distinct subnet, to rationally divide traffic and improve security:
VLAN 100: 10.60.0.0/20
VLAN 200: 10.60.16.0/20
VLAN 300: 10.60.32.0/20
VLAN 400: 10.60.64.0/20

A distinct functional department within the company was represented by each VLAN. This segmentation enhanced performance, decreased broadcast domains, and lessened the effect of possible security issues.

Multilayer Switching and SVI Configuration

Inter-VLAN routing was handled by the multilayer switch (MLS), which functioned as the network's central component. I set up Switched Virtual Interfaces (SVIs) for every VLAN and activated IP routing on the MLS. For each VLAN, each SVI served as the default gateway.

The MLS took over as the exclusive point of control for:

●	Communication between VLANs
●	DHCP relay
●	Gateway services by default
●	Trunk aggregation and core switching

IP Address Management and DHCP Automation
I used automatic DHCP assignment to expedite device onboarding and lower manual configuration failures. A centralized DHCP server was set up.

This design offered a number of advantages:

●	Deployment of zero-touch endpoints
When a new device connects to the network, a proper IP configuration is automatically sent to it.

●	Uniformity among VLANs
Standardized network settings, including gateway and DNS details, were sent to all clients.

●	Centralized management
Updates and audits were made simpler by managing DHCP scopes from a single location.

 
DHCP scope configuration:

●	The correct network and subnet mask were set up
●	The SVI is the default gateway.
●	Assignment of DNS servers


DNS Activation and Name Resolution
Internal name resolution was supported by DNS services. This improved usability and decreased configuration errors by enabling systems and users to access resources using hostnames rather than IP addresses.

DNS and DHCP integration allowed the network to guarantee:

●	Quicker troubleshooting
●	An enhanced user experience
●	Improved interoperability with services and apps

In order to transform the network from a rudimentary infrastructure into a fully operational enterprise environment, this phase was essential.

Access Ports and Trunking-Setup

I set up IEEE 802.1Q trunk links between the MLS and both Layer 2 access switches in order to accommodate numerous VLANs across switches. Trunking preserved logical separation while enabling required VLANs traffic to go over the physical link.

The Layer 2 switches' access ports were statically allocated to the corresponding VLANs. 

●	This guaranteed that devices were automatically assigned to the appropriate VLAN.
●	VLAN hopping without authorization was stopped.
●	The behavior of the network was secure and predictable.


This combination of access port control at the edge and trunking at the core adhered to industry best practices for enterprise networks.


Integration of Layer 2 and Layer 3 Switches
A distinct division of responsibilities was made possible by the employment of two Layer 2 switches and one Layer 3 switch: 

●	Layer 2 switches managed VLAN membership and end-device connection.
●	Core switching, policy enforcement, and routing were all managed by the Layer 3 switch.

This approach preserved great performance and centralized management at the core while reducing complexity at the access layer.

Security Benefits of the Design: 

Throughout the process, security was the main priority. By limiting lateral movement using VLAN isolation, the architecture enhanced security.


●	Inter-VLAN routing under control
●	Reduced broadcast exposure
●	IP addresses that are private
●	Network services that are centralized

Without having to reinvent the network, the hierarchical topology made it simpler to later incorporate monitoring, ACLs, and other security controls.

Overview of Topology
With the MLS at the center and two access switches branching outward, the final topology had a collapsed core architecture. This topology provided:

●	Superior performance
●	Simplified administration
●	Unobstructed routes for traffic
●	Cost-effectiveness


Additionally, it made it simple to expand in the future by adding more VLANs or access switches.
Personal Success and Career Advancement
It was a major accomplishment on both a personal and professional level to finish this project after moving. My ability to work autonomously, use theoretical knowledge in reality, and fulfill real-world expectations was proved by my ability to adapt to a new setting while delivering a technically competent solution.

This encounter increased my self-assurance in:

●	Planning and designing networks
●	Subnetting and IP addressing
●	Routing and switching
●	Automation of infrastructure
●	Security-conscious design


More significantly, it demonstrated that I am prepared to make a significant contribution in corporate networking settings. This network's successful deployment was not just a technical achievement but also a testament to my fortitude, flexibility, and dedication to lifelong learning.

In conclusion
This project serves as a thorough illustration of my networking skills. Every design choice, from DHCP automation and multilayer switching to Class A subnetting and VLAN segmentation, was deliberate and in line with industry best practices. Delivering this solution successfully in a new setting was a pivotal moment in my career and a powerful testament to my abilities, self-control, and technical maturity.
