# Password_Check

# Build a system where when user enters Reference ID it is encrypted, so that hackers
cannot view the mapping of Reference ID and finger print

Code:

import re
#userid = input('enter your user id: ')
ref_id = input('enter your reference ID: ')
x = True
while x:  
    if (len(ref_id)<6 or len(ref_id)>12):
        break
    elif not re.search("[a-z]",ref_id):
        break
    elif not re.search("[0-9]",ref_id):
        break
    elif not re.search("[A-Z]",ref_id):
        break
    elif not re.search("[$#@%&*]",ref_id):
        break
    elif re.search("\s",ref_id):
        break
    else:
        list1=list(ref_id)
        #print("Valid Password ",list1)
        list2=[]
        for i in list1:
                  
            if (i.isupper()):
                 result = i.lower()
                 list2.append(result)
     
            elif(i.islower()):
                 result = i.upper()
                 list2.append(result)
            
            else:
                list2.append(i)
            
        x=False
        break
print('Encrypted password is: ',''.join(list2))
if x:
    print("Not a Valid Password")

Output:

enter your reference ID: Ashi@12
Encrypted password is:  aSHI@12
