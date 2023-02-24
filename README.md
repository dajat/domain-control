<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDP, DNS, DHCP, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Windows 10 and Ubuntu (Linux) Virtual Machines
- Remotely Login to Windows 10 Virtual Machine
- Download and Install Wireshark and Open Command Prompt
- Observe traffic on ICMP, SSH, DHCP, DNS, RDP

<h2>Actions and Observations</h2>

<h2>Create Windows 10 and Ubuntu Virtual Machines in Microsoft Azure</h2>
<p>
<img src="https://imgur.com/pxrfAke.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Inside of Microsoft Azure, create a Windows 10 and Ubuntu virtual machine. Ensure that each virtual machine has the same region, size, and virtual network and subnet in Microsoft Azure.
</p>
<br />
<h2>Review Topology in Network Watcher and login to Windows 10 on Remote Desktop</h2>
<p>
<img src="https://imgur.com/AHG98ZO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once each virtual machine is created, you can review Network Watcher to verify that both machines are under the same virtual network. Next, you can virtually login to the Windows 10 machine by selecting the public IP address. Go to Microsoft Azure --> Click on Virtual Machine --> Click on VM with Windows 10 --> Copy the Public IP address under the Overview tab.
</p>
<br />
<h2>Download and Install Wireshark and Open Command Prompt</h2>
<p>
<img src="https://imgur.com/1bzjijP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After logging in remotely, search for "WireShark" in a web browser and select Windows Installer 64-bit to download. Next, open the file and continue steps for installation.
</p>
<br />
<h2>Observe ICMP Traffic</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
<h2>Observe SSH Traffic</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
<h2>Observe DHCP Traffic</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
<h2>Observe DNS Traffic</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
<h2>Observe RDP Traffic</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
