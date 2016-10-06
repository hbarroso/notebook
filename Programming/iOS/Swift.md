# SWIFT
* __Introduction to Swift__
	* __Variables and constants__
	* __Types of data__
	* __Operators__
	* __String Interpolation__
	* __Arrays__
	* __Arrays operators__
	* __Dictionaries__
	* __Conditional Statements__
	* __Loops__
	* __Loops over arrays__
	* __While loops__
	* __Switch case__
	* __Functions__
	* __External and internal parameter names__
	* __Return values__
	* __Optional Chaining__
	* __The nil coalescing operator__

### Variables and constants

Variables can be changed while constants are read-only values.
Variables are defined by `var` keyword while constants by `let`.

__Variable__ 

```swift
var name = "Henrique"
name = "Barroso" // and we can alter it at some later stage
``` 

__Constant__

```swift
let name = "Henrique"
name = "Barroso" // This will not work
```

* We should always pick `constants` if we know the value will not change. This is allow Xcode to apply optimizations that will make our code run faster.

### Types of Data

There's __two__ ways for defining what type of data a variable can hold.

__Type inference__

```swift
var name = "Henrique" 	// Swift can infer what data type hsould be used for this variable
```

__Type annotation__ 

```swift
var name: String
name = "Henrique"

var age: Int
age: 25
```

But we can also use both

```swift
var name: String = "Henrique Barroso" // Just one line of code
```

__Other types__

`Float`, `Double`, `Bool`. 

* `Float` and `Double` are very similar, however __Apple__ recommends using `Double` because it has the highest accurancy.


### Operators

__Math__ 

```swift
var a = 10

// add
a = a + 1
a += 1

// subtract
a = a - 1
a -=1

// Multiply
a = a * 2
a *= 2

// Divide
a = a / 3
a /= 3

// Modulus
9 % 3
``` 

__String concatenation__

```swift
var firstName = "Henrique"
var fullName = firstname + " Barroso" // "Henrique Barroso"
```

__Comparation operators__

```swift
var a = 1.1
var b = 2.2
var c = a +b

c > 3 		// greater than
c >= 3		// greater than or equal
c <	 3		// less than
c <= 3		// less than or equal
c == 3		// equal
c != 3		// not equal

var iLikeSwift = true
iLikeSwift // true
!iLikeSwift // false
```

* `String` comparations are __case-sensitive__ `Henrique Barroso` is __not__ equal to `HENRIQUE BARROSO`.

### String interpolation

```swift
var name = "Henrique Barroso"
var greetings = "Hello \(name)" // "Hello Henrique Barroso"
```

### Arrays

Like in simple data types (string, int, bool, etc..), Swift use __type inference__ to figure out what type of that an array holds.

````swift
var evenNumbers = [2, 4, 6, 8] // array of ints
var songs = ["Shake it Off", "Happy", "Comfortably Numb"] // array of strings
````

We can also use __type annotation__ to define an array

```swift
var names: [String] =  ["Shake it Off", "Happy", "Comfortably Numb"]
```

Because Swift is a type safe language we can't mix different data types with __type inference__. We must use the `Any` data type. A special type can hold any value.

```swift
var stuff: [Any] = [1, "Hello", false, 5.67]
```

Creating empty arrays to be filled later:

```swift
var songs: [String] // This wont work!!!

var songs: [String] = [] // This is ok
var songs: [String]() // Better
```

### Array operators

Like in __string concatenation__ we can also use operators to combine one or more arrays.

```swift
var numbers1 = [1, 2, 3]
var numbers2 = [3, 5, 6]

var allNumbers = numbers1 + numbers2 // [1, 2, 3, 4, 5, 6]

allNumbers += [7, 8] // [1, 2, 3, 4, 5, 6, 7, 8]
```

### Dictionaries

Defining and accessing dictionary:

```swift
var person = ["first": "Henrique", "last": "Barroso", "month": "July"]

person["first"] // "Henrique"
```

Like in array can also use __type annotation__ to specify what the type of data it holds:

```swift
var person: [String:String] = ["first": "Henrique", "last": "Barroso", "month": "July"]
var stuff: [String:Any] = ["age": 35, "street": "Foo dummy street 45", "hired": true]
```

### Conditional Statements

The `if`statement:

```swift
var person = "henrique"

if person == "henrique" {
	// something
} else if person == "barroso" {
	// something
} else {
	// something
}
```

### Loops

The `for` loop:

```swift
// This will print out 10 lines from 1 to 10
for i in 1 ... 10 {
	print("\(i) x 10 is \(i * 10)")
}
```

The `for` loop with __half open range__ operator, works as te regular `for` but exludes the last element:

```swift
for i in 1 ..< 5 {
	print(" fake") 
}
// "fake fake fake fake"
```

### Looping over arrays

```swift
var songs = ["Shake it off", "You belong to me" , "Back to December"]

for song in songs {
	print("My favourite song is \(song)")
}
```

we can also use the regular `for i in` with __arrays__:

```swift
var people = ["players", "haters", "heart-breakers", "fakers"]
var actions = ["play", "hate", "break", "fake"]

for i in 0 ..< people.count {
    print("\(people[i]) gonna \(actions[i])")
}
```

### While loops

