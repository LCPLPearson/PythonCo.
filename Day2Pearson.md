with open("test.txt", 'w') as fp:
  fp.write('first line\n')
  lines = ['Second Line\n', 'Third Line\n', 'Last Line\n']
fp.writelines(lines)

#r is for read, w if for write.
with open('test.txt', 'r') as fp:
  fp.read
'First line\nSecond Line\nThird Line\nLast Line\n'
  fp.read(5)
'First'
fp.readline
fp.readlines
mystring = "Every Third Word"
mystring.split(" ")
['Every', 'Third', 'Word']
