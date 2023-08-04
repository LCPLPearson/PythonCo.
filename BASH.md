### Question 16
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
