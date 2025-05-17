# Exp.No:33  
## POSTFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Postfix expression that contains Multiplication and Addition operators using the stack concept.

---

### ALGORITHM

1. **Start the program.**
2. Define a set named `OPERATORS` containing all the valid operators: `*, +, **, -, /, %`.
3. Define a function `evaluate_postfix(exp)` to evaluate the postfix expression:
   - Inside the function, create an empty list called `stack` to store operands and intermediate results.
4. Loop through each item in the given postfix expression:
   - If the current item is **not in OPERATORS**, it is an operand, so append it to the stack.
   - If the current item is an **operator**:
     - Pop the top two elements from the stack (first pop is `a`, second pop is `b`).
     - Perform the operation `b <operator> a` depending on the current operator.
     - Store the result in a variable called `result`.
     - Append the result back to the stack.
5. After the loop ends, return the first element of the stack as the final evaluation result.
6. Take a postfix expression as input from the user.
7. Print the postfix expression.
8. Call the function `evaluate_postfix()` with the input and print the result.
9. **End the program.**

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
![image](https://github.com/user-attachments/assets/0508e45f-3c8e-4549-8ab5-1a3ee79e8a4b)

### RESULT
Thus , a Python program to evaluate a user-given Postfix expression that contains Multiplication and Addition operators using the stack concept are verified.
