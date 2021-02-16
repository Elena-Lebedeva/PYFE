# PYFE
Python for everybody course assignments
10.2 Tuples. Write a program to read through the mbox-short.txt and figure out the distribution by hour of the day for each of the messages. You can pull the hour out from the 'From ' line by finding the time and then splitting the string a second time using a colon.
From stephen.marquard@uct.ac.za Sat Jan  5 09:14:16 2008
Once you have accumulated the counts for each hour, print out the counts, sorted by hour as shown below.

name = input("Enter file:")
if len(name) < 1 : name = "mbox-short.txt"
handle = open(name)
counts=dict()
for line in(handle):
    if not line.startswith("From ") : continue
    words=line.split()
    date=(words[5]) # <class 'str'>
    days=date.split(":") # <class 'list'>    
    days=[days[0]]
    for day in days:
        counts[day]=counts.get(day,0)+1
#print(counts) 
#RESULT {'09': 2, '18': 1, '16': 4, '15': 2, '14': 1, '11': 6, '10': 3, '07': 1, '06': 1, '04': 3, '19': 1, '17': 2}

lst=list()
for key, value in counts.items():
 newtup=(key,value)
 lst.append(newtup)
 lst=sorted(lst)
#print(lst)
#RESULT [('04', 3), ('06', 1), ('07', 1), ('09', 2), ('10', 3), ('11', 6), ('14', 1), ('15', 2), ('16', 4), ('17', 2), ('18', 1), ('19', 1)]
for key, value in lst:
 print(key,value)
OUTPUT
04 3
06 1
07 1
09 2
10 3
11 6
14 1
15 2
16 4
17 2
18 1
19 1
