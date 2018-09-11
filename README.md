
## Defining Functions

We've briefly seen a little bit of defining functions but will investigate more details and nuances here. Recall that you can define a function using the built in keyword `def` followed by a function name and any required parameters. Within an indendented block you then define what happens during the function call. Finally, any useful function should then `return` some output. All together we have:


```python
def function_name(parameter1, parameter2):
    #What the function does
    return output
```

## Functions, Variables, Namespaces and Scope

We've already seen many examples of functions and variables. 
After importing some packages, our very first line of code was roughly:  
` df = pd.read_csv('filename.csv')`. 
In this, we called a built in function (also called a method) from within the pandas package. This demonstrates the concept of a namespace; read_csv was only defined under the pandas (pd) namespace, and was not globally accessible. Similarly, we will start to see that what a variable refers to depends on context and what namespace is currently active.


```python
# This is a global variable
a = 0

if a == 0:
    # This is still a global variable
    b = 1
```


```python
c = 5 #Globally defined
```


```python
c #Calling the global variable
```




    5



# Undefined Variables Produce Errors


```python
d
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-7-e983f374794d> in <module>()
    ----> 1 d
    

    NameError: name 'd' is not defined


# Variables within Functions


```python
def my_function(c):
    # this is a local variable
    d = 3
    print('C is:', c) #Look for c within the function....if not then it will look in the global sense
    print('D is:', d)
```


```python
# Now we call the function, passing the value 7 as the first and only parameter
my_function(c=7)
```

    C is: 7
    D is: 3



```python
#Notice that globally, c is still 5
c
```




    5




```python
#Notice that globally, d is still not defined!
d
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-13-86fe4be54280> in <module>()
          1 #Notice that globally, d is still not defined!
    ----> 2 d
    

    NameError: name 'd' is not defined



```python
#Notice this function doesn't return anything. It only prints.
output = my_function(4)
```

    C is: 4
    D is: 3



```python
output
```


```python
type(output)
```




    NoneType




```python
print(output)
```

    None


# Describe the scope of a, b and c below.


```python
def my_function(a):
    b = a - 2
#     print(b)
    return b
    #Technically inside the function.
    #This would never execute because
    #as soon as we hit a return statement
    #the function exits (and returns what we asked)
    print('Stuff that never happens.')
```


```python
#Your description here
```

## Exercise 2

### A. 
Write a Python program to convert a temperature given in degrees Fahrenheit to its equivalent in degrees Celsius. You can assume that T_c = (5/9) x (T_f - 32), where T_c is the temperature in °C and T_f is the temperature in °F. Your program should ask the user for an input value, and print the output. The input and output values should be floating-point numbers.  

### B.
What could make this program crash? What would we need to do to handle this situation more gracefully?


```python
#Your code here
```

# Lambda Functions
As a final note on functions, we've also preview writing quick throwaway functions using python's `lambda` method. Lambda functions cannot be reused, but provide a quick and easy way to both define and implement a function simultaneously. Our previous outline of functions, 


```python
def function_name(parameter1, parameter2):
    #What the function does
    return output
```

becomes:


```python
lambda x: output
```

Notice that everything in a lambda function must happen in a single line. For more complex functions, you will still need to define a seperate function. However, you could still pass your function through a lambda pattern like so:


```python
lambda x: your_func(x)
```

# Practice Translating Functions
Practice your programming syntax by rewriting you farenheight to celsius function above as a lambda function.


```python
f_temps = [32, 212, 0, 40, 50, 60, 65, 70, 75, 80, 85, 90, 95, 100, 105]
c_temps = f_temps.map(lambda x: #Rewrite your temperature function in a single line here)
```
