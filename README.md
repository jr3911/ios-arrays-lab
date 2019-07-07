# Arrays lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.

## Question 1

Create an array of strings called `colors` that contain "orange", "red", "yellow", "turquoise", and "lavender".

Then, using array subscripting and string interpolation, print out the String `"orange, yellow, and lavender are some of my favorite colors"`.

```swift
var colors: [String] = ["orange", "red", "yellow", "turquoise", "lavender"]

print("\(colors[0]), \(colors[2]), and \(colors.last!) are some of my favorite colors")

```


## Question 2

Remove "Illinois" and "Kansas" from the array below.

```swift
var westernStates = ["California", "Oregon", "Washington", "Idaho", "Illinois", "Kansas"]

var index = 0

for currentState in westernStates {
    if westernStates[index] == "Illinois" || westernStates[index] == "Kansas" {
        westernStates.remove(at: index)
    } else {
        index += 1
    }
}

print(westernStates)
```

## Question 3

Iterate through the array below. For each state, print out the name of the state, a colon, and whether it is or is not **in the continental United States.**

`let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]`


```swift
let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]
var isInContinent = ["New Mexico", "Montana", "Texas", "New York", "Florida"]
var verification: Bool = false

for currentState in moreStates {
    verification = false
    for compareState in isInContinent {
        if currentState == compareState {
            verification = true
            if verification == true {
                print("\(currentState): is in the continental United States")
            }
            break
        }
    }
    if verification == false {
        print("\(currentState): is not in the continental United States")
    }
}
```

## Question 4

Print out how many non-whitespace characters are in `myString`:

`let myString = "This is good practice with Strings!"`

Iterate through the array below. For each sentence, print out how many non-whitespace characters are in it.

`let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]`


```swift
let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]

var numNonWhiteSpaces = 0

for quote in myFavoriteQuotes {
    numNonWhiteSpaces = 0
    for char in quote {
        if char != " " {
            numNonWhiteSpaces += 1
        }
    }
    print("There are \(numNonWhiteSpaces) non-whitespace characters in quote :\(quote)")
}
```

## Question 5

Iterate through `garden` and place any 🌷 that you find into the `basket`. Replace any 🌷 that you pick up with `"dirt"`. Then print how many 🌷 are in your `basket`.

```swift
var garden = ["dirt","🌷","dirt","🌷","dirt","dirt","🌷","dirt","🌷","dirt"]
var basket = [String]()
var index = 0

for iteration in index..<garden.count {
    if garden[index] == "🌷" {
        basket.append(garden[index])
        garden[index] = "dirt"
        index += 1
    } else {
        index += 1
    }
}

print("\(basket)    There are \(basket.count) flowers in the basket")
print(garden)

```

## Question 6

The below array represents an unfinished batting lineup for a baseball team. **You, the coach,** need to make some last minute changes:

- Add "Suzuki" to the end of your lineup.
- Change "Jeter" to "Tejada".
- Change "Thomas" for "Guerrero"
- Put "Reyes" to bat 8th instead.

`var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]`


```swift
var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]
var index = 0
var findReyes = index

battingLineup.append("Suzuki")

for player in battingLineup {
    if player == "Reyes" {
        findReyes = index
    } else if player == "Jeter" {
        battingLineup[index] = "Tejada"
    } else if player == "Thomas" {
        battingLineup[index] = "Guerrero"
    }
    index += 1
}

battingLineup.swapAt(findReyes, 7)

print(battingLineup)
```

## Question 7

Given an array of Ints, find out if it contains a target number.  

(The built-in `contains(_:)` function will do this, but you aren't allowed to use it for this exercise.)


```swift
// The array "numbers" must be initialized or assigned a value first before use
var numbers: [Int]

let target: Int = 32

var targetAcquired = false

for currentNum in numbers {
    if currentNum == target {
        targetAcquired = true
        break
    }
}

print(targetAcquired)
```

Ex.1

```swift
numbers = [4,2,6,73,32,4,2,1]

target = 32

//true
```

Ex. 2

```swift
numbers = [32459,2,4,5,1,4,2,1]

target = 3

//false
```


## Question 8

Find the largest value in an array of Int.  Do not use the built-in `max()` method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

var largestNum = arrayOfNumbers[0]

for num in arrayOfNumbers {
    if num > largestNum {
        largestNum = num
    }
}

print(largestNum)
```


## Question 9

Find the smallest value in an array of Int.  Do not use the built in min() method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

var smallestNum: Int = arrayOfNumbers[0]

for num in arrayOfNumbers {
    if num < smallestNum {
        smallestNum = num
    }
}

print(smallestNum)
```


## Question 10

Iterate through `secondListOfNumbers`, and print out all the odd numbers.

```swift
var secondListOfNumbers = [19,13,14,19,101,10000,141,404]
var onlyOddNumsKept: [Int] = []

for index in 0..<secondListOfNumbers.count {
    if secondListOfNumbers[index] % 2 == 1 {
        onlyOddNumsKept.append(secondListOfNumbers[index])
    }
}
print(onlyOddNumsKept)
```


## Question 11

Iterate through `thirdListOfNumbers`, and print out the sum.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`

```swift
var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]
print(thirdListOfNumbers.reduce(0,+))

