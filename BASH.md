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

## ERROR

mkdir $HOME/ZIP
echo 12345 | md5sum | cut -d" " -f1 > $HOME/ZIP/file1
echo 6789 | md5sum | cut -d" " -f1 > $HOME/ZIP/file2
echo abcdef | md5sum | cut -d" " -f1 > $HOME/ZIP/file3
zip -j $HOME/ZIP/file.zip $HOME/ZIP/file{1..3}
tar -czf $HOME/ZIP/file.tar.gz -C $HOME/ZIP/ file.zip
E??????

### Question 19
Design a basic FOR Loop that iteratively alters the file system and user entries in a passwd-like file for new users: LARRY, CURLY, and MOE.
Each user should have an entry in the $HOME/passwd file
The userid and groupid will be the same and can be found as the sole contents of a file with the user's name in the $HOME directory (i.e. $HOME/LARRY.txt might contain 123)
The home directory will be a directory with the user's name located under the $HOME directory (i.e. $HOME/LARRY)
NOTE: Do NOT use shell expansion when specifying this in the $HOME/passwd file.
The default shell will be /bin/bash
The other fields in the new entries should match root's entry
Users should be created in the order specified

## ERROR

baseline=$(head -1 ~/passwd)
for x in {LARRY,CURLY,MORE} ; do 

echo $baseline | awk -F: -v un=$x -v ui=$(cat $HOME/$x.txt) '{OFS=":"} {$1=un;$3=$4=ui;$6="HOME/"un} {print $0}' >> $HOME/passwd
mkdir $HOME/$x
done

### Question 20
Write a bash script that will find all the files in the /etc directory, and obtains the octal permission of those files. The stat command will be useful for this task.
Depending how you go about your script, you may find writing to the local directory useful. What you must seperate out from the initial results are the octal permissions of 0-640 and those equal to and greater than 642, ie 0-640 goes to low.txt, while 642 is sent to high.txt.
Have your script uniquely sort the contents of the two files by count, numerically-reversed, and output the results, with applicable titles, to the screen. An example of the desired output is shown below.
NOTE: There is a blank line being printed between the two sections of the output below.

find /etc -type f -exec stat -c '%a' {} \; > test.del 2>/dev/null

for x in $(cat test.del); do
   if [[ $x -le 640]]; then
   echo "$x" >> less.del
   elif [[ $x -ge 642 ]]; then
   echo "$x" >> more.del
   fi
done
echo "Files w/ OCTAL Perm values 642+:"
sort more.del | uniq -c | sort -nr
echo "Files w/ OCTAL Perm values 0-640:"
sort less.del | uniq -c | sort -nr

