# return a reversed version of a string
words = sentence.split()[::-1]
l = []
for i in words:
  l.append(i)
return ' '.join(l)'''

#return comma in a number string
return '{:;}'.format(n)

# return two list of numbers and put them in order
a = lst 0 + lst1
a = sorted(a)
a = reversed(a)
return list(a)


# avg numbers 
avg = (s1+s2+s3) / 3.0
if avg > 50.0:
  return 'GO'
else:
  return 'NOGO'


multiples = []
for i in range(0, limit+1):
  if i%integer==0 and i%2==0:
    multiples.append(i)
return multiples

diffs = []
linenum = 0


#Difference of lines in 2 files
with open(f0) as fp0:
  with open(f1) as fp1:
  line0= fp0.readlines()
  for i in fp1.readlines():
    if i != lines0[linenum0:
      diffs.append(linenum)
    linenum += 1
return diffs

#return dupe
seen = []
for i in lst:
    if i in seen:
      return i
    else:
      seen.append(i)

#return length of shortest word
words = strng.split()
minlen = len(words[0])
for word in words:
    if len(word) < minlen:
      minlen = len(word)
return minlen

#return digits in a string
chars = []
for c in strng:
    if c.isdigit():
      chars.append(c)
      x = ''.join(chars)
      x = int(x)
      x = chr(x)
return x

# return the number that isnt in order
for i in range(len(arr)):
  if (arr[i+1] - arr[i]) !=1:
    return arr[arr+1]
return None

fun=$(sort -n -t: -k4 /etc/passwd | head -10 | tail -1 | cut -d: -f6)
echo $fun | md5sum | cut -d- -f1
sky=$(sort -n -t: -k4 /etc/passwd | head -10 | tail -1 | cut -d: -f6)
echo $sky | md5sum | cut -d- -f1



touch hashed.txt error.txt
find /bin /var /etc -maxdepth 3 ! -type p -exec md5sum {} /; >> hashed.txt 2>> error.txt
success=$(wc -l < hashed.txt)
echo "Successfully Hashed Files: "$success
fail=$(grep -c "Is a directory" error.txt)
echo "Unsuccessfully Hashed Directories: "$fail

### Locke's 17 - Bash
```
dg=$( ip route | cut -d" " -f3 | head -1 )
p=$( which ping )
respo=$( $p -c 6 $dg | grep '6 received' | cut -d, -f2 | cut -d" " -f2-3)

if [[ $respo == '6 received' ]]; then
    echo "successful"
else
    echo "failure"
fi
```















