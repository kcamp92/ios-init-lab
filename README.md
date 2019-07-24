# Initialization Lab


## 1: Structs Review

Download the resources at the link below:

https://developer.apple.com/go/?id=app-dev-swift-student (Links to an external site.)


Open the folder titled "2 - Introduction to UIKit" then open the folder titled "3 - Structures".  Open the Playground there, and work through the exercises.

PAGE 1
```
struct GPS {

var latitude = 0.0
var longitude = 0.0

}

var somePlace = GPS()

somePlace.latitude = 51.514004
somePlace.longitude = 0.125226

print(somePlace.longitude)
print(somePlace.latitude)


struct Books {
var title = ""
var author = ""
var pages = 0
var price = 0.0
}
var favBook = Books ()
let favBook = Books(title: "And Then There Were None", author: "Agatha Christie", pages: 250, price: 7.99)

print(favBook)
```
PAGE 2
```

struct RunningWorkout{
var distance = 0.0
var time = 0.0
var elevation = 0.0
}

let firstRun = RunningWorkout(distance: 2396, time: 15.3, elevation: 94)

firstRun.distance
firstRun.elevation
firstRun.time
print(firstRun)
```
PAGE 3
```
struct GPS2 {

var latitude: Double
var longitude: Double

init (latitude: Double, longitude: Double){
self.latitude = latitude
self.longitude = longitude
}
}

let somePlace2 = GPS2(latitude: 51.514004, longitude: 0.125226)
print(somePlace2)

//

struct Books2 {
var title:String
var author: String
var pages: Double
var price: Double

init(title: String, author: String, pages: Double, price: Double) {
self.author = author
self.pages = pages
self.price = price
self.title = title
}
}

let favBook2 = Books2(title: "And Then There Were None", author: "Agatha Christie", pages: 250, price: 7.99)

favBook2.title
favBook2.author

print("My favorite book is \(favBook2.title), by \(favBook2.author), I read it when i was in jhs")

//

struct Height {
var heightInInches: Double
var heightInCentimeters: Double

init(heightInInches: Double) {
self.heightInInches = heightInInches
self.heightInCentimeters = heightInInches * 2.54
}

init(heightInCentimeters: Double) {
self.heightInCentimeters = heightInCentimeters
self.heightInInches = heightInCentimeters / 2.54
}

}

var randoHeight = Height(heightInInches: 65)
randoHeight.heightInCentimeters

var myHeight = Height(heightInInches: 66)
myHeight.heightInCentimeters

myHeight.heightInInches

```
PAGE 4
```
struct User {
var name: String
var age: Int
var height: Double
var weight: Double
var activityLevel: Int

init(name: String, age: Int, height: Double, weight: Double, activityLevel: Int) {
self.activityLevel = activityLevel
self.age = age
self.height = height
self.name = name
self.weight = weight
}
}
let Kris = User(name: "Krystal", age: 27, height: 5.5, weight: 130, activityLevel: 5)
print(Kris)

//

struct Distance {
var meters:Double
var feet:Double

init(meters: Double) {
self.meters = meters
self.feet = meters * 3.28084
}

init(feet: Double) {
self.feet = feet
self.meters = feet / 3.28084
}
}

var mile = Distance (meters: 1600)
mile.feet

var yourDistance = Distance(feet: 430)
yourDistance.meters
```
PAGE 5
```
struct Book {
var title: String
var author: String
var pages: Int
var price: Double

init(title: String, author: String, pages: Int, price: Double) {
self.author = author
self.pages = pages
self.price = price
self.title = title
}
}
let bookDescription = Book(title: "Becoming", author: "Michelle Obama", pages: 350, price: 40.00)

print(bookDescription)

//

struct Post {
var message: String
var likes: Int
var numberOfComments: Int

init(message: String, likes: Int, numberOfComments: Int) {
self.likes = likes
self.message = message
self.numberOfComments = numberOfComments
}

mutating func Like () {
if likes > 0 {
likes += 1
}
}
}
var facebook = Post(message: "Mawnin, Mawnin", likes: 5, numberOfComments: 4)
print(facebook)

facebook.Like()
print(facebook)
```
PAGE 6
```
struct RunningWorkout2 {
var distance: Double
var time: Double
var elevation: Double

//    init(distance: Double, time: Double, elevation: Double) {
//        self.distance = distance
//        self.elevation = elevation
//        self.time = time
//    }

func postWorkoutStats() {
//return RunningWorkout2
print(RunningWorkout2(distance: 16, time: 9, elevation: 5))
}
//RunningWorkout2.postWorkoutStats()
}
var stats = RunningWorkout2 (distance: 15, time: 10, elevation: 7)
stats.postWorkoutStats()
print(stats.postWorkoutStats())

//

struct Steps {
var steps: Int
var goal: Int

mutating func takeStep () {
steps += 1
}
}
var currentSteps = Steps(steps: 77, goal: 80)

print(currentSteps.steps)
currentSteps.takeStep()
print(currentSteps.steps)
```

