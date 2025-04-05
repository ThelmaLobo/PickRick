h1> Pick Rick </h1>

<h2>Description</h2>
<img src="https://i.imgur.com/BTqwPda.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />


<h2>Environments Used </h2>

- <b> Try Hack Me VM </b>
- <b>  </b> 

<h2>Program walk-through:</h2>

<p align="center">
I am using the Try Hack Me VM to perform this CTF. Let's check the version of this machine as shown below. This is just for our information  : <br/>
  
<img src="https://i.imgur.com/9PcZZPV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let us check the IP address of this machine. Our IP address is 10.10.119.232. We also have the target machine whose IP address is 10.10.165.99. We can see both the machines are on the subnet. We can also ping the victim machine to check if the connection can be established or not. In our case, we are able to see that it is working  : <br/>
<img src="https://i.imgur.com/xFGhhiP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/fBHnmes.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/3NnF8hI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap. We can see that two ports are open on this machine which port 80 (for http) and port 22 (port 22) : <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
As port 22 (http) is open. Lets go on to IP 10.10.165.99. We can see the web server and from that we need to understand how we can solve this challenge further. We can see this that is a web server which usually contains html files which may be hosted in remote machine.Therefore, we need to see the source code of the page and check if we find somehing fruitful there  : <br/>
  
<img src="https://i.imgur.com/QUModA9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
We can see the comments in green. This seems to be username as per the given comments. It might help in SSH as we already know that port 22 is open on the target machine. We will be inputing the username in there. However,we will needing the password. There are numerous steps to get the password by performing brute force attack.  : <br/>
<img src="https://imgur.com/iuSYzGh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
To perform enumeration, we did directory bruteforcing. We will be trying common directory brute forcing names such as login, admin, secret, .htpaswd,robots.txt. We also use Gobuster tool for performing such brute forcing. One of the common file we know is robots.txt. As we can see there some information given that seems like it might a password. It will help while performing the SSH - <br/>
  
<img src="https://i.imgur.com/RbCWfff.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/YrcBCNQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/xhNvEPK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now let's begin. We need to do port scanning on the target machine. This will help us understand which ports, services are open. This can help us perform enumeration on them. There are multiple ways to do that like running scripts, using nmap which is one of the most essential steps to do. We will be using this command - 
nmap -T5 -p- -vv -sV  10.10.165.99 -oA nmap: <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
