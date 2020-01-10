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

### Loops

#### For loop

```
dog_breeds = ['french_bulldog', 'dalmation', 'shihtzu', 'poodle', 'collie']
for breed in dog_breeds:
    print(breed)
```

The general way of writing a loop is:

```
for <temporary variable> in <list variable>:
    <action>
```

As we use loops to iterate, we can also use it to search. A useful keyword is break, which always use to exit the loop at a certain point.

```
items_on_sale = ["blue_shirt", "striped_socks", "knit_dress", "red_headband", "dinosaur_onesie"]

print("Checking the sale list!")
for item in items_on_sale:
  print(item)
  if item == "knit_dress":
    break
print("End of search!")
```

Another keyword that is useful is continue; what it does is it skips an index based on a evaluation and continues to iterate through the loop.

```
ages = [12, 38, 34, 26, 21, 19, 67, 41, 17]

for age in ages:
  if age < 21:
    continue
  print(age)
```

#### While Loops

Another kind of loop is the while loops:

```
dog_breeds = ['bulldog', 'dalmation', 'shihtzu', 'poodle', 'collie']

index = 0
while index < len(dog_breeds):
  print(dog_breeds[index])
  index += 1
```

While we are looping through a list we can also have if statement to add or remove something depending on our statement.

`usernames = [word for word in words if word[0] == '@']`

### Strings

With strings we can use length and slice them via their index, similar to how lists work.

```
first_name = "Reiko"
last_name = "Matsuki"

def password_generator(first_name, last_name):
  return first_name[len(first_name)-3:] + last_name[len(last_name)-3:]


temp_password = password_generator(first_name, last_name)

print(temp_password)
# ikouki
```

Selecting characters from strings, slicing strings, and concatenating strings, each time we perform one of these operations we are creating an entirely new string.

This is because strings are immutable. This means that we cannot change a string once it is created. We can use it to create other strings, but we cannot change the string itself.

This property, generally, is known as mutability. Data types that are mutable can be changed, and data types, like strings, that are **immutable** cannot be changed.

In Python we can also escape characters with \"

favorite_fruit_conversation = "He said, \"blueberries are my favorite!\""

If we need to iterate through a string to check if a character is present, we can simple do the following letter in word.

```
>>>"e" in "blueberry"
True
>>> "a" in "blueberry"
False
```

Example of the power of strings:

The following is a function that returns the common letters in two different strings

```
def common_letters(string_one, string_two):
  common = []
  for letter in string_one:
    if (letter in string_two) and not (letter in common):
      common.append(letter)
  return common

```
A function that creates a password from the username. If the username is AbeSimp, then the temporary password generated should be pAbeSim.

```
def password_generator(user_name):
    password = ""
    for i in range(0, len(user_name)):
        password += user_name[i-1]
    return password
```

### Dictionaries

A dictionary is an unordered set of key value pairs.

`sensors =  {"living room": 21, "kitchen": 23, "bedroom": 20}`

You can mix different type of key value pairs

`person = {"name": "Shuri", "age": 18, "siblings": ["T'Chaka", "Ramonda"]}`

Dictionaries rely on having “hashable” values of keys. A hash value must be unchangeable, for example, number or strings. Having a list for as a key would yield the error of unhashable.

`TypeError: unhashable type: 'list'`

If we want to add a key and object to a dictionary, we can do the following:

`person["location"] = "Iceland"`

Or we could add multiple values using the method update.

`person["location"] = "Iceland"`

#### Comprehensions to Dictionaries

If we want to combine two list into a dictionary, it is possible to use a list comprehensions.

```
names = ['Jenny', 'Alexus', 'Sam', 'Grace']
heights = [61, 70, 67, 64]
students = {key:value for key, value in zip(names, heights)}

# students is now {'Jenny': 61, 'Alexus': 70, 'Sam': 67, 'Grace': 64}
```

#### Using Dictionaries

When accessing keys that do not exist, a way to avoid KeyErrors is to use try/except.

```
key_to_check = "Landmark 81"
try:
  print(building_heights[key_to_check])
except KeyError:
  print("That key doesn't exist!")
```

Another way to check if a key exist in a dictionary it to use the method .get(). If the key is not found it will return None.

