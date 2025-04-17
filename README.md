# Data-Structures-using-Python-13-2

## AIM:

To write a Python program that evaluates a postfix expression using a stack, where the expression can contain two-digit numbers and basic binary operators

## ALGORITHM:

Step 1: Start the program.

Step 2: Split the input postfix expression into a list of tokens (numbers and operators).

Step 3: Initialize an empty stack.

Step 4: If the token is a number, push it onto the stack.

Step 5: If the token is an operator:

a) Pop the top two numbers from the stack.

b) Apply the operator on them (second popped first, then first popped).

c) Push the result back onto the stack.

Step 6: After processing all tokens, the final result is at the top of the stack.

Step 7: Stop the program.

# PROGRAM: 
```

OPERATORS=set(['*','-','+','/'])

def string_conv(str):
    l=[]
    for i in range (0,len(str)):
        if (str[i].isdigit() and str[i+1]=='.' and str[i+2].isdigit()):
            st=str[i]+str[i+1]+str[i+2]
            l.append(st)
        elif (str[i] in OPERATORS):
            l.append(str[i])
    return l;
    
def evaluate_postfix(expression):
    exp=string_conv(expression)
    stack=[] 
    for i in expression:
        if i not in OPERATORS:
            stack.append(i)
        else:
            a=stack.pop()
            b=stack.pop()
            
            if i=='*':
                res=int(b)*int(a)
            elif i=='+':
                res=int(b)+int(a)
            elif i=='-':
                res=int(b)-int(a)
            elif i=='/':
                res=int(b)/int(a)
            stack.append(res)
    return stack[0]

m = input()
print("postfix expression: ",m)
n=m.split()
print("Evaluation result: ",evaluate_postfix(n))
```
# OUTPUT:

![image](https://github.com/user-attachments/assets/583007aa-9431-4425-a5c1-dcc8b5f7f61e)


# RESULT:

Thus, Evaluation of postfix expression using a stack by pushing operands and applying operators in order proved successfully.
