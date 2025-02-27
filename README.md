<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, DNS, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Virtual Machines
- Wireshark to Observe Traffic
- Configure Network Security Groups

<h2>Actions and Observations</h2>

![image](https://github.com/user-attachments/assets/c2b5750d-e106-4731-87f3-e7220532c9f6)

<p>
Launch two virtual machines, a Windows 10 and a Linux Ubuntu Server. Make sure both are under the same resource group and virtual network. 
</p>
<br />

![image](https://github.com/user-attachments/assets/1ec8d4d6-b1de-4e76-a55f-0dc01aa5b738)

<p>
Install Wireshark and filter by ICMP to see traffic when pinging different IPs.
</p>
<br />

![image](https://github.com/user-attachments/assets/5bddc052-5294-4045-be45-97b178d63faa)

<p>
Non-stop ping the Linux Ubuntu VM by using the command "ping -t (IP Address or Domain)". In the network settings for the Linux Ubuntu VM go under Network Security Group to disable ICMP traffic.
</p>
<br />

![image](https://github.com/user-attachments/assets/e4161b96-cad9-454e-a73a-cfd6888d8d7f)

<p>
Back on the Windows 10 VM you'll notice on wireshark that a ping is sent but nothing is being replied back. Indicating that the security group added, succeeded in blocking the ICMP traffic.
</p>
<br />

![image](https://github.com/user-attachments/assets/2a76ab0a-f218-4580-b90e-92639a3451f3)

<p>
SSH traffic can also be observed by filtering Wireshark for SSH traffic only. You can SSH into the Lunix server by using the command "ssh usernam@private IP". From there you can enter commands (pwd, exit) to track data being transferred in Wireshark.
</p>
<br />

![image](https://github.com/user-attachments/assets/823183ed-98b6-4dc1-a289-8d9730777f7b)

<p>
Another protocol you can track is DNS traffic by filtering Wireshark by DNS traffic only. Enter a command like "nslookup google.com" to observe DNS traffic in Wireshark.
</p>
<br />
