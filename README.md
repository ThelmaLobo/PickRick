h1>Pick Rick </h1>

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
To perform enumeration, we did directory bruteforcing. We will be trying common directory brute forcing names such as login, admin, secret, .htpaswd,robots.txt. We can also use Gobuster, dirb tools for performing such brute forcing. As we can after trying manual brute forcing, we got some information from /robots.txt. It does look like it can be a passwprd which we can use to do ssh. As we already know from our port scanning, that port 22 was open. We will have to keep trying until we find some page which lets enter the username or password where will should be able to find the flag. the login.php seemed to work.As we can see, it is asking us to enter the username and password - <br/>
  
<img src="https://i.imgur.com/RbCWfff.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/YrcBCNQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/xhNvEPK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/8fArheI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Wf9tEaB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
After perfroming manual brute-forcing we managed to find the below page. 
<img src="https://i.imgur.com/C0j7Ivt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br />
<p align="center">
Here, we will be inputting the password discovered from the /robots.txt file and username discovered from web page as below <br/>
  
<img src="https://i.imgur.com/A4NThZI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ViaD7sN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Here we can view several folders such as Commands, Potions, Creatures, Potions and Beth Clone Notes. We tried going into these folders but couldnt find anyhting that would help us find the flag. However, we just have the Command Prompt. One attack we can perform is doing Remote Code Execution : <br/>
  
<img src="https://i.imgur.com/8EXKJaJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
We will do ls. After doing we can view some files : <br/>
  
<img src="https://i.imgur.com/1CbAmRt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br />
<p align="center">
We used cat command. However, it is disabled. Now we need to think what other commands can be used to perform this task i.e. read the contents of the file. There are different types of commands such as head, tail. Let's try them one by one and see what happens! : <br/>
<img src="https://i.imgur.com/jv2QZ0b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FsBCnw0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/u7AOUOh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/7CgoCnZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Those commands didnt work. After doing lot of google search. I came up with cat command alternatives and tried one command called the less command <br/>
  
<img src="https://i.imgur.com/43WAqK6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
After executing that command, we found the flag as below <br/>
  
<img src="https://i.imgur.com/E9zeDrc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
We need to search for other ingredients (flags) therefore we can try doing that using the same less command for other .txt files as below: <br/>
  
<img src="https://i.imgur.com/LTRj0hm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/HOCdT6f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
As per the above message we need to search other file systems to search for another flag. <br/>
  
<img src="https://i.imgur.com/V5Dxpri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Let's check our pwd now. This is our html directory where we store our apache files. Whenever we get access to any Linux system, we are always into home directory. We also need to check the home directory for gaining the information of users. We found two directories such as rick and ubuntu. We are mostly interested in the rick directory <br/>
  
<img src="https://i.imgur.com/YXxMrxb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/KADlmnT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
For doing we need to provide the absolute path i.e. ls /home/rick. Here we can see the name second ingredient. We need to see what is there inside this file.  <br/>
  
<img src="https://i.imgur.com/tikrFre.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/KjITjBg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br />
<p align="center">
To access the second ingredient file, we use less command as done previosuly. Here we found the second flag.  <br/>
  
<img src="https://i.imgur.com/hfI4R0M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/kxXvBVK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Now we need to search for the third ingredient. For lets see we can find anything in /root directory. 
  
<img src="https://i.imgur.com/7v666F1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
So, we found one text file called 3rd.txt. Lets see what's inside using less command <br/>
  
<img src="https://i.imgur.com/m9XLkao.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/SMFbdXg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
After giving sudo command i.e. we gave permissions for accessing the 3rd.txt file. We have captured the third ingredient as below <br/>
  
<img src="https://i.imgur.com/l6zYaqH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
The final output is as below -
<img src="https://i.imgur.com/TOzgfnd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