```
building_heights = {"Burj Khalifa": 828, "Shanghai Tower": 632, "Abraj Al Bait": 601, "Ping An": 599, "Lotte World Tower": 554.5, "One World Trade": 541.3}

# this line will return 632:
building_heights.get("Shanghai Tower")

#this line will return None:
building_heights.get("My House")
```

We can also specify a default value instead of `None`.

```
>>> building_heights.get('Shanghai Tower', 0)
632
>>> building_heights.get('Mt Olympus', 0)
0
```

We can also remove elements from the dictionary using the method **.pop()**.

```
available_items = {"health potion": 10, "cake of the cure": 5, "green elixir": 20, "strength sandwich": 25, "stamina grains": 15, "power stew": 30}
health_points = 20

health_points += available_items.pop("stamina grains", 0)
health_points += available_items.pop("power stew", 0)
health_points += available_items.pop("mystic bread", 0)

print(available_items)
print(health_points)
# {'green elixir': 20, 'cake of the cure': 5, 'strength sandwich': 25, 'health potion'# : 10}
# 65
```

Apart from fetching and removing elements, we can loop through all the elements in a dictionary.
Dictionaries also have a .keys() method that returns a dict_keys object. A dict_keys object is a view object, which provides a look at the current state of the dictionary, without the user being able to modify anything. 

```
user_ids = {"teraCoder": 100019, "pythonGuy": 182921, "samTheJavaMaam": 123112, "lyleLoop": 102931, "keysmithKeith": 129384}

users = user_ids.keys()

#pythonGuy
#keysmithKeith
#lyleLoop
#teraCoder
#samTheJavaMaam
```


On the contract, we can also use a method called .values(), to get the values of the dictionary. 

```
num_exercises = {"functions": 10, "syntax": 13, "control flow": 15, "loops": 22, "lists": 19, "classes": 18, "dictionaries": 18}

total_exercises = 0

for num in num_exercises.values():
  total_exercises += num
  
print(total_exercises)
#115
```

You can also get all the keys and values with **.items()**.

Like **.keys()** and **.values()**, it returns a dict_list object. 
 
Each element of the dict_list returned by .items() is a tuple consisting of:

```
(key, value)

For example:

biggest_brands = {"Apple": 184, "Google": 141.7, "Microsoft": 80, "Coca-Cola": 69.7, "Amazon": 64.8}

for company, value in biggest_brands.items():
  print(company + " has a value of " + str(value) + " billion dollars. ")

# Apple has a value of 184 billion dollars.
# Google has a value of 141.7 billion dollars.
# Microsoft has a value of 80 billion dollars.
# Coca-Cola has a value of 69.7 billion dollars.
# Amazon has a value of 64.8 billion dollars
```

### Classes

You can check the type of data by using type(variable).

A class is a template for a data type. It describes the kinds of information that class will hold and how a programmer will interact with the data.

```
class CoolClass:
  pass
```

In order to use your class you need to instantiated.

`cool_instance = CoolClass()`

Above, we created an object and assigned it to the variable cool_instance.

A class instance is called an object. The pattern of defining classes and creating objects to represent the responsibilities of a program is knows as OOP.

Instantiation takes a class and turns it into an object.

The __main__ in Python means, “this current file that we’re running”.


#### Class Variables

When we want the same data to be available to every instance we use a class variable.

```
class Musician:
  title = "Rockstar"

drummer = Musician()
print(drummer.title)
# prints "Rockstar"
```

You can access all the object’s class variable with object.variable.

#### Methods

Methods are functions that are defined as part of the class.

The first argument in a method is always the object that is calling the method, convention recommends we name the first argument self.

```
class Dog:
  dog_time_dilation = 7

  def time_explanation(self):
    print("Dogs experience {} years for every 1 human year.".format(self.dog_time_dilation))

pipi_pitbull = Dog()
pipi_pitbull.time_explanation()
# Prints "Dogs experience 7 years for every 1 human year."
```

#### Constructors

There are magical methods in Python called “dunder methods” short for double-underscore.

The first dunder method is **__ init __**

This method is used to initialize a newly created object. Methods that are used to prepare an object being instantiated are called constructor.

Python programmers who refer to a constructor are usually taking about the __ init __ method.

