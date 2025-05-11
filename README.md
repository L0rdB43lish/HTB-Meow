# Meow
Resolution of HackTheBox's machine "Meow".

Spawn machine IP: 10.129.112.23

To answer some of the questions:  

3. What service do we use to form our VPN connection into HTB labs?  
	`openvpn`

4. What tool do we use to test our connection to the target with an ICMP echo request?  
	`ping`

To verify connectivity with the target machine, I used the `ping` command, which sends ICMP echo requests. This is a simple and effective way to confirm that the target os reachable and responsive on the network.  
![image](https://github.com/L0rdB43lish/HTB-Meow/blob/33d909568646a528916c984d9d80835b98e6c371/Files/Captura%20de%20tela%202025-05-09%20174108.png)  

 5. What is the name of the most common tool for finding open ports on a target?  
	`nmap`

To identify which services were running on the target machine, I used `nmap`. It allows users to detect open ports, running services, versions, and even potential vulnerabilities.  
![image](https://github.com/L0rdB43lish/HTB-Meow/blob/33d909568646a528916c984d9d80835b98e6c371/Files/Captura%20de%20tela%202025-05-09%20174223.png)  

6. What service do we identify on port 23/tcp during our scans?  
	`telnet`

During the `nmap` scan, I discovered that the `telnet` service was running on port 23. I connected to the service using the `telnet` command, as shown in the screenshot below. The successful connection validated that the service was running and accepting connections, which posed a potential security risk due to the lack of encryption and authentication.  
![image](https://github.com/L0rdB43lish/HTB-Meow/blob/33d909568646a528916c984d9d80835b98e6c371/Files/Captura%20de%20tela%202025-05-09%20174614.png)  

7. What username is able to log into the target over telnet with a blank password?  
	`root`

I attempted to connect using default credentials. I discovered that the username `root` could successfully authenticate without a password, highlighting severe security misconfiguration.  
That granted immediate access to the system, allowing for further exploration. The screenshot bellow shows the successful login to the system.  
![image](https://github.com/L0rdB43lish/HTB-Meow/blob/33d909568646a528916c984d9d80835b98e6c371/Files/Captura%20de%20tela%202025-05-09%20174640.png)  

## Flag
While exploring the system, I was able to locate the `flag.txt` file. Executing the `cat` command, I was able to successfully display its contents and retrieve the flag.  
![image](https://github.com/L0rdB43lish/HTB-Meow/blob/33d909568646a528916c984d9d80835b98e6c371/Files/Captura%20de%20tela%202025-05-09%20174810.png)  

## What I Learned
Working through the "Meow" box helped me get hands-on with basic network enumaration and remote access. I used `nmap` to scan the target and found an open Telnet port - which stood out as a security risk. Being able to connect to it by using `root` with no password showed me how dangerous unauthenticated services can be, and the amount of damage one can do. From there, I explored the system and used `cat` to retrieve the flag. It was a simple challenge, but truly enjoyable and fun.
