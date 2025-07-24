# log-analysis-lab

## Issue 1

**Log Entries:** 

```
2023-02-17 09:36:07 192.168.1.61 217.23.2.15 TCP 21 Allow 3629
2023-02-17 09:36:15 192.168.1.61 141.98.10.195 TCP 21 Allow 2745
```
**Description of log entries:** Outbound FTP traffic is risky; attackers often use brute force through FTP.


## Issue 2
**Log Entries:**
```
2023-02-17 09:39:03 192.168.1.19 40.94.31.197 TCP 1433 Allow 37419  
2023-02-17 09:39:08 192.168.1.19 40.94.25.38 TCP 1433 Allow 32780  
2023-02-17 09:39:11 192.168.1.19 40.94.28.182 TCP 1433 Allow 41935
```
**Description of log entries:** SQL server traffic to external IPs Port 443

## Issue 3
**Log Entries:**
``` 
2023-02-17 09:35:56 172.17.99.132 205.185.216.10 UDP 443 Deny 6340  
2023-02-17 09:37:04–09:37:14 192.168.1.229 multiple UDP 443 Allow 6273  
2023-02-17 09:37:38–09:37:52 192.168.1.44 UDP 443 multiple  
2023-02-17 09:38:01–09:38:13 192.168.1.194 UDP 443 multiple
```
**Description of log entries:** High Volume UDP 443 Excessive or unexpected use of UDP over port 443 may indicate Quick UDP Internet Connections evasion or C2 activity.

## Issue 4
**Log Entries:**
```
2023-02-17 09:37:17 192.168.1.150 162.159.134.234 TCP 443 Allow 70136  
2023-02-17 09:37:27 192.168.1.150 162.159.130.233 TCP 443 Allow 72643
```
**Description of log entries:** High-Byte HTTPS Traffic to Single External IP

## Issue 5
**Log Entries:**
```
2023-02-17 09:38:24–09:38:53 192.168.1.72 111.221.29.254 TCP 443 Deny 0
```
**Description of log entries:** Repeated failed outbound attempts may indicate malware persistence or misconfiguration.

## Issue 6
**Log Entries:**
```
2023-02-17 09:34:03 192.168.1.27 45.137.80.15 TCP 41284 Deny 48  
2023-02-17 09:36:44 192.168.1.80 185.151.204.30 TCP 48127 Deny 48
```
**Description of log entries:** Denied High Port Access Attempt - Attempted connections to uncommon high-numbered ports often used in scanning or Peer to Peer activity.

## Issue 7
**Log Entries:**
```
2023-02-17 09:37:04–09:37:14 192.168.1.229 multicast/broadcast to port 443  
239.255.255.250, 255.255.255.255, 192.168.1.255, etc.
```
**Description of log entries:** Port 443 is typically TCP and unicast. Multicast User Data Protocol traffic here is highly suspicious.

## Issue 8 
**Log Entries:**
```
2023-02-17 09:34:14 192.168.1.49 216.109.119.63 TCP 25 Allow 7421
```
**Description of log entries:** Use of Port 25 SMTP not recommeded from Workstations. Workstations typically don’t send email via SMTP. Could indicate spambot or script.

## Issue 9
**Log Entries:**
```
2023-02-17 09:35:04 192.168.1.161 204.141.42.39 UDP 5060 Allow 5720
```
**Description of log entries:** VoIP traffic not typical on standard workstations unless Session Initiation Protocol client is in use.

## Issue 10
**Log Entries:**
```
2023-02-17 09:33:57 192.168.1.33 116.132.235.228 ICMP 0 Allow 98  
2023-02-17 09:35:30 192.168.1.34 35.186.224.47 ICMP 0 Allow 98
```
**Description of log entries:** Outbound ICMP could be benign (ping), or a sign of scanning/activity detection.