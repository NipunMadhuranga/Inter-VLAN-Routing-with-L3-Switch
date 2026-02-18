# Inter-VLAN-Routing-with-L3-Switch

Project Overview: Inter-VLAN Routing with L3 Switching and VTP
This lab demonstrates the configuration of a hierarchical campus network. By using a Layer 3 Switch (Multilayer Switch) as the core and VTP for database management, the network achieves full reachability across three distinct VLANs without the bottleneck of a traditional "Router-on-a-Stick" setup.

1. VLAN Management with VTP
To simplify administration and ensure consistency across the switching fabric, VTP (VLAN Trunking Protocol) was utilized:

VTP Server: One central switch was configured as the VTP Server to create and manage the three VLANs.

VTP Clients: The remaining switches were set to VTP Client mode, allowing them to automatically learn the VLAN database (VLAN IDs and names) from the server.

Trunking: High-speed trunk links were established between switches to carry traffic for all three VLANs across the network.

2. Layer 3 (Multilayer) Switching
Instead of using a dedicated router, a Layer 3 Switch was configured to perform inter-VLAN routing:

SVIs (Switched Virtual Interfaces): IP addresses were assigned to the virtual interfaces for each of the three VLANs (e.g., interface Vlan 10, interface Vlan 20, etc.). These act as the default gateways for the end devices.

IP Routing: The command ip routing was enabled on the multilayer switch to activate its hardware-based routing engine.

3. Network Segmentation
The network is logically divided into three functional areas:

VLAN A, B, and C: Each segment represents a different department or security zone.

Broadcast Isolation: By segmenting the network into VLANs, broadcast traffic is contained within its own subnet, improving overall network performance.

4. Connectivity & Verification
The configuration was verified by testing end-to-end communication:

Inter-VLAN Communication: Any end device in one VLAN (e.g., VLAN 10) can successfully ping a device in another VLAN (e.g., VLAN 30).

Efficiency: Because routing happens at the hardware level on the L3 switch, the communication between VLANs occurs at wire speed with minimal latency.

Key Outcomes
Administrative Efficiency: VTP eliminated the need to manually create VLANs on every individual switch.

High Performance: The Layer 3 switch provides faster routing than a traditional router while reducing the number of physical cables required.

Full Reachability: A seamless communication path exists between all users, regardless of their physical location or VLAN assignment.
