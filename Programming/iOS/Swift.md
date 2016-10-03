# SWIFT

* __Variables and constants__
* __Types of data__
* __Operators__
* __String Interpolation__

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