# scala-the-big-picture
Code samples for Pluralsight course Scala: The Big Picture  

# Course Samples
In addition to this code repository, a step-by-step instructions are availelable at [Gitbook](https://harithimanshu.gitbook.io/scala-the-big-picture/)



# Scala: The Big Picture
### by Harit Himanshu

## Description

Scala is one of the most popular functional programming languages that run on the JVM. This course covers the fundamentals of functional programming using Scala, reading and writing Scala code, error handling, classes, and concurrency.

Functional programming requires learning new programming paradigms, and Scala is an excellent language with which to do so. In this course, Scala: The Big Picture, you will learn the Scala language from scratch as a first step in your journey to master the language. First, you will learn the basics of functional programming which you’ll apply throughout the rest of the course. Next, you will explore the Scala language, from the basic syntax to functions, classes, collections, and pattern matching. Finally, you will discover how to do concurrent programming the right way using Scala. When you’re finished with this course, you will have the foundational knowledge needed to solve problems using Scala, and will know how to get help when needed.

## Course author

Harit Himanshu

Harit Himanshu is an engineer by profession with the deep interest in applying technologies to solve business problems. Harit is passionate about writing clean, modular, testable code and believes...


## Course info

    Level Beginner
    Duration 2h 16m
    Released 2 May 2018


## Table of contents

    
### Course Overview
    1m 37s
        Course Overview
        1m 37s
### Introduction
    14m 34s
        Overview
        42s
        Why Learn Scala?
        3m 37s
        What You Will Learn
        3m 4s
        Installation
        5m 0s
        Scala REPL
        47s
        Scala IntelliJ IDEA
        55s
        Summary
        25s
### Functional Programming Concepts
    15m 20s
        Overview
        39s
        Immutability
        2m 6s
        Expressions vs. Statements
        1m 6s
        Functions
        1m 3s
        Pure and Impure Functions
        4m 5s
        Referential Transparency
        1m 54s
        Higher Order Functions
        3m 31s
        Summary
        54s
### First Interaction with Scala
    13m 8s
        Overview
        48s
        REPL
        2m 42s
        Variables and Values
        1m 11s
        Conditionals
        2m 39s
        Loops
        5m 11s
        Summary
        36s
### Functions
    12m 13s
        Overview
        27s
        Structure of a Function
        3m 38s
        Anonymous Functions
        2m 41s
        Higher Order Functions
        4m 38s
        Summary
        48s
### Classes
    15m 36s
        Overview
        41s
        Structure of Classes
        4m 8s
        Companion Objects
        4m 3s
        Creating Objects Using Apply
        1m 9s
        Case Classes
        2m 36s
        Launching Standalone Programs Extending App
        2m 5s
        Summary
        51s
### Null Checks and Error Handling
    8m 48s
        Overview
        41s
        Why Null Checks Are Bad
        48s
        Option as a Better Alternative
        3m 8s
        Error Handling in Imperative Languages
        45s
        Error Handling with Try
        1m 15s
        Error Handling with Either
        1m 23s
        Summary
        46s
### Pattern Matching
    10m 57s
        Overview
        35s
        What Is It?
        1m 41s
        Match on Constants
        2m 2s
        Match on Case Classes
        1m 22s
        Match on Sequences
        1m 35s
        Match on Type Only
        1m 21s
        Guarding Your Match
        1m 34s
        Summary
        44s
### Collections
    24m 1s
        Overview
        1m 21s
        Benefits of Scala Collections Library
        2m 25s
        Mutable and Immutable
        1m 15s
        Class Hierarchy Diagram
        2m 6s
        List with Examples
        1m 39s
        Set with Examples
        53s
        Map with Examples
        1m 38s
        Methods on Numeric Collections
        1m 0s
        Filtering, Size, and Conversion Operations on Collections
        2m 59s
        Transforming a Collection Using Map
        2m 17s
        Transforming a Collection Using FlatMap
        2m 39s
        Working with Option and FlatMap
        2m 24s
        Summary
        1m 19s
### Concurrency
    14m 53s
        Overview
        52s
        Concurrency and Parallelism
        2m 16s
        Future and ExecutionContext
        4m 24s
        Futures Transformation
        1m 35s
        Filtering and Collecting Futures
        1m 35s
        Other Ways to Model Asynchronous Operation
        1m 18s
        Dealing with Future Failures
        2m 3s
        Summary
        48s
### What’s Next?
    4m 52s
        Overview
        24s
        Start Experimentation Using the REPL
        46s
        Explore the API
        48s
        Solve Programming Problems
        56s
        Where to Ask for Help
        1m 8s
        Summary
        48s




# BOOK_ harithimanshu.gitbook.io/scala-the-big-picture (20180503)

## Introduction
Last updated 6 days ago

www.scala-lang.org/download



### First Scala program on REPL

println("This is my first program")

### First Scala program in IntelliJ IDE

object Hello extends App {
 println("This is my new program from the IDE")
}


## Functional Programming concepts
Last updated 6 days ago

### Higher Order Functions

map
reduce
filter
fold


```scala
case class Fruit(name: String)
​
val apple = Fruit("apple")
val orange = Fruit("orange")
val kiwi = Fruit("kiwi")
​
val fruitBasket = List(apple, orange, kiwi, apple, orange, kiwi, apple, orange, kiwi)
​
def getApples(basket: List[Fruit]) = for (fruit <- basket if fruit.name == "apple") yield fruit
def getOranges(basket: List[Fruit]) = for (fruit <- basket if fruit.name == "orange") yield fruit
def getFruits(basket: List[Fruit], filterByFruit: Fruit => Boolean) = for (fruit <- basket if filterByFruit(fruit)) yield fruit
​
​
def getApples(basket: List[Fruit]) = getFruits(fruitBasket, (fruit: Fruit)=> fruit.name == "apple")
def getOranges(basket: List[Fruit])= getFruits(fruitBasket, (fruit: Fruit)=> fruit.name == "orange")
def getKiwis(basket: List[Fruit])= getFruits(fruitBasket, (fruit: Fruit)=> fruit.name == "kiwi")
```
​
### First interaction with Scala
Last updated 6 days ago

#### Scala REPL examples

Start a new REPL session by going to the command-line, type scala and hit Enter (or type :paste then paste from clipboard and type Ctl+D):

```scala
5 + 10
"Hello" + ", World!" // values, so expression, type returned
res0 * 10
res1 / 10
println("hello") // statement, no type returned
```

#### Variable and values

```scala
var x = "assigned"
x = "reassigned"
x
​
val y = 6
y = 7
```

#### Conditionals

```scala
val arguments = Array("Monday")
val day = if (!arguments.isEmpty) {
    arguments(0);
  } else {
    "Sunday";
  }
​
val day = if (!arguments.isEmpty) args(0) else "Sunday"
```

#### Loops

WHILE >>> Do Sth. (IMPERATIVE)
FOR >>> Return values (FUNCTIONAL)

```scala
val letters = List("a", "b", "c", "d", "e")
for (letter <- letters) {
 println(letter)
}
​
val numbers = List(1,2,3,4,5,6,7,8,9,10)
for (number <- numbers) {
  if (number % 2 == 0) {
   println(number)
  }
}
​// This can be re-written:
for (number <- numbers if (number % 2) == 0) {
  println(number)
}
​
for (
  number <- numbers
  if (number % 2 == 0)
  if (number > 2)
) println(number)
​
val letters = List("a", "b", "c")
val numbers = List(1, 2)
for (number <- numbers) {
  for (letter <- letters) {
    println(number + " => " + letter)
  }
}
     
for {
  number <- numbers
  letter <- letters
} println(number + " => " + letter)
​
val numbers = List(1,2,3,4,5,6)
for (number <- numbers) yield number * 2     
numbers
     
for (number <- numbers) { yield number * 2 } // error
for (number <- numbers) yield { number * 2 }
​
for (number <- numbers if (number % 2 == 0) ) yield { number * 2 }
​
val numbers = List(1,2,3,4,5,6)
val letters = List("a", "b")
for {
  number <- numbers
  letter <- letters
} yield number + " => " + letter
```

#### Functions
Last updated 6 days ago

##### Structure

```scala
def plusOneOrZero(number: Int): Int = { // defining output type
  if (number < 0) 0
  else number + 1
}
​
plusOneOrZero(-1)
plusOneOrZero(99)
plusOneOrZero("hello")
​
def plusOneOrZero(number: Int) = { // NOT defining output type
  if (number < 0) 0
  else number + 1
}
​
plusOneOrZero(-1)
plusOneOrZero(99)
​
def product(a: Int, b: Int) = {
  if (a == 0 || b == 0) 0
  else a * b
}
​
product(2, 10)
product(2, 0)
​
def product(a: Int, b: Int) = a * b
```

##### Anonymous functions

Intended to be used just once.

```scala
val plusOne = (x: Int) => x + 1
plusOne(99)
​
val product = (a: Int, b: Int) => a * b
product(2, 10)
```

##### Higher Order functions

Filter:

def filter(p: (A) => Boolean): List[A]

```scala
case class Fruit(name: String)
​
val apple = Fruit("apple")
val orange = Fruit("orange")
val kiwi = Fruit("kiwi")
​
val fruitBasket = List(apple, orange, kiwi, orange, kiwi, apple, kiwi, kiwi, apple, orange)
​
val numbers = List(1,2,3,4)
val letters = List("a", "b", "c", "d")
​
fruitBasket.filter((fruit: Fruit) => fruit.name == "apple")
fruitBasket.filter((fruit) => fruit.name == "apple")
fruitBasket.filter(fruit => fruit.name == "apple")
fruitBasket.filter(_.name == "apple")
fruitBasket.filter((fruit) => fruit.name != "kiwi" && fruit.name == "apple")
​
fruitBasket.filter( _.name != "kiwi" && _.name == "apple")  // error: underscore uses the variable on the left just once
```




#### Classes
Last updated 6 days ago


##### Structure of Class

```scala
class Person {}
val john = new Person
val mary = new Person
​
class Employee { var salary = 0 }
val john = new Employee
val mary = new Employee
​
john.salary
mary.salary
​
john.salary = 100
mary.salary = 120
​
john.salary
mary.salary
```


##### Clone the repository

```scala
git clone git@github.com:hhimanshu/scala-the-big-picture.git
cd src/module05
```

##### Run Employee program on REPL

```scala
class Employee {
  private var salary: Int = 100

  def getSalary() = salary
  def setSalary(newSalary: Int) = {
    salary = newSalary
  }
}
```


```scala
:load Employee.scala
​
val john = new Employee
john.salary
​
john.getSalary()
john.setSalary(100)
john.getSalary()
​
val mary = new Employee
mary.getSalary()
​
:load Employee.scala
val julie = new Employee
julie.getSalary()
```

##### Run Math program on REPL

```scala
object Math {
  def sum(a: Int, b: Int): Int = a + b
  def getPrivateMember: Int = new Math().max
}

class Math {
  private val max = 100
}

```


```scala
:load Math.scala
val math = new Math()
math.sum(5, 10)
​
:paste
​
object Math {
  def sum(a: Int, b: Int): Int = a + b
  def getPrivateMember: Int = new Math().max
}
​
class Math {
  private val max = 100
}
​
Math.sum(5, 10)
Math.getPrivateMember
```

>>> Object companion


##### Creating objects using apply

apply creates new instances of classes without the new keyword

```scala
:paste
​
object Person {
  def apply(firstName: String, lastName: String) = new Person(firstName, lastName)
}
​
class Person(firstName: String, lastName: String) {
  def getName: String = firstName + " " + lastName
}
​
val joe = Person("joe", "williams")
joe.getName
```

##### Case Classes

companion objects (and apply method)
Immutable arguments in parameter list
copy method to make modified copies
hashCode, equals, toString by default
Pattern Matching


```scala
class Person(firstName: String, lastName: String)
​
case class Course(title: String, author: String)
val scalaCourse = Course("Scala The Big Picture", "Harit Himanshu")
val anotherScalaCourse = Course("Scala The Big Picture", "Harit Himanshu")
​
scalaCourse == anotherScalaCourse
scalaCourse.title
scalaCourse.author
​
val newScalaCourse = scalaCourse.copy(title = "New Scala Course")
scalaCourse
```

##### Launching standalone programs by extending App


```scala
# make sure you have cloned the repo and are in src/module05 folder
scalac Main.scala
scala Main
```


#### Null checks and Error Handling
Last updated 6 days ago


##### Scala Option as better alternative
```scala
val employees = Set("John", "Sam", "Mary", "Stacie")
employees.find(_ == "John")
employees.find(_ == "Frank")
​
employees.find(_ == "John").get
employees.find(_ == "Frank").get
​
employees.find(_ == "Frank").getOrElse("Not Found")
​
val maybeFrank = employees.find(_ == "Frank")
if (maybeFrank.isDefined) println (maybeFrank.get)
​
employees.find(_ == "Frank").getOrElse("employee with name Frank not found!")
```


##### Error handling with Try
```scala
import scala.util.Try
val outcome = Try(10 / 0)
outcome.isSuccess
outcome.isFailure
​
import scala.util.{Try, Success, Failure}
val outcome = Try(10 / 0)
outcome match {
  case Success(value) => println("computation was ok")
  case Failure(e) => println("computation failed," + e.getMessage)
}
```


##### Error Handling with Either
```scala
def stringToInt(in: String): Either[String, Int] = {
  try {
    Right(in.toInt)
  } catch {
    case e: NumberFormatException => Left("Error: " + e.getMessage)
  }
}
​
val fiveToInt = stringToInt("5")
val helloToInt = stringToInt("hello")
```


#### Pattern Matching
Last updated 6 days ago

##### What is it?
```scala
val numbers = List(1, 2, 3)
if (numbers.nonEmpty && numbers.size >=2) println(numbers(1)) else println("found nothing")
​
val number = 5
number match {
  case 0 => "zero"
  case 5 => "five"
  case 9 => "nine"
}
 
val number = 99
number match {
  case 0 => "zero"
  case 5 => "five"
  case 9 => "nine"
}
  
val number = 99
number match {
  case 0 => "zero"
  case 5 => "five"
  case 9 => "nine"
  case _ => "nothing matched"
}
​
number match {
  case _ => "nothing"
  case 0 => "zero"
}
```

##### Match on Case Classes
```scala
case class Book(title: String, yearPublished: Integer, author: String, isbn: String)
​
val progInScala = Book("Programming in Scala 3rd Edition", 2016, "Martin Odersky", "0981531687")
val funcProgInScala = Book("Functional Programming in Scala", 2014, "Paul Chiusano", "1617290653")
val scalaCookbook = Book("Scala Cookbook", 2013, "Alvin Alexander", "1449339611")
​
progInScala match {
  case Book(title, yearPublished, author, isbn) => println(s"$title <=> $yearPublished <=> $author <=> isbn")
  case _ => println("Did not match anything")
}
​
progInScala match {
  case Book(_, _, author, _) => author
  case _ => "No Author"
}
```

##### Match on Sequences
```scala
val numbers = List(10, 20, 30)
numbers match {
  case List(a, b, c) => b
  case _ => -1
}
  
numbers match {
  case List(_, second, _) => second
  case _ => -1
}
  
val numbers = List(1, 2, 3, 4, 5, 6)
numbers match {
  case List(_, second, _) => second
  case _ => -1
}
  
numbers match {
  case List(_, second, _*) => second
  case _ => -1
}
```

##### Matching on Type only
```scala
case class Trip(to: String)
case class Car(model: String)
case class Cash(amount: Integer)
case class NoPrize()
​
val magicBucket = List(NoPrize(), Car("Tesla"), Trip("New Zealand"), NoPrize(), Trip("California"), Cash(1000), Cash(500), NoPrize(), NoPrize(), NoPrize(), NoPrize())
​
Random.shuffle(magicBucket).take(1)(0) match {
  case t: Trip => println(s"You have won a trip to ${t.to}")
  case c: Car => println(s"You have won a ${c.model}")
  case ca: Cash => println(s"You have won cash worth ${ca.amount} dollars")
  case n: NoPrize => println("Hard luck, you did not win anything. try again!")
}
```

##### Guarding your match
```scala
case class Email(from: String, body: String)
​
val importantPeople = Set("wife@home.com", "boss@office.com")
val importantEmail = Email("boss@office.com", "We need to talk!")
val regularEmail = Email("marketing@google.com", "Read our transparency report")
​
def alertOrNoAlert(email: Email) = email match {
  case Email(from, _) if importantPeople.contains(from) => println("This email needs your attention")
  case Email(_, _) => println("do not disturb!")
}
  
alertOrNoAlert(regularEmail)
alertOrNoAlert(importantEmail)
```

#### Collections
Last updated 6 days ago

##### List

```scala
val numbers = List(1, 2, 3, 4)
numbers.head
numbers.tail
​
numbers.init
numbers.last
​
numbers :+ 5
0 +: numbers
numbers
​
numbers ++ List(5, 6, 7)
List(-1, 0) ++ numbers
​
numbers.drop(1)
numbers.dropRight(1)
numbers.dropWhile(_ < 3)
```


##### Set

```scala
val numbers = Set(1, 1, 2, 2, 3, 3, 4, 4)
numbers + 6
numbers - 1
numbers
numbers ++ Set(0, 10)
```

##### Map

```scala
val weekDays = Map(1 -> "Sunday", 2 -> "Monday", 3 -> "Tuesday")
weekDays(1)
weekDays + (4 -> "Wednesday")
weekDays - 1
weekDays
​
weekDays.foreach(entry => println(s"${entry._1} => ${entry._2}"))
​
val tuple = (10, 20, 30)
tuple._1
tuple._2
tuple._3
​
weekDays ++ Map(4 -> "Wednesday", 5 -> "Thursday")
```

##### Methods on numeric collections

```scala
val numbers = List(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
numbers.sum
numbers.product
numbers.min
numbers.max
```


##### Filtering, Conversion and size related methods

```scala
val numbers = List(1,2,3,4)
numbers.head 
1
numbers.tail
List(2,3,4)

numbers.init
List(1,2,3)

numbers.last
4

numbers :+5
List(1,2,3,4,5)

0 :+ numbers
List(0,1,2,3,4,5)

// drop
// drop while
// ...
```

```scala
val pageLoadTimesInSeconds = List(2, 1, 5, 9, 14, 22, 45, 2, 4, 23)
pageLoadTimesInSeconds.filter(seconds => seconds >= 10)
pageLoadTimesInSeconds.filter(_ >= 10)
pageLoadTimesInSeconds.filter(_ >= 10).min
pageLoadTimesInSeconds.filter(_ >= 10).max
​
val list = List(4, 3, 2, 1)
val set = Set(4, 3, 2, 1)
val map = Map(1 -> "Sunday", 2 -> "Monday")
list.isEmpty
list.nonEmpty
set.isEmpty
set.nonEmpty
map.isEmpty
map.nonEmpty
​
val list = List(4, 5, 1, 3, 3, 3)
list.toSet
​
val set = Set(1, 2, 3, 4)
set.toList
```


##### Transformation using map

```scala
case class Event(location: String, dayOfWeek: String, sessionTimeInSeconds: Integer, source: String)
​
val event1 = Event("US", "Sun", 10, "Twitter")
val event2 = Event("China", "Mon", 15, "WeChat")
val event3 = Event("New Zealand", "Sun", 30, "Twitter")
val event4 = Event("US", "Tue", 5, "Facebook")
val event5 = Event("US", "Thu", 24, "LinkedIn")
val event6 = Event("US", "Sat", 60, "Facebook")
​
val events = List(event1, event2, event3, event4, event5, event6)
​
val locations = events.map(event => event.location)
val locations = events.map(_.location)
val sources = events.map(_.source)
val days = events.map(_.dayOfWeek)
```


##### Transformation using flatMap

```scala
val nestedList =  List(List(1, 2, 3, 4), List(4, 5, 6, 7))
nestedList.map(aList => aList.map(_ + 1))
nestedList.map(aList => aList.map(_ + 1)).flatten
nestedList.flatMap(aList => aList.map(_ + 1))
```


##### Working with Option and flatMap
```scala
def toInt(s: String): Option[Int] = {
  try {
    Some(s.toInt)
  } catch {
    case e: NumberFormatException => None
  }
}
    
val arguments = List("10", "eight", "5", "four", "3", "20", "one")
arguments.map(toInt(_))
arguments.flatMap(toInt(_))
arguments.flatMap(toInt(_)).sum
arguments.map(toInt(_)).flatten.sum
```


#### Concurrency
Last updated 6 days ago

##### Future and ExecutionContext
```scala
import scala.concurrent.Future
val fut = Future { Thread.sleep(10000); 21 + 21 }
​
import scala.concurrent.ExecutionContext.Implicits.global
val fut = Future { Thread.sleep(10000); 21 + 21 }
​
fut.isCompleted
new java.util.Date()
new java.util.Date()
fut.isCompleted
​
fut.value
​
import scala.util.{Success, Failure}
fut.onComplete({
  case Success(result) => println("got: " + result)
  case Failure(e) => println("failed: " + e)
})
```



##### Future transformation
```scala
val salary = Future {Thread.sleep(20000); 4000}
val bonus = 500
​
val salaryWithBonus = salary.map(value => value + 500)
salaryWithBonus
​
val productPrice = Future {Thread.sleep(10000); 150}
val productTax = Future {Thread.sleep(10000); 8.95}
​
val finalPrice = for {
  price <- productPrice
  tax <- productTax
} yield price + tax
​
finalPrice
```


##### Filtering and Collecting Futures
```scala
val salary = Future { Thread.sleep(5000); 7000 }
val salaryLarge = salary.filter(s => s > 5000)
salaryLarge
​
val salaryFuture = Future { Thread.sleep(5000); 3000 }
val salaryIncremented = salaryFuture.collect { case salary if salary < 5000 => salary + 1000 }
salaryIncremented
```


##### Other ways to model Asynchronous operation
```scala
Future.successful("yay!")
Future.failed(new Exception("boom :("))
​
import scala.concurrent.{ Future, Promise }
val promise = Promise[Int]
promise.future
promise.success(100)
promise.future
promise.future.value
```

##### Dealing with Future failures
```scala
val failedFuture = Future { 10 / 0 }
failedFuture.value
val failedException = failedFuture.failed
​
val fallbackFuture = Future.successful(100)
val computation = Future { 1 / 0} fallbackTo(fallbackFuture)
computation
​
val resultFuture = Future { 100 / 0 }
resultFuture
​
resultFuture.recover {
  case e: ArithmeticException => 0
}
```



#### What's next ??

Scala REPL
Scala API
Solve Scala programs
Ask for help


REPL (type scala and hit enter) >>> type :help

www.scala-lang.org/api/current >>> check the API

Solve S-99 problems: 
aperiodic.net/phil/scala
www.hackerrank.com/domains/fp/intro


stackoverflow.com/questions/tagged/scala

gitter.im/scala/scala




```scala

```
