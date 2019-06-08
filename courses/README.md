# Learning Python Project
      
## Udemy

- [ ] https://www.udemy.com/the-complete-python-postgresql-developer-course/learn/v4/
- [ ] https://www.udemy.com/complete-python-bootcamp/learn/v4/overview

## CodeAcademy

Two common errors that we encounter while writing Python are SyntaxError and NameError.

**SyntaxError** means there is something wrong with the way your program is written — punctuation that does not belong, a command where it is not expected, or a missing parenthesis can all trigger a SyntaxError.

A **NameError** occurs when the Python interpreter sees a word it does not recognize. Code that contains something that looks like a variable but was never defined will throw a NameError.

### Numbers:

Integer: Is a whole number and has no decimal point. It includes zero and negative numbers.

Float (floating-point number): Is a decimal number. It can be used to represent fractional quantities as well as precise measurements. https://docs.python.org/3/tutorial/floatingpoint.html

 Python performs addition, subtraction, multiplication, and division with +, -, *, and /.

### Control Flow

In Python we can use the following keyword if, elif and else. The execution flow is the following:


List comprehension

```
a = [
   x for x in range(20) // loop
   if x % 2 == 0        // conditional
   x * 2                // action
]

```

Try/Catch Statements

```
def divides(a,b)
  try:
    result = a / b
    print (result)
  except ZeroDivisionError:
    print ("Can't divide by zero!")
```

Tip:

Add execute permissions to file 

`chmod +x <filename.sh>`

### Lists

Two combine two or more lists we can use zip

```
names = ['Jenny', 'Alexus', 'Sam', 'Grace']
dogs_names = ['Elphonse', 'Dr. Doggy DDS', 'Carter', 'Ralph']

names_and_dogs_names = zip(names, dogs_names)

print(names_and_dogs_names)
# <zip object at 0x7fa81d48a348>
print(list(names_and_dogs_names))
# [('Jenny', 'Elphonse'), ('Alexus', 'Dr. Doggy DDS'), ('Sam', 'Carter'), ('Grace', 'Ralph')]
```

If we want to append to a list we can use .append()

Another method is using the + operator. For example:

```
items_sold_new = items_sold + ['biscuit', 'tart']
print(items_sold_new)
# ['cake', 'cookie', 'bread', 'biscuit', 'tart']
```

The function range takes a single input, and generates numbers starting at 0 and ending at the number before the input. Similar to zip, the range function returns an object that we can turn into a list.

The range function can also take two parameters, the first one servers as a starting point and the second point as a ending point. Finally, it is possible to pass it three parameters. The last parameter is called a “skip”. It will give us a list where each number is “skip” greater than the previous number.

```
my_range2 = range(2, 9, 2)
print(list(my_range2))
# [2, 4, 6, 8]
```

#### Selecting lists


Python is zero-indexed. To select an element we can select [2] index. We can also use len() to get the length of the list.

To select the last element, we can simply type [-1]. 

**Slicing List**

We can slice a list by setting **start** to select the first element we want and **end** is one more than the last index we want to include. list[start:end]

`fruits = ['apple', 'banana', 'cherry', 'date']`

```
banana_cherry = fruits[1:3]
# ['banana, 'cherry']
```


We can also use shorter for selecting.

- When selecting from the beginning we can omit the zero [0:3] becomes [:3].
['apple', 'banana', 'cherry']
- When selecting the last elements we can do something similar [2:].
['cherry', 'date']
- We can also use the following syntax so select the last three elements [-3:]
['banana', 'cherry', 'date']

Other methods we can do against lists count(), sort()

**Sort** is a bit special, in a way that it does not return a new list but modifies the existing list.

`fruits.sort()`

Another method similar is **sorted**. Sorted is different because it comes before the list and it returns a new list.

```
sorted_fruit = sorted(fruits)
print(sorted_fruit)
```
