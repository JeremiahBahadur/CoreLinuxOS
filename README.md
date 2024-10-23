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
In Linux operating systems, the /etc/passwd file is a text-based database of information about users who may log into the system or other operating system identities that own running processes. The /etc/passwd file is a text file with one record per line, each describing a user account. Each record consists of seven fields separated by colons. An example record may be:

 

jsmith:x:1001:1000:Joe Smith,Room 1007,(234)555-8910,(234)555-0044,email:/home/jsmith:/bin/sh

 

The ordering of the records within the file is generally unimportant, but in this example, the second field stores information used to validate a user’s password. Rather than using the actual password in a location that is so widely known, best practice usually sets this field to “x” (or some other indicator) as shown in this example. The actual password information is stored in a separate shadow password file. A common practice for deactivating an account to prevent it being used is to set the field to an asterisk (*).

<br />

Configured networking in the vi Editor with the elevated privileges of the sudo command<br/>

   ![image](https://github.com/user-attachments/assets/ce10b311-28c3-41fe-93cf-74fa1acc03fb)
<br />
<br />
Used the sestatus command to verify that SELinux (Security Enhanced Linux) is enabled and the current mode is enforcing.

Security Enhanced Linux is a mandatory access control system designed to help a Linux system adhere to the principle of least privilege.
<br />
<br />
Used the iptables -L command to ensure that the iptables firewall was running and the ntpd -q command to set the Network Time Protocol (NTP) <br/>

![image](https://github.com/user-attachments/assets/e7fc7fac-93e1-48af-a551-b7f195e7c106)

<br />
System time must be synchronized with other network servers and/or an atomic-time server on the Internet for consistent operations and valid chronology of events. Synchronized timestamps aid in searching logs for errors and potential security breaches. Certain network services also rely on synchronized system clocks to verify security and other network tokens across the network. If the clocks are out of sync, many services may malfunction. Network Time Protocol (NTP) is a protocol for clock synchronization between computers on a network.

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
