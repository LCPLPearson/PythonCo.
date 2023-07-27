def q1(floatstr):
  newlist = []
  for y in floatstr.split('.'):
    newlist.append(float(y))
  return newlist
return [float(idx) for idx in floatstr.split(',')]



#Given the floatstr, which is a comma separated string of floats, return a list with each of the floats in the argument as elements in the list.

pass

def q2(*args):

s = 0
for arg in args:
  s += arg
return s/len(args)

return sum(args)/len(args)
#given the variable length argument list, return the average of all the arguments as a float.

pass

def q3(lst,n):

return lst[-n:]
#Given a list (lst) and a number of items (n), return a new 
    list containing the last n entries in lst.

pass

def q4(strng):

#Given an input string, return a list containing the ordinal numbers of 
    each character in the string in the order found in the input string.

return [ord(x) for x in list(strng)]

newlist = []
for i in strng:
  newlist.append(ord(i))
return newlist

pass
#Given an input string, return a tuple with each element in the tuple
    containing a single word from the input string in order.

def q5(strng):

#Given an input string, return a tuple with each element in the tuple
    containing a single word from the input string in order.

return tuple(strng.split())

def q6 (catalog order)
Given a dictionary (catalog) whose keys are product names and values are product
    prices per unit and a list of tuples (order) of product names and quantities,
    compute and return the total value of the order.

def q7(filename):

#Given a filename, open the file and return the length of the first line 
    in the file excluding the line terminator.

with open(filename) as fp:
  x = fp.readline()
  y = len(x) -1

def q8(filename,lst):

with open(filename, 'w') as fp:
  for item in lst:
    if item.lower() == 'stop':
      break
    fp.write('{item}\n')

Given a filename and a list, write each entry from the list to the file
    on separate lines until a case-insensitive entry of "stop" is found in 
    the list. If "stop" is not found in the list, write the entire list to 
    the file on separate lines.

def q9(miltime):

Given the military time in the argument miltime, return a string 
    containing the greeting of the day.


if miltime >= 0o0301 and miltime < 1200:
  return "Good Morning:
elif miltime >= 1200 and miltime < 1600:
  return "Good Afternoon"

def q10(numlist):

for i in numlist:
  if i <0:
    return
