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