```
## Question 12

Iterate through `thirdListOfNumbers`, and print out the sum of all the even numbers.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`


```swift
var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]
var onlyEvens: [Int] = []

for num in thirdListOfNumbers {
    if num % 2 == 0 {
        onlyEvens.append(num)
    }
}
print(onlyEvens.reduce(0,+))
```

## Question 13

Append every Int that appears in both `listOne` and `listTwo` to the `sharedElements` array. Then print **how many Ints** are shared.

```swift
var listOne = [28, 64, 7, 96, 13, 32, 94, 11, 80, 68]
var listTwo = [18, 94, 48, 6, 42, 68, 79, 76, 13, 7]
var sharedElements = [Int]()

for num1 in listOne.sorted() {
    for num2 in listTwo.sorted() {
        if num1 == num2 {
            sharedElements.append(num1)
        }
    }
}
print("Number of shared integers: \(sharedElements.count)")
print(sharedElements)

```


## Question 14

Write code such that `noDupeList` has all the same Ints as `dupeFriendlyList`, but has no more than one of each Int.

```swift
var dupeFriendlyList = [4,2,6,2,2,6,4,9,2,1]
var noDupeList: [Int] = []

for num in dupeFriendlyList {
    if noDupeList.contains(num) == false {
        noDupeList.append(num)
    }
}
print(noDupeList)
```

## Question 15

Find the second smallest number in an Array of Ints

`let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}`


```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}
var sortedArrayOfNumbers = arrayOfNumbers.sorted()

var smallestNum: Int = sortedArrayOfNumbers[0]
var secondSmallestNum: Int = 0

for num in sortedArrayOfNumbers {
    if num != smallestNum {
        secondSmallestNum = num
        break
    }
}
print(secondSmallestNum)
```


## Question 16

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all the multiples of 3 or 5 below 1000.


```swift
var range = 3..<1000
var sum = 0

for num in range {
    if num % 3 == 0 || num % 5 == 0 {
        sum += num
    }
}
print(sum)
```

## Question 17

Make an array that contains all elements that appear **more than twice** in `someRepeatsAgain`.

```swift
var someRepeatsAgain = [25,11,30,31,50,28,4,37,13,20,24,38,28,14,44,33,7,43,39,35,36,42,1,40,7,14,23,46,21,39,11,42,12,38,41,48,20,23,29,24,50,41,38,23,11,30,50,13,13,16,10,8,3,43,10,20,28,39,24,36,21,13,40,25,37,39,31,4,46,20,38,2,7,11,11,41,45,9,49,31,38,23,41,16,49,29,14,6,6,11,5,39,13,17,43,1,1,15,25]

var sortedSomeRepeatsAgain = someRepeatsAgain.sorted()
var repeaters: [Int] = []
var preceedingNum: Int = sortedSomeRepeatsAgain[0]
var counter = 0

for num in sortedSomeRepeatsAgain {
    if num == preceedingNum {
        counter += 1
        if counter > 2 && repeaters.contains(num) == false {
            repeaters.append(num)
            counter = 0
        }
    } else {
        counter = 0
    }
    preceedingNum = num
}
print(repeaters)
```


## Question 18

Identify if there are 3 integers that sum to 10 in the following array. If so, print them as a triplet. If there are multiple triplets, print all possible triplets.

`var tripleSumArr = [-20,-14, -8,-5,-3,-2,1,2,3,4,9,15,20,30]`

```swift
var tripleSumArr = [-20,-14, -8,-5,-3,-2,1,2,3,4,9,15,20,30]

for num1 in tripleSumArr {
    for num2 in tripleSumArr {
        for num3 in tripleSumArr {
            if num1 + num2 + num3 == 10 {
                print("\(num1), \(num2), \(num3)")
            }
        }
    }
}
```

## Question 19

Given an array of Strings, find the the String with the most "a"s in it.

input: `["apes", "abba", "apple"]`

output: `"abba"`


```swift
var array = ["apes", "abba", "apple"]
var previousCounter = 0
var currentCounter = 0
var mostA: String = ""

for word in array {
    for char in word {
        if char == "a" {
            currentCounter += 1
        }
    }
    if currentCounter > previousCounter {
        mostA = word
    }
    previousCounter = currentCounter
    currentCounter = 0
}
print(mostA)
```
## Question 20

Given an Array of Arrays of Ints, find the Array of Ints with the largest sum:

