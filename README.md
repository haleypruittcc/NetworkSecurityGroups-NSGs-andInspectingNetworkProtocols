<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
When virtual machines are created, they are given an IP address. As they boot up, each virtual machine (VM) that you deploy into a virtual network or subnet receives an IP address. In this tutorial, we use Wireshark to monitor a variety of network traffic going to and coming from Azure Virtual Machines and we practice using Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04



<h2>Configuration Steps</h2>

<h3>Step 1: Create a Virtual Machine </h3>

<p>
<img src="https://i.imgur.com/MJOpWkB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/h8BZEzi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/2ny0xyg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p
 
 - First, you going to create your Resource Group. If you don't know how to click [here](https://github.com/haleypruittcc/ResourcegroupandHelloworld) before you continue with this section. 
- Next, type "Virtual Machine" on top in the search and click on "Create"
- Choose your existing "Resource Group", then choose the name of chose for your Virtual Mahcine.
- Then choose your region in your area, next your going select "Windows 10 Pro" on Image.
- Next, your going to create your username and password by chose.
- Finally, Click on " Review and Create" and 
   
     
 

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
