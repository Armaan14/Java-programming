def twins(a,b):
    a=a.lower()
    b=b.lower()
    a_even=[]
    a_odd=[]
    b_even=[]
    b_odd=[]
    if len(a)!=len(b):
        return "No"
    alphabet = list(map(chr, range(97, 123)))
    for i in range(len(a)):
        if i%2==0:
            a_even.append(a[i])
        else:
            a_odd.append(a[i])
    
    for i in range(len(b)):
        if i%2==0:
            b_even.append(b[i])
        else:
            b_odd.append(b[i])
    flag1=0
    for i in range(26):
        if (a_even.count(alphabet[i])==b_even.count(alphabet[i])) and (a_odd.count(alphabet[i])==b_odd.count(alphabet[i])):
            flag1=1
        else:
            flag1=0
        if flag1==0:
            return "No"
    return "Yes"

if _name__=="__main_":
    n=int(input())
    aa=[]
    bb=[]
    for i in range(n):
        aa.append(input().strip())
    temp=int(input())
    for i in range(temp):
        bb.append(input().strip())
    
    result=[]
    for i in range(n):
        result.append(twins(aa[i],bb[i]))
    
    for i in range(n):
        print(result[i])
