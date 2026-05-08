# VA-LAB-week-8-9
Challenges

OS and Software used:
Kali Linux
Metasploitable 2
Windows 10 and Zenmap GUI

1. Challenge 1: <img width="782" height="534" alt="image" src="https://github.com/user-attachments/assets/6df15f93-ea7e-4209-9976-74a1571a9397" />
NetBIOS Enumeration
Action: Executed nbtstat -a <target_IP> to query the NetBIOS name table.
Result: Identified the hostname (<00> UNIQUE), the domain/workgroup (<00> GROUP), and confirmed that SMB was enabled via the File Server service code (<20>).

2. Challenge 3: <img width="385" height="200" alt="image" src="https://github.com/user-attachments/assets/b400cb57-4193-4ac7-b239-c094015f4672" />
<img width="626" height="677" alt="image" src="https://github.com/user-attachments/assets/9989d3f8-91ee-4aa5-a0a0-86a97be87905" />
DNSRecords
Action: Used nslookup and dig to query public DNS records.  
Result: Successfully retrieved the IPv4 address (A record), IPv6 address (AAAA record), and identified the mail server (MX record) for the target domain.


3. Challenge 4: <img width="425" height="154" alt="image" src="https://github.com/user-attachments/assets/e1a1dc26-3015-42aa-88f3-15cf3434d803" />
SNMPWalk
Action: Ran snmpwalk -v1 -c public <IP> against port 161.  
Result: Leaked critical system information, including the system name (sysName), description (sysDescr), a list of network interfaces, and current system uptime.

4. Challenge 6: <img width="705" height="487" alt="image" src="https://github.com/user-attachments/assets/c3d551b7-d9d2-4235-a8df-c06382af20fc" />
Anonymous LDAP Query
Action: Performed an anonymous search using ldapsearch on port 389.  
Result: Confirmed if the server allowed anonymous binds, which typically returns sensitive user objects, descriptions, and CN entries without requiring credentials

5. Challenge 7:<img width="395" height="68" alt="image" src="https://github.com/user-attachments/assets/32853584-082b-4894-95f4-d3243187eb32" />
SMTP VRFY/EXPN
Action: Connected to port 25 via nc and issued VRFY and EXPN commands.  
Result: Identified valid usernames on the server; a "weak" server responds with a 250 code indicating the user exists.

6. Challenge 9: <img width="180" height="47" alt="image" src="https://github.com/user-attachments/assets/328964de-b131-4a29-a8a6-35aeed763379" />
FTP Banner
Action: Used nc <IP> 21 to capture the service banner.  
Result: Obtained the specific software version (e.g., vsFTPd 2.3.4), which is essential for identifying known vulnerabilities.

7. Challenge 10: <img width="263" height="160" alt="image" src="https://github.com/user-attachments/assets/345b4002-ecc8-4eb7-8fb9-c37b564fa304" />
Anonymous FTP Login
Action: Attempted to log in to the FTP service using the username anonymous.  
Result: Verified if the server allows unauthenticated access and listed readable directories available to the public.

8. Challenge 11: <img width="492" height="283" alt="image" src="https://github.com/user-attachments/assets/e6db8833-6cac-44a3-912f-ce0729b7e8ed" />
SMB NSE Enumeration
Action: Ran Nmap scripts (smb-os-discovery, smb-enum-users) on port 445.  
Result: Discovered the operating system (Windows/Samba version) and generated a list of valid local users like "Administrator" or "Guest".

9. Challenge 12: <img width="770" height="683" alt="image" src="https://github.com/user-attachments/assets/07e63ed9-85bc-4eb3-a2b5-51f84126fa89" />
Enum4Linux
Action: Executed enum4linux -a <IP> for deep SMB profiling.  
Result: Extracted a comprehensive profile including users, groups, share names (like ADMIN$), and further NetBIOS information.

10. Challenge 16: <img width="892" height="453" alt="image" src="https://github.com/user-attachments/assets/257e641b-9f44-408d-b30d-075afe7e9caa" />
Version detection
Action: Performed an Nmap service scan using the -sV flag.  
Result: Identified exact version numbers for all open services, such as SSH, HTTP, FTP, and SQL, facilitating targeted exploit research.









