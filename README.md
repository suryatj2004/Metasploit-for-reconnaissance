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
## OUTPUT:

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/e877bf40-30b5-4bfa-a82f-0f4aeac97dc5)

## OUTPUT:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/9fede203-c2a2-46e6-88cf-eaff0abc9cd4)

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/08c5d299-9093-4cb4-9a6c-a9ad01b0c450)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000 

## OUTPUT:

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/6eaf72e8-9bc7-49ff-92bc-744b8d626267)

nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/60c0f2bb-d3bb-4c7c-b57f-f8f4029d097d)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l 

## OUTPUT:

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/8c38c78d-4572-4fa8-baaa-1f389d948ac3)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform.

## OUTPUT:

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/eb506a5e-633d-489f-b3ef-64780c2af31a)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/3363d610-2ea2-4736-af90-ef6f8f7f448e)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/353d2a61-1ddc-4330-b396-70b8cd9a5b2f)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/69c364ff-4777-4c79-a71e-62ac675419af)

Use the set rhosts command to set the parameter and run the module, as follows: 

## Output:

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/d00f18eb-c440-481a-832a-8414c83c1bab)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/4b8a4d5a-38dd-420c-8a33-2c6444fd8a84)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/Catty12384/Metasploit-for-reconnaissance/assets/120629225/70b9ae92-d214-4fcf-8bed-4f00b12a7e89)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
