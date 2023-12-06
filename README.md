<p align="center"> 

<h1> Inspecting Traffic Between Virtual Machines</h1>
In this example, I observe network traffic to and from Virtual Machines with Wireshark. <br />
<br>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop (Microsoft)
- Powershell (Microsoft)
- Network Protocols (ICMP, SSH, DHCP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04
<br>

<h3>1. Observing ICMP Traffic and changing NSG Inbound Traffic Rules</h3>
<p><i>Observations: Upon changing the Network Security Group (NSG) inbound traffic rules to deny all ICMP traffic, the ping from VM1 to VM2 immediately timed out and Wireshark captured only request packets.</p></i>
<br>
<p>-Create 2 virtual machines (VMs) in Azure on the same virtual network/subnet. One running WindowsOS and one running LinuxOS (Ubuntu):</p>
<a href="https://imgur.com/Kng2TVG"><img src="https://i.imgur.com/Kng2TVG.png" title="source: imgur.com" /></a>
<br>
<br>
<br>
<p>-Remote Desktop connect to VM1 (WindowOS), open WireShark and filter for ICMP traffic. Open Powershell and perpetual ping VM2 (LinuxOS):</p> 
<a href="https://imgur.com/mCwoi9z"><img src="https://i.imgur.com/mCwoi9z.png" title="source: imgur.com" /></a>
<br>
<br>
<br>
<p>-In Azure, configure VM2's (LinuxOS) inbound traffic by creating an inbound traffic rule within VM2's Network Security Group:</p>

![NSG VM2 Before](https://github.com/emily-hardy/azure-network-protocols/assets/150190489/360d7d68-b375-45f5-9a68-a2fbda03fca5)
<br>
<p>-New Inbound Security Rule = deny all incoming ICMP traffic:</p>
<a href="https://imgur.com/pJ9mOtc"><img src="https://i.imgur.com/pJ9mOtc.png" title="source: imgur.com" /></a>
<br>
<br>
<br>
<p>-In VM1's (WindowsOS) remote session, observe the ICMP request/reply timeout after VM2's NSG settings have been altered:</p>

![ICMP timeout](https://github.com/emily-hardy/azure-network-protocols/assets/150190489/e525ec61-5e81-479e-b28d-e2276e8b517d)
<br>
<br>
<br>
<h3>2. Connecting to VM2 from VM1 via SSH</h3>
<a href="https://imgur.com/N4Eu5ju"><img src="https://i.imgur.com/N4Eu5ju.png" title="source: imgur.com" /></a>
<br>
<br>
<br>
<h3>3. Observing DHCP Traffic when Renewing VM1's IP Address  </h3>
<a href="https://imgur.com/ujOGs91"><img src="https://i.imgur.com/ujOGs91.png" title="source: imgur.com" /></a>
