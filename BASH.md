### Question 16
--Design a script that detects the existence of directory: $HOME/.ssh
-Upon successful detection, copies any and all files from within the directory $HOME/.ssh to directory $HOME/SSH and produce no output. You will need to create $HOME/SSH.
-Upon un-successful detection, displays the error message "Run ssh-keygen" to the user.

dir=$HOME/.ssh
if [[ -d "${dir[$i]}" ]]; then
cp -a $HOME/.ssh $HOME/SSH
else
echo Run ssh-keygen
fi

if [[ -d ~HOME/.ssh ]]; then
cp ~/.ssh/* ~/SSH/
else
echo "Run ssh-keygen"
fi

### Question 17
--Write a script that determines your default gateway ip address. Assign that address to a variable using command substitution.
-Have your script determine the absolute path of the ping application. Assign the absolute path to a variable using command substitution. HINT: man which
-Have your script send six ping packets to your default gateway, utilizing the path discovered in the previous step, and assign the response to a variable using command substitution.
-Evaluate the response as being either successful or failure, and print an appropriate message to the screen

A=$( ip route | cut -d" " -f3 | head -1 )
B=$( which ping )
C=$( $B -c 6 $A | grep '6 received,' | cut -d" " -f4-5)
if [[ $C == '6 received,' ]]; then
   echo successful
else
   echo failure
fi

one=$(ip route | egrep default | cut -d' ' -f3)
two=$(which ping)
if [[ "6 received" == $($two -c 6 $one | grep -Eo "6 received") ]]; then
echo successful
else
   echo failure
fi

### Question 18
Create the following files in a new directory you create $HOME/ZIP:
file1 will contain the md5sum of the text 12345
file2 will contain the md5sum of the text 6789
file3 will contain the md5sum of the text abcdef
Create a zip file containing the three files above, without being stored inside a directory in the zip file. Name the zip file $HOME/ZIP/file.zip
HINT: "Junk" the paths
Utilize tar on $HOME/ZIP/file.zip to archive it into a file called $HOME/ZIP/file.tar.gz which should not include directories. Use the gzip option in tar, DO NOT use a seperate gzip binary.
HINT: You might need an option to change directories first.

mkdir $HOME/ZIP
echo 12345 | md5sum | cut -d" " -f1 > $HOME/ZIP/file1
echo 6789 | md5sum | cut -d" " -f1 > $HOME/ZIP/file2
echo abcdef | md5sum | cut -d" " -f1 > $HOME/ZIP/file3
zip -j $HOME/ZIP/file.zip $HOME/ZIP/file{1..3}
tar -czf $HOME/ZIP/file.tar.gz -C $HOME/ZIP/ file.zip
E??????

