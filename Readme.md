# Learn Kotlin
### Note
* no semicolons at end of lines
* Data types are declared after a variable or function name
* Question mark after a datatype means the variable can expect a null value

### Syntax
(i) package definition -top of .kt file
```
		package my.demo
		import kotlin.text.*
```

(ii) program entry point-through main function
```
    fun main() {
		    //code//
		}
```
### Variables
we can use :
* val – read-only variable that is assigned data once
* var – variable whose data can change during execution
* TODO(): Marking code as incomplete

```
		…
		var a: Int
		var a: Int = 5
		var name = “Dickson”

		val a: Int
		val a: Int = 5
		…
```
#### Swapping two variables
```
		var a = 1
		var b = 2
		a = b.also { b = a }
```

#### Constants
```
const val MAX_COUNT = 8
```
* constants are named in capital letters
### Array
use listOf()

```
val fruits = listOf("apple", "banana", "kiwifruit")

```
* values can't be changed - "val"
##### loop through an Array
```
for (item in items) {
		println(item)
}
```
Checking if a collection contains an object using in operator:
```
val fruits = listOf("banana", "avocado", "apple", "kiwifruit")
when {
		"orange" in fruits -> println("juicy")
		"apple" in fruits -> println("apple is fine too")
}
```
##### map and filter data in array using lambda expression
```
val fruits = listOf("banana", "avocado", "apple", "kiwifruit")
fruits
		.filter { it.startsWith("a") }
		.sortedBy { it }
		.map { it.toUpperCase() }
		.forEach { println(it) }
```
##### check if an array contains a specific object
use 'in' - this checks if an instance of the object exists in the array
```
val fruits = listOf("banana", "avocado", "apple", "kiwifruit")
when {
    "orange" in items -> println("juicy")
    "apple" in items -> println("apple is fine too")
}
```
in code(for other checks):
```
if ("apple" in fruits) {
			//code
	 }
```

### Map
data is added in value key pair
```
val map = mapOf("a" to 1, "b" to 2, "c" to 3)
	println(map["key"])
	map["key"] = value
```
### Functions
can be declared with parameters e.g
```
		fun sum(a: Int, b:Int): Int{
		    println("sum of $a and $b is ${a + b}")
		}
```
* data type comes after the parameter is declared in the function

## String template
```
				var a = 1
				val s1 = "a is $a"
				a = 2
				val s2 = "${s1.replace("is", "was")}, but now is $a"
```
$a - get value of the variable a

## Conditional expression
##### if...else
```
  		fun maxOf(a: Int, b: Int): Int {
				if (a > b) {
				     return a
				} else {
			                 return b
			            }
			}
```
or one-liner if..else

```
  		fun maxOf(a: Int, b: Int) = if (a > b) a else b

			syntax: fun Name(parameters) = if(condtion) trueReturn else falseReturn
```

##### check for null
```
  if(Name != null){
    //code
  }
```
e.g
```
fun printProduct(arg1: String, arg2: String) {
    val x = parseInt(arg1)
    val y = parseInt(arg2)

    if (x != null && y != null) {
        println(x * y)
      }
      else {
        println("'$arg1' or '$arg2' is not a number")
      }
}
```
null check shorthand in a variable
```
val value = ...
	value?.let {
			 //execute this block if not null
	}
```
##### casting a datatype to an object
'is' is used
```
fun getStringLength(obj: Any): Int? {
    if (obj is String && obj.length > 0) {
    return obj.length
    }

    if (obj !is String) {
    return null
    }

    return null
}

* question mark only comes in datatype any
* A datatype is then casted to it
```

### Loops
##### for loop
```
  val fruits = listOf("apple", "banana", "kiwifruit")
    for (fruit in fruits) {
      println(fruit)
    }
```

or
```
  val fruits = listOf("apple", "banana", "kiwifruit")
    for (index in fruits.indices) {
      println("Fruit at $index is ${fruits[index]}")
    }
```
#### when expression
```
fun describe(obj: Any): String =
  when (obj) {
          1      -> "One"
        "Hello"  -> "Greeting"
        is Long  -> "Long"
      !is String -> "Not a string"
         else    -> "Unknown"
}
```

* acts like switch case
* in this function a String is expected that's why after the Datatype return of the statements in the function are Strings

```
when (x) {
	is "Foo" -> ...
	is "Bar" -> ...
	else 	 -> ...
}
```
* checks like a variable named x

* return when statements
```
fun transform(color: String): Int {
	return when (color) {
				"Red" -> 0
				"Green" -> 1
				"Blue" -> 2
				else -> throw IllegalArgumentException("Invalid color param value")
		}
}
```

#### loop with a Ranges
e.g print all numbers between the range of 1 to 5

* closed range that includes 5
```
  for (x in 1..5) {
    print(x)
}
```
* checks if x is within the range of 1 - 5 then prints the number


* half-open range doesn't include 100
```
for (x in 1 until 100) {
	...
 }
```

##### loop with ranges over a progression
* acts like a for loop till a condition is met

counts up by 2
```
for (x in 1..10 step 2) {
    print(x)
}
```
counts down by 3

```
println()
for (x in 9 downTo 0 step 3) {
    print(x)
}
```

##### loop over a collection
```
for (item in items) {
    println(item)
}
```
### Ranges
used to check if a number is within a range
```
val x = 10
val y = 9
if (x in 1..y+1) {
  println("fits in range")
}
```

* checks if x(10) is within the range of 1 to 10

 y=9 so y+1 = 10

### Classes
```
Class Name{

}
```

### Writing Test
```
class MyTestCase {
		@Test fun ensureEverythingWorks_onAndroid() {
				//code
			}
}
```
