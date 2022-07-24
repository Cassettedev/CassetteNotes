# Kotlin is a programming language
to add a normal variable:
```Kotlin
var x = 5
```

to make it constant:
```Kotlin
val x = 5
```

to declare the type (optional):
```Kotlin
val x: Int = 5
```

assigning null variables:
```Kotlin
val x: Int? = null
```

print statement:
```Kotlin
println(x)
```

getting input:
```Kotlin
val num1 = readLine()
val num2 = readLine()
```

converting variables to other types:
```Kotlin
/*
	!! makes the variable assume that the variable is not null
*/
val result = num1!!.toInt() + num2!!.toInt()
```

null safe tip:
```Kotlin
/*
	?: will assign the value "0" to the variable in the case that it 
	turns out to be null
*/
val num1 = readLine() ?: "0"
```

logical operators:
```Kotlin
|| // OR
&& // AND
== // Equal To
!= // Does Not Equal
!() // Inverts The Output Of The Expression In The Parenthesis
```

if else:
```Kotlin
if(condition) {
	your code goes here
} else if(condition) {
	your code goes here
} else {
	your code goes here
}
```

you can use if conditions to assign values to variables:
```Kotlin
/* 
	this willl asign 2 to x if the variabe y is 2
	and 3 if the variable y is not 2
*/
val x: Int = if(y == 2) 2 else 3
```

lists (arrays):
```Kotlin
val shoppingList = listOf<String>("bannana", "apple", "bread", "g u n")
```

accessing items in list:
```Kotlin
println(shoppingList[0])
/* output: bannana */
println(shoppingList[2])
/* output: bread */
```

By default, lists are immutable. To make them mutable:
```Kotlin
val shoppingList = mutableListOf<String>("bannana", "apple", "bread", "g u n")
```

while loop:
```Kotlin
var counter: Int = 0 /* var because the variable will change */
while(counter < shoppingList.size) {
	println(shoppingList[counter])
	counter++
	/* this code will be
	repeated until counter
	becomes equal to the
	amount of items in the
	list*
}
```

for loop:
```Kotlin
for(shoppingItem in shoppingList) {
	println(shoppingItem)
}
```

when:
```Kotlin
val x: Int = 3
when(x){
	in 1..2 -> println("x is between 1 and 2")
	in 3..10 -> println("x is between 3 and 10")
	else -> {
		more code goes here
	}
}
```

functions:
```Kotlin
fun main(){
	all code runs here
}
```

making your own function:
```Kotlin
fun addTen(){
	val num1: Int = 10
	val num2: Int = 10
	result = num1 + num2
	println(result)
}
```

function with input and return types:
```Kotlin
fun isEven(number: Int): Boolean{
	return number % 2 == 0
}
```

using function:
```Kotlin
val x = isEven(5)
println(x) /* should print false */
```

