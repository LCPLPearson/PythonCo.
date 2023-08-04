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
$two -c 6 $one | grep -Eo "6 received"
