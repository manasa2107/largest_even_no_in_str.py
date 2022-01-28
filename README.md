# largest_even_no_in_str.py
import re
s=input()
s=re.sub('[^0-9]','',s)
l=[]
c=0
for i in s:
    if i not in l:
        l.append(i)
for i in l:
    if int(i)%2!=0:
        c+=1
if c==len(l):
    print(0)
else:
    l=sorted(l,reverse=True)
    if int(l[-1])%2==0:
        print(''.join(l))
    else:
        if int(l[-2])%2==0:
            l[-1],l[-2]=l[-2],l[-1]
            print(''.join(l))
        else:
            for i in l:
                if int(i)%2==0:
                    d=l.index(i)
                    r=i
                    l.pop(d)
                    l.append(r)
                    print(''.join(l))
                
    
