<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDP, DNS, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Windows and Linux virtual machines 
- Make sure both virtual machines are on the same subnet
- Download Wireshark
- Analyze your network using the sniffer

<h2>Actions and Observations</h2>

<p>
<img  width="746" alt="ping" src="https://github.com/user-attachments/assets/5ef21696-3184-4cb1-ad1b-a781c95acfc8"/>
</p>
<p>
 To begin this project you must first create a resource group within azure that has two virtual machines. The first being a windows vm and the second is a ubuntu 20.04 server. As you create these virtual machines, you must put both virtual machines within the same subnet. After you create these vm's you must download wireshark on your windows vm. Start packet capture within wireshark and filter out icmp traffic. Retrieve the private ip address of your ubuntu server and ping it using your command line tool. 
</p>
<br />

<p>
<img   width="742" alt="ssh" src="https://github.com/user-attachments/assets/e12f6fa1-34a3-4f6d-809c-e7b781fd7494"/>
</p>
<p>
After pinging the linux vm you can go to its firewall and disable in-bound traffic. Once you go back to the sniffer you will see that it is no longer recieving icmp traffic. After that experiment you can re-enable icmp traffic and end that capture. Then we will filter for ssh traffic, you will login to your linux server using ssh on your windows vm. 
</p>
<br />

<p>
<img width="739" alt="dhcp2" src="https://github.com/user-attachments/assets/70f9fcc9-9e9e-4dd3-a19d-9265fe759eff"
 />
</p>
<p>
The last objective is to inspect dhcp traffic, create a script within notes that has two commands(ipconfig/release and ipconfig/renew). Save the file with a .bat extension and run it. The result in whireshark should show your vm broadcasting, dhcp offering ip addresses, followed by a request and acknowledgment by dhcp. 
</p> 
<br />