PAGE 7
```

struct Rectangle {
var width: Int
var height: Int
var computedProperty: Int {
get {
return width * height
}
}
}
var newRectangle = Rectangle (width: 55, height: 77)
newRectangle.computedProperty

//

struct Height {
var heightInInches: Double

var heightInCentimeters: Double

init(heightInInches: Double) {
self.heightInInches = heightInInches
self.heightInCentimeters = heightInInches*2.54
}

init(heightInCentimeters: Double) {
self.heightInCentimeters = heightInCentimeters
self.heightInInches = heightInCentimeters/2.54
}
}
```

PAGE 8
```

struct RunningWorkout3 {
var distance: Double
var time: Double
var elevation: Double
var averageMileTime: Double {
get {
return Double((distance / 1600) / ( time ))
}
}
}
var user = RunningWorkout3(distance: 3200, time: 5, elevation: 3)

user.averageMileTime

//

struct Steps {
var steps: Int
var goal: Int

mutating func takeStep() {
steps += 1
}
}
```

## 2: Classes and Inheritance

Open the folder titled "2 - Introduction to UIKit" then open the folder titled "4 - Classes and Inheritance".  Open the Playground there, and work through the exercises.

PAGE 1:
```
class Spaceship {
var name: String = ""
var health = 0
var position = 0

init(name: String, health: Int, position: Int) {
self.name = name
self.health = health
self.position = position
}

func moveLeft() {
position -= 1
}
func moveRight() {
position += 1
}

func wasHit() {
health -= 5
if health <= 0 {
print("Sorry. Your ship was hit one too many times. Do you want to play again?")
}

}
}

let falcon = Spaceship(name: "Falcon", health: 4, position: 3)
print(falcon)

falcon.moveLeft()
falcon.moveLeft()
print(falcon.position)

falcon.moveRight()
print(falcon.position)
falcon.wasHit()
print(falcon.health)
```




## BONUS: Actor mini-project

Complete each of the following exercises by creating a new Command Line App in Xcode.  Classes and structs allow us to separate out our code into multiple different files.  In you main.swift file, copy and paste the code at the link below.

 https://gist.github.com/benstone1/75ae3cf24c8cb2ade792b9c66e79ee5c



## 3

Create a new file and name it "Movie.swift".  Make sure to save it right below your main.swift file.


Inside of the Movie.swift file, create a class called Movie that has properties for name (String), year (Int), genre (String), cast ([String]), and description (String).


Inside of main.swift, populate an array of Movies converted from the array of dictionaries in the gist above.

## 4

Then, for each movie in the Movie array, print the name of each movie and associated cast on a single line. Be sure not to print the array of cast members, only the string elements.



Correct Output Examples:

Minions: Sandra Bullock, Jon Hamm, Michael Keaton
Shrek: Mike Myers, Eddie Murphy, Cameron Diaz


Incorrect Output Examples (printing an array instead of the actors joined together as a String):

Minions: ["Sandra Bullock", "Jon Hamm", "Michael Keaton"]
Shrek: ["Mike Myers", "Eddie Murphy", "Cameron Diaz"]


## 5

Let's refactor our Movie class with what we learned today.



Create a failable convenience initializer convenience init?(with dict: [String:Any]) for the Movie class that takes in a dictionary, and uses the values of the input dictionary to initialize a Movie object.



Go back to the for loop in main.swift where we iterate through the movies array. Rewrite the body of the loop such that it creates a Movie object for each dictionary in the movies array using the new convenience initializer.


## 6

Repeating the same process you used to make the Movie.swift file, create files named:

- Person.swift
- Actor.swift


In Person.swift, create a class named Person with

- A name of type String
- A birthYear of type Int
- A deathYear of type Optional Int

In Actor.swift, create a class named Actor that

- Inherits from Person
- Has a breakoutYear of type Int
- Has a breakoutRole of type String

Rewrite your Movie class to have its case property be an array of Actors instead of Strings.

## 7

Repeating the same process you used to make the Movie.swift file, create a file named:

Genre.swift

In Genre.swift, create an enumeration with raw String values with the following cases:

- animation
- action
- drama


Rewrite your Movie class to have its genre property be of type Genre instead of String.


## 8

Refactor your code and create an area of your improved Movie class out of the array of dictionaries.

Then, use your new array to complete each of the following questions:

a. Print the name of the first movie.

b. Print a list of all movie names on one line.

c. Print a list of all movie years and names (each on a new line) as follows:

2015: Minions
2001: Shrek

d. Print the title of each movie and add an appropriate emoji to represent its genre.

e. Print out the title of each movie and all of the actors that were older than 40 when then movie was made.
