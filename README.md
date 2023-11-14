<p align="center">
<h1>Inspecting Traffic Between Azure Virtual Machines</h1>
In this example, I observe network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Command-Line Tools
- Network Protocols (ICMP, SSH, DNS)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04
<br>

<h3>1. Observing ICMP Traffic and changing NSG Inbound Traffic Rules</h3>
<p><i>Observations: Upon changing the Network Security Group (NSG) inbound traffic rules to deny all ICMP traffic, the ping from VM1 to VM2 immediately timed out and Wireshark captured only request packets.</p></i>
<br>
-Create 2 virtual machines (VMs) in Azure on the same virtual network/subnet:
![VMs](https://github.com/emily-hardy/azure-network-protocols/assets/150190489/4ae25cb0-8209-4a78-b40d-b9f0ed4c7c33)


<br>
-Remote Desktop connect to VM1, open WireShark and filter for ICMP traffic, open Powershell and perpetual ping VM2: 
![VM1 ping VM2][(https://github.com/emily-hardy/azure-network-protocols/assets/150190489/8e3741a6-87c2-4073-a43b-d1150c4e2d93)]


<br>
-Create an inbound traffic rule on VM2's Network Security Group to disable all incoming ICMP traffic:

![NSG VM2 Before](https://github.com/emily-hardy/azure-network-protocols/assets/150190489/360d7d68-b375-45f5-9a68-a2fbda03fca5)
<br>
![Inbound Security Rule - Deny ICMP](https://github.com/emily-hardy/azure-network-protocols/assets/150190489/273f1f13-74d3-4b9c-9fb7-4da47ea2c9c9)


<br>
In VM1's remote session, observe the ICMP request/reply timeout after VM2's NSG settings have been altered:

![ICMP timeout](https://github.com/emily-hardy/azure-network-protocols/assets/150190489/e525ec61-5e81-479e-b28d-e2276e8b517d)


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
