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
<img src="https://i.imgur.com/dUQ7758.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/kY2II2Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/S4xSu8g.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p
 
 - First, you going to create your Resource Group. 
   - If you don't know how to click [here](https://github.com/haleypruittcc/ResourcegroupandHelloworld) before you continue with this section. 
- Second, type " Virtual Mahcine" on the top of the search bar and click on "Create".
- Choose you're existing "Resource Group", then choose the name of chose for your Virtual Mahcine.
- Then choose your region in your area, next you're going select "Windows 10 Pro" on Image.
- Next, select what size of your performance on you're remote desktop windows. Note: Make sure you look at your prices before you select so you won't use all your free credits up.
- Next, you're going to create your username and password by chose.
- Finally, Click on " Review and Create" and click on " Create". 
- Now you're going to do the repeat the same step but change your "Image" to "Ubuntu Server 20.04 LTS" on your second Virtaul Machine.
   
 🎉Congratulations! You have created your first Virtual Mahcine within Azure!🎉
  
  <h3>Step 2: Observe the Vitual Machine within Network Watcher </h3>
 
 <p>
<img src="https://i.imgur.com/VnWx9JU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <p>
<img src="https://i.imgur.com/r7zi1RS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 <p>
<img src="https://i.imgur.com/Le7DBDC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 <p>
<img src="https://i.imgur.com/dNlxcoG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 <p>
<img src="https://i.imgur.com/6L3TIYR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- First, type "Network Watcher" on the search bar on top and click on "Topology" and observe the Virtual Machines connected.
  - Note: If the error said " No Network watcher present in this subscription" on the topology then follow this instrictions.
- Click on " Overview" and click on three dots on the "NetworkWatcher_eastus".
- Next, click on "Move" besides the Resource Group.
- Then, select the resource group you created on the last step and click on "Next", after its checking the resources to make sure it can move then click "Move".
- Finally, after the resources move to the subscription go back to the Network Watcher Topology and observe the connections traffic .

   
   <h3>Step 3: Observe the ICMP Traffic </h3>  
    
    <p>
<img src="https://i.imgur.com/BfcH3SL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 

<img src="https://i.imgur.com/0sLSQo7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

 
<img src="https://i.imgur.com/mvFeK8n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
<img src="https://i.imgur.com/zHRggSD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 <img src="https://i.imgur.com/ocb8ORy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 <img src="https://i.imgur.com/dcH6F6j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 
 <img src="https://i.imgur.com/bbDWVVB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

 <img src="https://i.imgur.com/xBRWaJa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 
 <img src="https://i.imgur.com/3Vqnzk8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 <img src="https://i.imgur.com/vHWZ1ri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 
 

 
- First, go to your VM01 and copy the pubic IP address. 
- Open your "Remote Desktop" on your computer and paste your public IP address and click "Connect".
- Then, type in  the sames username and password you create earlier in the last step on your VM01.
- Next, Open your Chrome or Internet browser in your remote desktop and type "Wireshark 64 bite" and install it.
- Open "Wireshark" and filter on the top bar ICMP traffic only.
- Go back to your orginal computer and go to your VMO2 copy or remember the private IP address.
- Go back to your VMO1 remote desktop and open your command line attempt to ping it. Example: "ping 10.0.0.5" 
   - Observe ping requests and replies within Wireshark.
- Now open your Powershell and attempt to ping a public website. Example:"ping www.google.com -4) 
- Next ping your VM02  private IP address for the non-stop traffic. Example " ping 10.0.0.5 -t"
  - Observe the traffic in Wireshark .
- Now we going to initiate a perpetual/non-stop ping from VM01 to VM02 
- First, go back to your orignal computer and open Network Security Group by going to your VM02 and click on "Networking" and click on " Add inbound port rule".
- Second, Select "Any" on source > Select "Any" on destination > Select "Custom" on service > Select "ICMP" on protcol > Select "Deny" on action > Type "210" on priority > on name type "Deny_ICMP_Ping_From_Anywhere" > Now click "Add".
 - Now go back to your VM01 remote desktop and observe the ICMP traffic in Wireshark and the commmand line ping activity.
- Go back to your orginal computer and re-eable ICMP traffic in your VM02 Network Security Group by click "Allow" and refresh it.
- Go back to your VM01 and observe the ICMP traffic in Wireshark and the commmand ling ping activity
- To stop ping activity press control key + c .
 
 
 <h3>Step 4: Observe the SSH Traffic </h3> 
 
 <img src="https://i.imgur.com/vQpE5Hy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
 
- First, go to the Wireshark in VM01 and refresh and filter "SSH" traffic only.
- Second, go to your Powershell and type ssh your username @ VM02 private IP address and press enter. 
  - For Example:"ssh hpruittcc@10.0.0.5"
- When the question pop up on the command to be continue connecting , type "yes" and press eneter.
- Next, it going to ask for the your password, the password is the same one your created in your VM02, enter your password and press enter.
  - Note: When you enter your password it won't show up so please enter your password correctly.
- Now you're are in VM02. Type command (ls,pwd,etc) into the linux (VM02) SSH connection 
  - Observe SSH traffic spam in Wireshark.
- Finally, exit the SSH connection by typing "exit" and press enter.
 
 
 <h3>Step 5: Observe the DHCP Traffic </h3> 
 
 <p>
<img src=https://i.imgur.com/UhmwCJg.png"" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
- First, go back in Wireshark and refresh , filter "DHCP" traffic only.
- Next, attempt to issue your VM a new IP address from the command line , type (ipconfig/renew)
  - Obsereve the DHCP traffic appearing in Wireshark.
   
   <h3>Step 6: Observe the DNS Traffic </h3>
  
   <p>
<img src="https://i.imgur.com/4ZxpDFs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

- First, go back to Wireshark and refresh, filter for "DNS" traffic only.
- Second, go to the commmand line and type "nslookup www.google.com" or "nslookup www.disney.com" to see what are their IP adresses are.
  - Obserev the DNS traffic being show in Wireshark.
   
  <h3>Step 7: Observe the RDP Traffic </h3> 
  
   
   <p>
<img src="https://i.imgur.com/HoQjS1n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
- First, back in Wireshark filter (tcp.port==3389) for RDP traffic only and press enter.
  - Question:  Before you press enetr , Will this traffic will spam non- stop or go blank or etc? 
   - Observe the immadiate non-stop spam of traffic, because the RDP (protocol) is constantly showing you a live stream from one computer to another , therefore traffic is always being transmitted.
    
    
  🎉Finally! You are done experiences performing activites on the Newtwork!🎉
    
   Make sure after you done delete your Resource Groups. If you don't know how to click [here](https://github.com/haleypruittcc/ResourcegroupandHelloworld)

