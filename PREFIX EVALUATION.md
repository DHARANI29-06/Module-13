# Exp.No:34  
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
OPERATORS=set(['*','-','+','%','/','**'])
def postfix_Eval(exp):
    stack=[]
    for i in exp:
        smallexp=''
        if i not in OPERATORS:
            stack.append(i)
        else:
            a=stack.pop()
            b=stack.pop()
            if i=='+':
                res=int(b)+int(a)
                stack.append(res) 
            if i=='-':
                res=int(b)-int(a)
                stack.append(res) 
            if i=='*':
                res=int(b)*int(a)
                stack.append(res) 
            if i=='/':
                res=int(b)/int(a)
                stack.append(res) 
            if i=='%':
                res=int(b)%int(a)
                stack.append(res) 
            if i=='**':
                res=int(b)**int(a)
                stack.append(res)
    return stack[0]
exp=input()

print("postfix expression: ",exp)
print("Evaluation result: ",postfix_Eval(exp))


```


### OUTPUT
![image](https://github.com/user-attachments/assets/18859cb3-d7ed-4b80-b07b-831b5321dc88)

### RESULT
Thus ,a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction are verified.