```swift
var counter = 0

while true {
	print("Counter is now \(counter)")
	counter += 1
	
	if counter == 556 {
		break
	}
}
```

#### Switch case

In `switch` statements `default` is mandatory in order to ensure all cases are exhaustive.

```swift
let liveAlbums = 2

switch liveAlbums {
	case 0:
		print("You're just starting out")
		
	case 1:
		print("You just release iTunes love from soho")
		
	case 3:
		print("You just released speak now world tour")
		
	default:
		print("Have you done something new?")
}
```

We can also apply ranges of values in `switch` statements.

```swift
	
let cookiesEaten = 5

switch cookiesEaten {
	case 0...1:
		print("You are on a diet or something?")

	case 2..3:
		print("Good snack!")
		
	case 3..5:
		print("Ok, control yourself man!")
		
	default:
		print("OMG you are the cookie monster")
}

```

* In switch statements we __don't__ need to use `break` after each case like in other languages. Instead we use the `fallthrough` keyword to make one case fall into the next.


### Functions

```swift

// Simple function
func favouriteAlbum() {
	print("My favourite is Dark Side of the Moon")
}

// parameters
function sayMyName(name: String) {
	print("Your name is \(name)");
}

sayMyName(name: "Henrique") // "Your name is Henrique"
```

### External and internal parameter names

This technique allows to expose a parameter name that will have a different name inside the functions scope.

```swift
function countLettersInString(myString str: String) {
	print("The string\(str) has \(str.characters.count) letters.")
}
countLettersInString(myString: "Hello")
```

We can also use `_` as the external parameter name. Which tells Swift that it shouldn't have any external name at all.

```swift
func countLettersInString(_ str: String) {
	print("The string\(str) has \(str.characters.count) letters.")
}
countLettersInString("Hello")
```

### Return values

Return values type will ensure that our functions always return the same data type. This is done by appending `-> TYPE` to our functions.

```swift
func nameIsValid(name: String) -> Bool {
	if name == "Henrique" { return true }
	if name == "Barroso" { return true }
	
	return false
}
```

### Optionals

An optional value is one that __might__ have a value or __not__.
This is useful for cases where we don't have 100% sure that a function or variable will have the date type value we asked. For those cases Swift created optionals which will return `nil`.

```swift
// We add a ? to our return data type to let the 
// compiler know this might return a nil instead of a String
func getHaterStatus(weather: String) -> String? {
	if weather == "sunny" {
		return nil
	} else {
		return "Hate"
	}
}
```

Because Swift is a very safe language, it doesn't allows us to use `nil` as if it were a `String` object. So we need to check if the data we are fetching is ready to be used or not.

```swift
var status: String
status = getHaterStatus(weather: "rainy") // This will throw a compiler error

var status: String? // We need to declare this a optinal String
status = getHaterStatus(weather: "rainy")
```

However, whenever we use a __optional__ data type we can't use it directly. We need to __unwrap__ it first.
Swift has two ways for dealing with this:

First: __Optional Unwrapping__ with `if let` statement which allows to safe manipulate these Optionals.

```swift
// Safe way to check if an optional is ready or not
if let unwrappedStatus = status {
	//  unwrappedStatus contains a non-optional value now!
} else {
	// Watch out, we have a nil here
}
```

Second: __force unwrapping optionals__. By using an exclamation `!` character we can tell swift to simply return the unwrapped value.

```swift
func getAlbumYear(name: String) -> Int? {
	if name == "foo" { return 1991 }
	if name == "bar" {return 1995 }
	
	return nil
}

var year = getAlbumYear(name: "foo")

// Safe
if year == nil {
	print("There was an error")
} else {
	print("It was released in \(year!)")
}

// This is madness, we are not sure year is not nil. Do not do this.
print("It was released in \(year!)")

```

* __warning__: you should only do this, if you are 100% sure the returned value is not `nil` otherwise the app can crash because if you use it directly without confirming is not `nil`.


### Optional Chaining

Optional chaining lets us run code __only__ if our optional has a value.
This is useful when we are trying to access methods from objects that maybe wrapped inside an __optional__.

```swift

func albumReleased(year: Int) -> String? {
    switch year {
    case 2006: return "Taylor Swift"
    case 2008: return "Fearless"
    case 2010: return "Speak Now"
    case 2012: return "Red"
    case 2014: return "1989"
    default: return nil
    }
}

let album = albumReleased(year: 2006)
print("The album is \(album)") // The album is Optional("Taylor Swift")
```

If we wanted to use some `String` class method for the returned value we could do:

```swift
print(album.uppercased())
```

Except we couldn't, because `album` is an optional, if the `albumReleased` returned `nil` we couldn't access `uppercased()` method.

The way swift handles this is this:

```swift
print(album?.uppercased()) // notice the ?
```

What this does it first check if `album` can be unwrapped into a `String` and only then it calls `uppercased()` otherwise it just defaults to `nil`.

This is useful especially when we have more chanining in place eg:

```swift
album?.someOtherOptional?.moreOptionals?.whatever
```

Swift will checkf from __left__ to __right__ until it find `nil`, at which point it stops.


### The nil coalescing operator

```swift

let bar = albumReleased(year: 2006) ?? "unkown album"

```

This basically says: "if the returned value is a string print it, otherwise if nil print unknown album".

### Enumerations
