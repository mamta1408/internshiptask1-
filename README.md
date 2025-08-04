 Cyber Security Internship - Task 1: Nmap Port Scanning
 
 
 Objective:
   To discover open ports on device in your local network to understand exposure 
  
  Tools Used

    Nmap – for network scanning
    Wireshark – for packet capture and traffic analysis

 Commands Used

    root@DESKTOP-DIH67TP:~# ifconfig
   
    root@DESKTOP-DIH67TP:~# nmap -sS 172.20.16.0/20

 Summary of Active Hosts in 172.20.16.0/20:

    Total IPs scanned: 4096

    Live hosts found: 2

    Time taken: ~17.77 seconds

 Detailed Results:
  1. Host: DESKTOP-DIH67TP.mshome.net (IP: 172.20.16.1)

    Status: Host is up

    MAC Address: 00:15:5D:97:DE:EE (Microsoft Hyper-V Virtual Adapter)

    Open Ports:

        3306/tcp → MySQL

    Other Ports: 999 filtered (possibly due to firewall )

     Wireshark Packet Analysis 

         Captured network packets on port 9100 using Wireshark:
            wireshark file attached 
              nmap.pcapng



#  Risk Analysis Report

| Port  | Service   | Risk Description                         |
|-------|-----------|-------------------------------------------|
| 21    | FTP       | Unencrypted login credentials             |
| 22    | SSH       | Vulnerable to brute-force attacks         |
| 23    | Telnet    | Very insecure, sends data in plain text   |
| 80    | HTTP      | Susceptible to web-based attacks          |
| 9100  | JetDirect | Can be exploited to spam or flood printers|

##  Recommendation

Open or unused ports should be:
- Closed if not required.
- Protected by firewalls.
- Monitored regularly.
- Access-controlled (e.g., using IP whitelisting).

 Findings & Conclusion

I found port 9100 open on a local device, which is commonly used for printers. If this port is not actively needed, it becomes a potential entry point for attackers.

Open ports like 21 (FTP) and 23 (Telnet) are especially dangerous as they transmit data unencrypted and are frequent targets of cyberattacks.