Input: `[[2,4,1],[3,0],[9,3]]`

Output: `[9,3]`

```swift
var matrix = [[2,4,1],[3,0],[9,3]]
var largestSum: Int = 0
var arrayWithLargestSum = [Int] ()

for array in matrix {
    var sum = array.reduce(0,+)
    if largestSum < sum {
        largestSum = sum
        arrayWithLargestSum = array
    }
}
print(arrayWithLargestSum)
```

## Question 21

Given an Array of Tuples of type `(Int, Int)`, create an array containing all the tuples where the first Int is equal to the second Int.

Input: `[(4,2), (-3,-3), (1,1), (3,9)]`

Output: `[(-3,-3), (1,1)]`

```swift
let array = [(4,2), (-3,-3), (1,1), (3,9)]
var onlyIdenticals = [(Int,Int)] ()

for tuple in array {
    if tuple.0 == tuple.1 {
        onlyIdenticals.append(tuple)
    }
}
print(onlyIdenticals)
```

## Question 22

Given an Array of Bools, make a variable called `allAreTrue` that is true if all of the Bools are true and false if any of them are false.

Input: `[true, false, true, true]`

Output: `false`

```swift
var input = [true, false, true, true]
var allAreTrue = Bool ()

for index in 0..<input.count {
    if input[index] == false {
        allAreTrue = false
        break
    } else {
        allAreTrue = true
    }
}
print(allAreTrue)
```

## Question 23

Given an Array of Ranges of Ints, create an array that has all the values from all the ranges in order from smallest to greatest with no duplicates.

Input: `[0..<3 , 2..<10, -4..<6, 13..<14]`

// typo in output, 10 is not included in ranges from input
Output: `[-4,-3,-2,-1,0,1,2,3,4,5,6,7,8,9,10,13]` 


```swift
var arrRanges = [0..<3 , 2..<10, -4..<6, 13..<14]
var allValuesInRanges = [Int] ()

for range in arrRanges {
    for value in range {
        if allValuesInRanges.contains(value) == false {
            allValuesInRanges.append(value)
        }
    }
}
var sortedRanges = allValuesInRanges.sorted()
print(sortedRanges)
```
## Question 24

Given an array of Characters, create a String ignoring and uppercase Characters and spaces.  Then uppercase every other character of the String.

Input: `let arr: [Character] = ["a", "p","P","l","E"," ","S","a","u","C,"e"]`

// typos: first "e" in "ApLeAuE" should not be in there because "E" is ignored, missing " after "C in input
Output: `"ApLeAuE"`

```swift
let arr: [Character] = ["a", "p","P","l","E"," ","S","a","u","C","e"]
let ignore = "ABCDEFGHIJKLMNOPQRSTUVWXYZ "
var spongeBobText = ""
var index = 0

for char in arr {
    if ignore.contains(char) == true {
        continue
    } else {
        spongeBobText.append(char)
    }
}

var textArr: [Character] = Array(spongeBobText)

for letter in textArr {
    if index % 2 == 0 {
        textArr[index] = Character(String(letter).uppercased())
    }
    index += 1
}

spongeBobText = String(textArr)

print(spongeBobText)
```
## Question 25

Print out each element in `myMatrix`

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`

```swift
var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]

// prints each array in its entirety
for array in myMatrix {
    print(element)
}

// prints each element in each array in the matrix
for array in myMatrix {
    for value in array {
        print(value)
    }
}

```

## Question 26

Print out the sum of the diagonals of `myMatrix`.

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`

```swift
var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]
var sum1 = Int ()
var sum2 = Int ()
var downwardRightIndex = 0
var leftDownwardIndex = myMatrix[0].count - 1

for arr in myMatrix {
    // calculates sum for diagonal going from top left to bottom right
    sum1 += arr[downwardRightIndex]
    downwardRightIndex += 1
    // calculates sum for diagonal going from top right to bottom left
    sum2 += arr[leftDownwardIndex]
    leftDownwardIndex -= 1
}
print(sum1)
print(sum2)
```

## Question 27

Using for loops, rotate `matrixToRotate` 90 degrees.

var matrixToRotate = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

![Matrix Rotation](images/rotated_matrix.jpeg)

```swift
// flaw is that input needs to be perfect square in order to work
var matrixToRotate = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
var rotatedMatrix  = Array(repeating: Array(repeating: 0, count: matrixToRotate[0].count), count: matrixToRotate.count)
var columnIndex = matrixToRotate[0].count - 1

for array in matrixToRotate {
    var indexForRotatedMatrix = 0
    var rowIndex = 0
    for value in array {
        rotatedMatrix[indexForRotatedMatrix][columnIndex] = value
        indexForRotatedMatrix += 1
        rowIndex += 1
    }
    columnIndex -= 1
}
print(rotatedMatrix)
```
