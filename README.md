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
Inside of Microsoft Azure, create a Windows 10 and Ubuntu virtual machine. Ensure that each virtual machine has the same region, size, resource group, and virtual network and subnet in Microsoft Azure.
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
<img src="https://imgur.com/wU4rB7V.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
After downloading and install Wireshark, open Wireshark and the Command Prompt. Next, filter "ICMP" in Wireshark and initiate a perpetual ping (ping -t) to the Ubuntu server by using it's private IP address. Toggle back to Microsoft Azure and select the virtual machine with Ubuntu and paste the private IP address in command prompt. Next observe the changes in Wireshark and you will see that the ping was successful.
</p>
<br />
<h2>Blocking ICMP Traffic in Microsoft Azure</h2>
<p>
<img src="https://imgur.com/76V2Ota.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Inside of Microsoft Azure, you can allow or deny incoming traffic to protocols. Next, go to the Ubunutu virtual machine --> select Networking --> Click on Add Inbound port --> Select the "ICMP" protocol --> select "Deny" --> click "Save"
</p>
<br />
<h2>Observing Blocked ICMP Traffic</h2>
<p>
<img src="https://imgur.com/2jU73tp.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, observe the changes in Wireshark and Command Prompt and you can see that the request timed out due to blocking the ICMP traffic to the Ubuntu server.
</p>
<br />
<h2>Re-Enable ICMP Traffic</h2>
<p>
<img src="https://imgur.com/ZKrvav7.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
You can go back to Microsoft Azure and re-enable ICMP traffic. Go to the Ubunutu virtual machine --> select Networking --> Click on ICMP under Networking --> Select the "ICMP" protocol --> select "Allow" --> click "Save". Go back to Wireshark and observe that the incoming traffic pinged successfully.
</p>
<br />
<h2>Observe SSH Traffic</h2>
<p>
<img src="https://imgur.com/A7TEPKV.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter traffic in Wireshark to SSH only and ping in Command Prompt by using "SSH and using the private IP address for the Ubuntu server. Type in the password created when initially setting up the Ubuntu account, type "yes", and observe the changes in Wireshark. We can see that both virtual machines are pinging back and forth by looking at the source and destination tabs listing the private IP addresses of both virtual machines. Exit the SSH connection by typing "Exit" in command prompt and pressing "enter"
</p>
<br />
<h2>Observe DHCP Traffic</h2>
<p>
<img src="https://imgur.com/l4yibXJ.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter in Wireshark for DHCP traffic only. Inside of command prompt try to issue a new IP address by entering "ipconfig /renew". In Wireshark, we can see that the IP address still links to the Windows 10 original private IP address.
</p>
<br />
<h2>Observe DNS Traffic</h2>
<p>
<img src="https://imgur.com/oAkJxh4.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter in Wireshark for DNS traffic only. In command prompt, use "nslookup" to review the IP address of disney.com. In Wireshark, we can review what the IP address is for Disney.com and see where the source is pinged from the private IP address of the Windows 10 Virtual Machine.
</p>
<br />
<h2>Observe DNS Traffic Continued</h2>
<p>
<img src="https://imgur.com/NGDZ6K5.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter in Wireshark for DNS traffic only. In command prompt, use "nslookup" to review the IP address of google.com. In Wireshark, we can review what the IP address is for google.com and see where the source is pinged from the private IP address of the Windows 10 Virtual Machine.
</p>
<br />
<h2>Observe RDP Traffic</h2>
<p>
<img src="https://imgur.com/SINJZGy.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter in Wireshark for RDP traffic only by using "tcp.port == 3389". Inside of Wireshark, we can see that the traffic is continuously spamming due to the RDP protocol showing live data from one computer to another. RDP traffic is always transmitted.
</p>
<br />
