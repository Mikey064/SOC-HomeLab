# Day 10: SSH Brute-forcing an Ubuntu Server

## Objective

TBA

### Skills Learned

- Brute-forcing techniques using multiple tools.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate attack signatures and patterns.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Kali Linux as the attacker machine
- Brute-frocing tools (Nmap script, Python script, Metasploit & Hydra) for carrying out the attack.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps

### 1. Python script brute-forcing
The script work by leveraging the usernames and passwords saved in the `passwords.csv` file , then it asks for the IP address of the host you're going to connect to and then it opens the file and works through the passwords. Threading was used to make multiple connections to speed things up. The script automatically accepts the public key of the server you're connecting to (because of this line of code `ssh_client.set_missing_host_key_policy(AutoAddPolicy())`). You only get to accept the public key once and the next time you try to connect, you'll only be asked for the password because some form of `trust`  has been established already. 

**Steps:**
1. First, we need to find out which ports are open and specifically we'll be looking at port 22 used by Secure Shell (SSH).  Nmap on Kali Linux can give us that information by running this command in the terminal `nmap <iprange/iaddress> -p 22 --open `. The command will provide information abut the status of SSH servers on the IP address.
2. Go to the GitHub link provided here (https://github.com/davidbombal/ssh_bruteforcing) to copy the Python script we'll be using.  In the terminal, create the script using the command `nano main.py`. This will open the nano text editor in which you paste the code you copied and do the same for passwords (paswords.csv) you copied as well. 
3. The directory should contain both the script and the password file. To execute the script, use the command `python3 main.py `, enter the target IP address.
4. The script runs and attempts to login  using different usernames and passwords located in the `passwords.csv` file. 
You can further expand the reach by adding more words and if possible slip in the correct username and password. The aim is to generate enough telemetry. The SSH server also tried to rate limit the brute-forcing but the script continued to make connections to the server and should some credentials were found in the process, a `credentials_found.txt` file will be created.

### 2. Using Nmap

### 3. Using Metasploit

### 4. Using Hydra

drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
