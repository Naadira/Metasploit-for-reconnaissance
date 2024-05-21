# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/ede62393-559b-4af8-8713-49c30eedd356)

Invoke msfconsole:
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/0a4a11eb-e357-4e61-af68-cf596f15c278)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/f164aa64-01f3-4ae8-bb09-13c0f211f69e)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/75f1ae7f-bc7f-4692-804c-3e2b2a91417a)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later. scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/c5819eab-c0ff-4d52-a022-97b081e29705)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/b09cd44e-043a-4466-a535-215565cb09ff)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/70281cb0-5790-42f5-9345-401218bb172f)

The info command provides information regarding a module or platform 
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/69a73bf5-195b-4277-a5bc-a77d64e18405)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/79a7bab7-1f4d-4201-9d26-8eef8c3a073f)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/006bf2d8-7845-4f42-84fb-aaf181d4387a)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/0f5c8297-863c-460e-9955-9a83fe07ce63)

Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/53f9c707-8efd-42f2-99ce-223c35a0ed4e)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/f65dc414-c3de-4c4c-8b01-40688bd2423a)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/Naadira/Metasploit-for-reconnaissance/assets/128135126/08031caf-64cb-4d19-9588-133858ac919a)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
