```python
o=0
for x in range(133,4093):
    for y in range(x+1, 4093+1):
        if abs(x-y)>9:
            if (x*y)%18==0:
                if (x*y)%16>0:
                    o+=1
print(o)



        #    1 2 3 4 5 6 7 8 9 10


```