```
class Shouter:
  def __init__(self, phrase):
    # make sure phrase is a string
    if type(phrase) == str:

      # then shout it out
      print(phrase.upper())

shout1 = Shouter("shout")
# prints "SHOUT"

shout2 = Shouter("shout")
# prints "SHOUT"

shout3 = Shouter("let it all out")
# prints "LET IT ALL OUT"
```

An important thing to note is that each instance variable can hold different kinds of data. The data is not shared by all instances of a class, they are variables that are specific to the object they are attached to.

```
class FakeDict:
  pass
  
fake_dict1 = FakeDict()
fake_dict2 = FakeDict()

fake_dict1.fake_key = "This works!"
fake_dict2.fake_key = "This too!"

# Let's join the two strings together!
working_string = "{} {}".format(fake_dict1.fake_key, fake_dict2.fake_key)
print(working_string)
# prints "This works! This too!"
```

There are two Python functions that can help us learn if an object has an attribute and which attribute exists.
- getattr()
- hasattr()

```
hasattr(attributeless, "fake_attribute")
# returns False

getattr(attributeless, "other_fake_attribute", 800)
# returns 800, the default value
```

In order to see what attributes an object has we can run dir().

```
class FakeDict:
  pass

fake_dict = FakeDict()
fake_dict.attribute = "Cool"

dir(fake_dict)
# Prints ['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'attribute']
```

Since everything is an object in Python, we can called dir() on anything

```
type(fun_list)
# Prints <class 'list'>

dir(fun_list)
# Prints ['__add__', '__class__', [...], 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```

Using string representation with the special dunder method, __ init __ , we can print out information about our class.

```
class Employee():
  def __init__(self, name):
    self.name = name

  def __repr__(self):
    return self.name

argus = Employee("Argus Filch")
print(argus)
# prints "Argus Filch"
```

#### Inheritance and Polymorphism

In the following example, we see how we can inherit from one class

```
class User:
  is_admin = False
  def __init__(self, username)
    self.username = username

class Admin(User):
  is_admin = True
```

#### Override Method

Override method definition is to offer a new definition for the method in our subclass.

```
class Message:
  def __init__(self, sender, recipient, text):
    self.sender = sender
    self.recipient = recipient
    self.text = text

class User:
  def __init__(self, username):
    self.username = username
    
  def edit_message(self, message, new_text):
    if message.sender == self.username:
      message.text = new_text
      
# Admins overrides the edit message and does not check for user
# since admin can override any message regardless of who posted it
class Admin(User):
  def edit_message(self, message, new_text):
      message.text = new_text
```

#### Super()

If we want to add extra logic to an existing method, we can use super(). Super gives us a proxy object. With this proxy object, we can invoke the method of an object's parent class (also called its superclass). We call the required function as a method on super().

```
class PotatoSalad:
  def __init__(self, potatoes, celery, onions):
    self.potatoes = potatoes
    self.celery = celery
    self.onions = onions
    
class SpecialPotatoSalad(PotatoSalad):
  def __init__(self, potatoes, celery, onions, raisins):
    super().__init__(potatoes, celery, onions, raisins)
    self.raisins = 40
```

#### Interfaces

When two classes have the same method names and attributes, we say they implement the same interface. An interface in Python usually refers to the names of the methods and the arguments they take. Other programming languages have more rigid definitions of what an interface is, but it usually hinges on the fact that different objects from different classes can perform the same operation (even if it is implemented differently for each class).

```
class InsurancePolicy:
  def __init__(self, price_of_item):
    self.price_of_insured_item = price_of_item
    
class VehicleInsurance(InsurancePolicy):
  def get_rate(self):
    return self.price_of_insured_item * 0.001

class HomeInsurance(InsurancePolicy):
  def get_rate(self):
    return self.price_of_insured_item * 0.00005
```

#### Polymorphism

Polymorphism is the term used to describe the same syntax (like the + operator here, but it could be a method name) doing different actions depending on the type of data.

```
# For an int and an int, + returns an int
2 + 4 == 6

# For a float and a float, + returns a float
3.1 + 2.1 == 5.2

# For a string and a string, + returns a string
"Is this " + "addition?" == "Is this addition?"

# For a list and a list, + returns a list
[1, 2] + [3, 4] == [1, 2, 3, 4]
```

In this example we use the dunder method **__ add __**

