<h1>Installing a Core Linux Operating System on a server</h1>


<h2>Description</h2>
Network security best practice mandates that Windows systems and Linux systems should be installed on a secure network subnet and updated (patched) using trusted sources. Only the minimum services required should be installed, and unneeded services should be disabled. While this axiom remains true, it can be very difficult to find the right balance between a functional system and a secure system.

 

On UNIX and Linux systems, program dependencies can make it very hard for new administrators to find this balance. Many administrators simply install GUI-driven servers with standard services (SMTP, HTTP, DNS, X-Window, etc.) and put their faith in the firewall to keep attackers out.

 

The foundation of host-based security starts with the installation of the operating system (OS). Contrary to popular opinion, there is no such thing as a secure operating system, but in this lab, I learned how to install the Linux CentOS operating system in a secure manner. I created a new virtual machine, partitioned the hard drive, and installed the Linux operating system. I also created a non-root user account and verified that key services are (or are not) running.
<br />


<h2>Network Topology</h2>

- <b>vWorkstation (Windows: Server 2016)</b>
- ![image](https://github.com/user-attachments/assets/510d36ce-60c1-4f6f-8bc7-ccdc96cbb324)



<h2>Lab walk-through:</h2>


Created a virtual machine using Oracle VM VirtualBox <br/>

  ![image](https://github.com/user-attachments/assets/1ca01d66-30fc-40c6-8135-041bd32f3a9a)

<br />
<br />
Partitioned the drive and installed CentOS  <br/>
 
  ![image](https://github.com/user-attachments/assets/9e5691b9-6a8c-4ad6-83cf-2b22295e99a6)

<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
