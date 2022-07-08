# Programming is the art of telling the computer to do stuff

### Data
All computers, and consequently programs, work with and manipulate data. While the program may abstract this data to represent things such as "int" and "char" and "float", it is important to remember that all data is just a combination of 1 and 0.

### Variables
You can put this data into Variables. Variables are often described as "containers" for data, which you can assign a name and manipulate.
```python
age = 20
```

### Functions
A function is a segment of code, often code that does something useful, that is given a name and can be called later in the program. Calling a function executes the code within the function without needing to write the code again. An example of a function that is in almost every programming language is Print:
```python
print(age)
```
Which would output:
```20```
## What we have learned
Let's write a program in Python that uses a VARIABLE to store someone's age as a NUMBER, and then adds ten to that age and prints it out with a FUNCTION:
```python
age = 20

def numPlusTen(num):
	newnum = num + 10
	return newnum

print(numPlusTen(age))
```
Which would output: 
```30```
Notice how the function is not "agePlusTen", but "numPlusTen", and uses "newnum" instead of "newage" as variables. This structures the program in a way that allows it to be used for many other things, such as adding ten to a price:
```python
price = 30

def numPlusTen(num):
	newnum = num + 10
	return newnum

print(numPlusTen(price))
```
Which would output:
```40```
Notice how the only thing that has changed is the "price" variable name.
We can now call this function several times, saving space on what would otherwise be a very large program:
```python
age = 20
price = 30
km = 312
fingers = 9

def numPlusTen(num):
	newnum = num + 10
	return newnum

print(numPlusTen(age))
print(numPlusTen(price))
print(numPlusTen(km))
print(numPlusTen(fingers))
```
Which would output:
```30
40
322
19
```
Notice the 'return' statment at the end of each function, and the "num" in the parenthesies. These are called Return statments and Arguments respectivly.