```
class Atom:
  def __init__(self, label):
    self.label = label
    
  def __add__(self, other):
    return Molecule([self, other])
    
class Molecule:
  def __init__(self, atoms):
    if type(atoms) is list:
            self.atoms = atoms
      
sodium = Atom("Na")
chlorine = Atom("Cl")
salt = Molecule([sodium, chlorine])
# salt = sodium + chlorine
```

Mode dunder methods available:

```
class LawFirm:
  def __init__(self, practice, lawyers):
    self.practice = practice
    self.lawyers = lawyers
    
  def __len__(self):
    return len(self.lawyers)
  
  def __contains__(self, lawyer):
    return lawyer in self.lawyers
    
d_and_p = LawFirm("Injury", ["Donelli", "Paderewski"])
```

### Data Structures

#### Nodes

A node contains data and the link or *pointer* to another node.

![image](https://user-images.githubusercontent.com/1566236/60555044-af6d8400-9d08-11e9-877b-efeef0318fa7.png)

In summary nodes
- Contain data, which can be a variety of data types
- Contain links to other nodes. If a node has no links, or they are all null, you have reached the end of the path you were following.
- Can be orphaned if there are no existing links to them

Example of using Node

```
class Node:
  def __init__(self, value, link_node=None):
    self.value = value
    self.link_node = link_node
    
  def set_link_node(self, link_node):
    self.link_node = link_node
    
  def get_link_node(self):
    return self.link_node
  
  def get_value(self):
    return self.value

# Add your code below:
yacko = Node("likes to yak")
wacko = Node("has a penchant for hoarding snacks")
dot = Node("enjoys spending time in movie lots")

yacko.set_link_node(dot)
dot.set_link_node(wacko)

# yacko -> dot -> wacko

dots_data = yacko.get_link_node().get_value()
print(dots_data)
# enjoys spending time in movie lots

wackos_data = dot.get_link_node().get_value()
print(wackos_data)
# has a penchant for hoarding snacks

print(yacko.get_link_node().get_link_node().get_value())
# has a penchant for hoarding snacks
```

#### Linked List

A linked list is one of the basic structures in Computer Science. A list is comprised of a series of nodes. The **head node** is the node at the beginning at the list. Each node contains data and a link or a pointer to the next node. The list is terminated when the node link is null. This is called the **tail node**. Linked lists can be unidirectional or bidirectional.

![image](https://user-images.githubusercontent.com/1566236/60584577-a35ee200-9d5b-11e9-96d0-72af462f5cfe.png)

Common operations found in linked lists are:

- adding nodes
- removing nodes
- finding nodes
- traversing nodes

Removing and adding nodes require some maintance to the existence link list. One cannot just simply add or remove nodes. In the following example we want to remove node_b however we have to change the link of node_a beforehand.

![image](https://user-images.githubusercontent.com/1566236/60585026-bfaf4e80-9d5c-11e9-96b1-c2c9ceaca60d.png)

```
class Node:
  def __init__(self, value, next_node=None):
    self.value = value
    self.next_node = next_node
    
  def get_value(self):
    return self.value
  
  def get_next_node(self):
    return self.next_node
  
  def set_next_node(self, next_node):
    self.next_node = next_node

class LinkedList:
  def __init__(self, value=None):
    self.head_node = Node(value)
  
  def get_head_node(self):
    return self.head_node
  
  def insert_beginning(self, new_value):
    new_node = Node(new_value)
    new_node.set_next_node(self.head_node)
    self.head_node = new_node
    
  def stringify_list(self):
    string_list = ""
    current_node = self.get_head_node()
    while current_node:
      if current_node.get_value() != None:
        string_list += str(current_node.get_value()) + "\n"
      current_node = current_node.get_next_node()
    return string_list
  
  def remove_node(self, value_to_remove):
    current_node = self.get_head_node()
    if current_node.get_value() == value_to_remove:
      self.head_node = current_node.get_next_node()
    else:
      while current_node:
        next_node = current_node.get_next_node()
        if next_node.get_value() == value_to_remove:
          current_node.set_next_node(next_node.get_next_node())
          current_node = None
        else:
          current_node = next_node
```

#### Stacks

A stack is a data structure which contains ordered set of data

A stack provides three methods:

- Push: adds data to the "top" of the stack
- Pop: returns and removes data of the "top" of the stack
- Peek: returns data from the "top" of the stack without removing it

The last plate you put down becomes the first and only one that you can access. This is the **Last In, First Out or LIFO**.

![image](https://user-images.githubusercontent.com/1566236/61175582-1cdaa980-a580-11e9-9dcf-93dd845978e7.png)

Stacks can be implemented using a linked list.

![image](https://user-images.githubusercontent.com/1566236/61175627-e5b8c800-a580-11e9-93e7-ded0d19853d3.png)

A constraint that may be placed on a stack is its size. This is done to limit and quantify the resources the data structure will take up when it is “full”.

Attempting to push data onto an already full stack will result in a **stack overflow**. Similarly, if you attempt to pop data from an empty stack, it will result in a **stack underflow**.

We can now create a Stack class with the following methods: push, pop & peek

```
from node import Node

class Stack:
  def __init__(self):
    self.top_item = None
  
  # Define your push() and pop() methods below:
  def push(self, value):
    item = Node(value)
    item.set_next_node(self.top_item)
    self.top_item = item

  def pop(self):
    item_to_remove = self.top_item
    self.top_item = item_to_remove.get_next_node()
    return item_to_remove.get_value()
  
  def peek(self):
    return self.top_item.get_value()
  ```
  
  After we have a basic methods working, now we are going to add size and limit to avoid a stackoverflow
  
 ```
from node import Node

class Stack:
  def __init__(self, limit=1000):
    self.top_item = None
    self.size = 0
    self.limit = limit
  
  def push(self, value):
    if self.has_space():
      item = Node(value)
      item.set_next_node(self.top_item)
      self.top_item = item
      # Increment stack size by 1 here:
      self.size += 1
    else:
      print("All out of space!")

  def pop(self):
    if not self.is_empty():
      item_to_remove = self.top_item
      self.top_item = item_to_remove.get_next_node()
      self.size -= 1
      return item_to_remove.get_value()
    else:
      print("This stack is totally empty.")
  
  def peek(self):
    if not self.is_empty():
      return self.top_item.get_value()
    else:
      print("Nothing to see here!")
      
  # Define has_space() and is_empty() below:
  def has_space(self):
    if self.limit > self.size:
      return True
    else:
      return False
    
  def is_empty(self):
    if self.size == 0:
      return True
    else:
      return False
 ```

The following code is for the building the **Towers of Hanoi** game.

![image](https://user-images.githubusercontent.com/1566236/66935206-ad0a0e00-f009-11e9-89a8-c985c8cc3cf3.png)


```
from stack import Stack

print("\nLet's play Towers of Hanoi!!")

#Create the Stacks
stacks = []
left_stack = Stack("Left")
middle_stack = Stack("Middle")
right_stack = Stack("Right")

#Set up the Game
stacks += [left_stack, middle_stack, right_stack]


#Get User Input
num_disks = int(input("\nHow many disks do you want to play with?\n"))

while num_disks < 3:
  num_disks = int(input("Enter a number greater than or equal to 3\n"))

# Set all disks to left stacks
for disk in range(num_disks, 0, -1):
  left_stack.push(disk)
        
# Optimal moves
num_optimal_moves = 2 ** num_disks - 1
print(num_optimal_moves)

# print(left_stack.get_name())
# print(middle_stack.get_name())
# print(right_stack.get_name())

# Helper player function
def get_input():
  choices = [stack.get_name()[0] for stack in stacks]

  while True:
    
    for i in range(len(stacks)):
      name = stacks[i].get_name()
      letter = choices[i]
      print("Enter {0} for {1}".format(letter, name))
    
    user_input = input("")
    

    if user_input in choices:
      for x in range(len(stacks)):
        return stacks[i]
    
  
# Play the Game
num_user_movies = 0

while right_stack.get_size() != num_disks:
  print("\n\n\n...Current Stacks...")
  for i in range(len(stacks)):
    print(stacks[i].print_items())
  while True:
    print("\nWhich stack do you want to move from?\n")
    from_stack = get_input()
    print("\nWhich stack do you want to move to?\n")
    to_stack = get_input()
    if from_stack.get_size() == 0:
      print("\n\nInvalid Move. Try Again")
    elif to_stack.get_size() == 0 or from_stack.peek() < to_stack.peek():
      disk = from_stack.pop()
      to_stack.push(disk)
      num_user_movies += 1
      break
  else:
    print("\n\nInvalid Move. Try Again")
    
    
print("\n\nYou completed the game in {0} moves, and the optimal number of moves is {1}".format(num_user_moves, num_optimal_moves))
```

#### Queues

A queue is a data structure which contains an ordered set of data. A queue provides three methods of interacting:

- Enqueue: adds data to the "back" or end of the queue
- Dequeue: provides and removes datah from the "front" or beginning of the queue
- Peek: reveals data from the "front" of the queue of the queue without removing it

The first person in the queue is the first to be served. Queues are a First In, First Our or FIFO structure.

![image](https://user-images.githubusercontent.com/1566236/67773280-d6776080-fa31-11e9-8122-3257ad541755.png)

Queues can be implemented using **linked lists** as the data structure. The front of the queue is equivalent to the *head node* and the back of the queue is equivalent to the *tail node*. One last constraint that may be placed on the queue is the *length*. If the queue has a limit on the amount of data, it is considered a **bounded queue**.

Similar to stacks, if we attemp to enqueue data from an already full stack, we get a *queue overflow* and if we dequeue data from an empty queue, we get a *queue underflow*.


![image](https://user-images.githubusercontent.com/1566236/67773976-f78c8100-fa32-11e9-92b2-321f601cf3dd.png)

The following is an example of an implementation of a queue

```
from node import Node

class Queue:
  def __init__(self, max_size=None):
    self.head = None
    self.tail = None
    self.max_size = max_size
    self.size = 0
    
  # Adds item from the queue
  def enqueue(self, value):
    if self.has_space():
      item_to_add = Node(value)
      print("Adding " + str(item_to_add.get_value()) + " to the queue!")
      if self.is_empty():
        self.head = item_to_add
        self.tail = item_to_add
      else:
        self.tail.set_next_node(item_to_add)
        self.tail = item_to_add
      self.size += 1
    else:
      print("Sorry, no more room!")
  
  # Remove item from the queue
  def dequeue(self):
    if self.get_size() > 0:
      item_to_remove = self.head
      print(str(item_to_remove.get_value()) + " is served!")
      if self.get_size() == 1:
        self.head = None
        self.tail = None
      else:
        self.head = self.head.get_next_node()
      self.size -= 1
      return item_to_remove.get_value()
    else:
      print("The queue is totally empty!")
  
  # Returns the first item in the queue without removing
  def peek(self):
    if self.size > 0:
      return self.head.get_value()
    else:
      print("No orders waiting!")
  
  # Returns the size of the queue
  def get_size(self):
    return self.size
  
  # Returns boolean if the queue has space
  def has_space(self):
    if self.max_size == None:
      return True
    else:
      return self.max_size > self.get_size()
    
  # Returns boolean if queue is empty
  def is_empty(self):
    return self.size == 0

print("Creating a deli line with up to 10 orders...\n------------")
deli_line = Queue(10)
print("Adding orders to our deli line...\n------------")
deli_line.enqueue("egg and cheese on a roll")
deli_line.enqueue("bacon, egg, and cheese on a roll")
deli_line.enqueue("toasted sesame bagel with butter and jelly")
deli_line.enqueue("toasted roll with butter")
deli_line.enqueue("bacon, egg, and cheese on a plain bagel")
deli_line.enqueue("two fried eggs with home fries and ketchup")
deli_line.enqueue("egg and cheese on a roll with jalapeos")
deli_line.enqueue("plain bagel with plain cream cheese")
deli_line.enqueue("blueberry muffin toasted with butter")
deli_line.enqueue("bacon, egg, and cheese on a roll")
# ------------------------ #
# Uncomment the line below:
deli_line.enqueue("western omelet with home fries")
# ------------------------ #
print("------------\nOur first order will be " + deli_line.peek())
print("------------\nNow serving...\n------------")
deli_line.dequeue()
deli_line.dequeue()
deli_line.dequeue()
deli_line.dequeue()
deli_line.dequeue()
deli_line.dequeue()
deli_line.dequeue()
deli_line.dequeue()
deli_line.dequeue()
deli_line.dequeue()
# ------------------------ #
# Uncomment the line below:
deli_line.dequeue()
# ------------------------ #
```

#### Hash Maps



