# Warm-up schedule

One set per class meeting. The page opens the set whose date matches today. Add the day id to the link (for example `#d05`) to open a specific set.

| Day | Date | Work order | Linux commands | PowerShell commands |
|---|---|---|---|---|
| d01 | 2026-10-28 | Computer Lab Disconnected | `pwd`<br>`ls`<br>`cd blueland`<br>`cd ..`<br>`mkdir cleared`<br>`ip addr`<br>`ip route`<br>`ping -c 4 192.168.50.1`<br>`ping -c 4 1.1.1.1`<br>`nslookup example.com`<br>`nslookup example.com 1.1.1.1` | `pwd`<br>`ls`<br>`cd blueland`<br>`cd ..`<br>`mkdir cleared`<br>`ipconfig /all`<br>`ping 192.168.50.1`<br>`ping 1.1.1.1`<br>`nslookup example.com`<br>`nslookup example.com 1.1.1.1` |
| d02 | 2026-10-30 | Who is on this machine? (kali) | `whoami`<br>`id`<br>`ip link`<br>`cat /etc/passwd`<br>`grep bash /etc/passwd`<br>`id bhelper` | `whoami`<br>`net user`<br>`getmac`<br>`net user bhelper`<br>`Get-LocalGroupMember Administrators` |
| d03 | 2026-11-02 | Who has this address? (kali) | `ip neigh`<br>`ping -c 1 192.168.50.1`<br>`ip neigh`<br>`ip link`<br>`ip route` | `arp -a`<br>`ping 192.168.50.1`<br>`arp -a`<br>`getmac` |
| d04 | 2026-11-04 | Audit the lab addresses (kali) | `ip -br addr`<br>`ip route`<br>`ping -c 4 192.168.50.1`<br>`hostname`<br>`nslookup example.com` | `ipconfig`<br>`hostname`<br>`ipconfig /all \| findstr DNS`<br>`ping 192.168.50.1` |
| d05 | 2026-11-06 | What is installed, and is it current? (cp-ubuntu) | `hostname`<br>`uname -a`<br>`cat /etc/os-release`<br>`dpkg -l \| grep ssh`<br>`ip link` | `hostname`<br>`Get-NetAdapter`<br>`Get-HotFix`<br>`ipconfig /all \| findstr DNS` |
| d06 | 2026-11-09 | Static or dynamic? (kali) | `pwd`<br>`ls`<br>`cd blueland`<br>`cd ..`<br>`mkdir cleared`<br>`ip addr` | `pwd`<br>`ls`<br>`cd blueland`<br>`cd ..`<br>`mkdir cleared`<br>`ipconfig /all` |
| d07 | 2026-11-11 | Build the as-built record (kali) | `hostname`<br>`uname -a`<br>`ip -br addr`<br>`ip link`<br>`ip route` | `hostname`<br>`ipconfig /all`<br>`getmac`<br>`ping 192.168.50.1` |
| d08 | 2026-11-13 | Share it, lock it down (cp-ubuntu) | `ls -l`<br>`chmod 750 media`<br>`ls -l`<br>`sudo ufw status`<br>`sudo ufw enable`<br>`sudo ufw allow 445/tcp`<br>`sudo ufw status` | `icacls media`<br>`Get-SmbShare`<br>`Get-NetFirewallProfile \| Select-Object Name, Enabled`<br>`Test-NetConnection 192.168.50.20 -Port 445` |
| d09 | 2026-11-16 | Catch the AI (cp-ubuntu) | `ls -l`<br>`chmod 750 media`<br>`ls -l`<br>`ip route` | `icacls media`<br>`icacls media /remove Everyone`<br>`icacls media` |
| d10 | 2026-11-18 | Least-privilege audit (cp-ubuntu) | `ls -l`<br>`chmod o-w notes.txt`<br>`ls -l`<br>`id` | `icacls media`<br>`Get-LocalGroupMember Administrators` |
| d11 | 2026-11-20 | What is listening? (cp-ubuntu) | `ss -tuln`<br>`ps aux \| grep vsftpd`<br>`ss -tuln > ports.txt`<br>`sudo systemctl disable --now vsftpd`<br>`ss -tuln` | `netstat -ano`<br>`Get-NetTCPConnection -State Listen`<br>`Stop-Service ftpsvc`<br>`Get-Service ftpsvc` |
| d12 | 2026-11-30 | Speed run (kali) | `pwd`<br>`ls`<br>`cd blueland`<br>`cd ..`<br>`mkdir cleared`<br>`ip route` | `pwd`<br>`ls`<br>`cd blueland`<br>`cd ..`<br>`mkdir cleared` |
| d13 | 2026-12-02 | Computer Lab Disconnected, full mission (kali) | `ip addr`<br>`ip route`<br>`ping -c 4 192.168.50.1`<br>`ping -c 2 127.0.0.1`<br>`sudo dhclient -v eth0` | `ipconfig /all`<br>`ping 192.168.50.1`<br>`ping 127.0.0.1`<br>`ipconfig /renew` |
| d14 | 2026-12-04 | Read the evidence (cp-ubuntu) | `tail -n 5 /var/log/auth.log`<br>`grep "Failed password" /var/log/auth.log`<br>`grep -c "Failed password" /var/log/auth.log`<br>`wc -l /var/log/auth.log` | `Get-Content C:\Logs\security.log -Tail 5`<br>`Select-String Failed C:\Logs\security.log`<br>`Select-String Failed C:\Logs\security.log \| Measure-Object` |
| d15 | 2026-12-07 | Follow the trail (cp-ubuntu) | `find / -name incident.log`<br>`cat /home/student/evidence/incident.log`<br>`grep "Failed password" /var/log/auth.log`<br>`history` | `Get-ChildItem C:\ -Recurse -Filter incident.log`<br>`Get-Content C:\Users\student\evidence\incident.log`<br>`Select-String Failed C:\Logs\security.log`<br>`Get-History` |
| d16 | 2026-12-09 | Review stations (cp-ubuntu) | `id`<br>`ip route`<br>`ping -c 4 192.168.50.1`<br>`nslookup example.com`<br>`ss -tuln`<br>`ls -l` | `whoami`<br>`ipconfig /all`<br>`ping 192.168.50.1`<br>`nslookup example.com`<br>`netstat -ano` |
| d17 | 2026-12-11 | No warm-up today. It is Unit 2 test day. Good luck. | - | - |
| d18 | 2026-12-15 | Final review (cp-ubuntu) | `pwd`<br>`ls -l`<br>`ip route`<br>`ping -c 4 192.168.50.1`<br>`nslookup example.com`<br>`ss -tuln`<br>`grep "Failed password" /var/log/auth.log` | `pwd`<br>`ipconfig /all`<br>`ping 192.168.50.1`<br>`nslookup example.com`<br>`netstat -ano`<br>`Select-String Failed C:\Logs\security.log` |

`kali` is the Kali station prompt and `cp-ubuntu` is the CyberPatriot practice image prompt.
