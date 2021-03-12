# CipherSchoolsAssignment
#problem 1
n=5
x=65
for i in range(0, n):
    for j in range(0, i + 1):
        y=chr(x)+' '
        print(y, end="")
        x=x+1
    print()
 
#problem 2
n=5
k = 2*n - 2
for i in range(0, n):
    for j in range(0, k):
        print(end=" ")
    k = k - 2
    for j in range(0, i+1):
        print("* ", end="")
    print("\r")
#problem 3
print('welcome to the grocery list')
budget=int(input('enter your budget : '))
lst=[]
lst1=[]
flag=True
while(flag) : 
    print('1.Add an item')
    print('2.Exit')
    option=int(input('Enter your Choice : '))
    if(option==1) : 
        name=input('enter product : ')
        quantity=input('enter the quantity : ')
        quantity=quantity.split()[0]
        quantity=float(quantity)
        price=int(input('enter the price : '))
        if(price>budget) : 
            print('cant buy the product ###(because budget left is '+str(budget)+')')
            continue
        else : 
            for i in lst : 
                lst1.append(i[0])
            if(name in lst1) : 
                for i in lst : 
                    if(name in i) : 
                        budget=budget+i[2]
                        i[1]=quantity
                        i[2]=price
            else : 
                lst.append([name,quantity,price])
            budget=budget-price
            print('Amount left : '+str(budget))
    elif(option==2) : 
        if(budget>=0) : 
            for i in lst : 
                if(i[2]<=budget) : 
                    print('Amount left can buy you '+i[0])
                    break
        print('Grocery List is  : ')
        print('Product name    Quantity    Price')
        for i in lst : 
            print(i[0]+' '*(16-len(i[0]))+str(i[1])+' kg'+' '*(9-len(str(i[1])))+str(i[2]))
        flag=False
