### 1 Display middle characters of string

def get_middle_character(word):
    word_length = len(word)
    middle_index = word_length // 2

    if word_length % 2 == 0:
        return word[middle_index - 1 : middle_index + 1]
    else:
        return word[middle_index]

Test the function
print(get_middle_character("test"))  # Output: "es"
print(get_middle_character("python"))  # Output: "th"
print(get_middle_character("hello"))  # Output: "l"

### 2 Make string upper case
def make_upper_case(s):
    return s.upper()

### 3 A hero is on his way to the castle to complete his mission. However, he's been told that the castle is surrounded with a couple of powerful dragons! each dragon takes 2 bullets to be defeated, our hero has no idea how many bullets he should carry.. Assuming he's gonna grab a specific given number of bullets and move forward to fight another specific given number of dragons, will he survive?Return true if yes, false otherwise :)

def hero(bullets, dragons):
    x = dragons * 2
    return bullets >= x

### 4 For simplicity, you'll have to capitalize each word, check out how contractions are expected to be in the example below.Your task is to convert strings to how they would be written by Jaden Smith. The strings are actual quotes from Jaden Smith, but they are not capitalized in the same way he originally typed them.
Example:
Not Jaden-Cased: "How can mirrors be real if our eyes aren't real"
Jaden-Cased:     "How Can Mirrors Be Real If Our Eyes Aren't Real"
def to_jaden_case(string):
    x = string.split()
    cw = [word.capitalize() for word in x]
    return " ".join(cw)

### Given the floatstr, which is a comma separated string of floats, return a list with each of the floats in the argument as elements in the list.
def q1(floatstr):
  newlist = []
  for y in floatstr.split('.'):
    newlist.append(float(y))
  return newlist
return [float(idx) for idx in floatstr.split(',')]
pass

### given the variable length argument list, return the average of all the arguments as a float.
def q2(*args):

s = 0
for arg in args:
  s += arg
return s/len(args)

return sum(args)/len(args)
pass

def q3(lst,n):
### Given a list (lst) and a number of items (n), return a new list containing the last n entries in lst.

return lst[-n:]
pass

def q4(strng):

### Given an input string, return a list containing the ordinal numbers of each character in the string in the order found in the input string.

return [ord(x) for x in list(strng)]

newlist = []
for i in strng:
  newlist.append(ord(i))
return newlist

pass

def q5(strng):

### Given an input string, return a tuple with each element in the tuple
    containing a single word from the input string in order.

return tuple(strng.split())

def q6 (catalog order)
### Given a dictionary (catalog) whose keys are product names and values are productprices per unit and a list of tuples (order) of product names and quantities, compute and return the total value of the order.

def q7(filename):

### Given a filename, open the file and return the length of the first line in the file excluding the line terminator.

with open(filename) as fp:
  x = fp.readline()
  y = len(x) -1

def q8(filename,lst):
### Given a filename and a list, write each entry from the list to the file on separate lines until a case-insensitive entry of "stop" is found in the list. If "stop" is not found in the list, write the entire list to the file on separate lines.
with open(filename, 'w') as fp:
  for item in lst:
    if item.lower() == 'stop':
      break
    fp.write('{item}\n')
    
def q9(miltime):

### Given the military time in the argument miltime, return a string containing the greeting of the day.

if miltime >= 0o0301 and miltime < 1200:
  return "Good Morning:
elif miltime >= 1200 and miltime < 1600:
  return "Good Afternoon"

def q10(numlist):

for i in numlist:
  if i <0:
    return

### Complete the solution so that it reverses the string passed into it.

def solution(string):
    return string[::-1]
### The rgb function is incomplete. Complete it so that passing in RGB decimal values will result in a hexadecimal representation being returned. Valid decimal values for RGB are 0 - 255. Any values that fall out of that range must be rounded to the closest valid value. Note: Your answer should always be 6 characters long, the shorthand with 3 will not work here.

def rgb(r, g, b):

    r = format(max(0, min(255, r)), '02X')
    g = format(max(0, min(255, g)), '02X')
    b = format(max(0, min(255, b)), '02X')

    return r + g + b

    pass

### Complete the solution so that the function will break up camel casing, using a space between words.

def solution(s):
    return ''.join([' ' + char if char.isupper() else char for char in s])

### Given a random non-negative number, you have to return the digits of this number within an array in reverse order.

def digitize(n):
    if n == 0:
        return [0]
    rd = [int(digit) for digit in str(n)][::-1]
    return rd
### Create a function that gives a personalized greeting. This function takes two parameters: name and owner.
def greet(name, owner):
    if name == owner:
        return "Hello boss"
    else:
        return "Hello guest"

### Exam 2 q1, given a string of multiple words separate by single spaces return a new string with the sentence reversed the words themselves should remain as they are

l = []
for i in words:
l.append(i)
return ''.join (l)

return ' '.join(reversed(sentence.split()))

### q2, given a positive integer return its string representation with commas seperating groups of 3 digits
return '{:,}'.format(n)

### q3, given two lists of integers return a sorted list that contains all integers from both listsin descending order
a = lst0 + lst1
a = sorted(a)
a = reversed(a)
#print(type(a))
return list(a)
return sorted(lst0+lst1???

### q4, given 3 scores in the range 0-100 inclusive return 'GO' if the aerage score is greater than 50 return 'NOGO'

avg = (s1+s2+s3) / 3.0
if avg > 50.0:
    return 'GO'
    else:
        return 'NOGO'

### q5,    given an integer and a imit
multiples = []
for i in range(0, limit+1):
    if i%integer==0 and i%2==0:
    multiples.append(i)
    return multiples
### q6(f0, f1): given two filenames return a list whose elements consist of line numbers for which the two files differ the first line is considered line 0 
diffs - []
linenum = 0
with open(f0) as fp0:
with open(f1) as fp1:
    lines0= fp0.readlines()
    for i in fp1.readlines():
    if i !_ lines0[linenum]:
    diffs.append(linenum)
    linenum += 1 
    return diffs

### q7(lst) return the first duplicate vaulu in the given list
seen =[]
for i in lst:
    if i in seen:
        return i
        else:
            seen.append(i)

### q8(strng) given a sentence as a string with words being sepereated by a single space, return the length of the shortest word
words = strng.spit()
minlen = len(words[0])
for word in words:
if len(word) < minlen:
minlen = len(word)
return minlen

return len(min(strng.split(),key=len))

### q9(strng) given a alphanumeric string, return a character whose ascii value is that of the integer representation of all of the digits in the string concatenated in the orer in which they appear
char = []
for c in strng:
    if c.isdigit():
        chars.append(c)
        x = ''.join(chars)
        x = int(x)
        x = chr(x)
        return x

### q10(arr): given a list of positive integers sorted in ascending order, return the first non-consecutive valur if all values are consecutive return None
for i in range(len(arr)):
    if (arr[i+1] - arr[i]) !=1:
        return arr[i+1]
return None

### Keep only having to work in the first couple octets of the ip address | 
