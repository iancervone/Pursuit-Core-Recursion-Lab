# Recursion Exercises

- ### Sum of all from 1 to n

Write a function that takes in a number as input and recursively finds the sum of all numbers up to and including that number.

```js
input: 6
output: 21

//21 = 6 + 5 + 4 + 3 + 2 + 1
```
var sum = Int()
func recursiveSum(num: Int) -> Int {
var nextNum = num - 1
if num >= 0 {
sum += num
recursiveSum(num: nextNum)
}
return sum
}
print(recursiveSum(num: 6))




- ### Multiply array

Write a function called `multArr` that takes in an array of numbers as an argument and recursively multiplies together all of the values in the array.

```js
multArr([2, 3, 5]); // returns 30
multArr([5, 5, 1, 2]); //returns 50
```

var product: Int = 1
func multArr(arr: [Int]) -> Int{
var newArr: [Int] = arr
if arr.count > 0 {
product *= newArr.removeLast()
multArr(arr: newArr)
}
return product
}
//
multArr(arr: [5, 5, 1, 2])

//QUESTION 2 (NOT A SOLUTION BUT HOW I STARTED TO APPROACH PROBLEM)
////var sum: Int = 1
////
////func multArr(arr: [Int]) -> Int{
////  let iterations: Int = arr.count
//////  var nextIndex: Int = iterations - 1
////  if iterations >= 0 {
////    sum *= arr[iterations]
////    var newArr = arr
////    newArr.remove(at: iterations)
////    multArr(arr: newArr)
////  }
////  return sum
////}
////
////multArr(arr: [2, 3, 5])
////




- ### Concatenate array

Write a function called `concatArr` that takes in an array of strings as an argument and recursively concatenates the strings together into a single string, with spaces between each original string.

```js
concatArr(['is', 'it', 'tomorrow']); // returns 'is it tomorrow'
concatArr(['or', 'just', 'the', 'end', 'of', 'time']); //returns 'or just the end of time'
```


var concatenated: String = ""
func concatArr(arr: [String]) -> String{
var newArr: [String] = arr
if arr.count > 0 {
concatenated += newArr.removeFirst() + " "
concatArr(arr: newArr)
}
return concatenated
}

concatArr(arr: ["is", "it", "tomorrow"])







- ### Sum evens

Write a function called `sumEvens` that takes in an array of numbers as an argument and recursively sums only the even numbers in the array.

```js
sumEvens([2, 3, 5, 6]); // returns 8
sumEvens([10, 5, 1, 2, 12]); //returns 24
```


var sum: Int = 0

func sumEvens(arr: [Int]) -> Int{
var newArr = arr.filter({$0 % 2 == 0})
if newArr.count > 0 {
sum += newArr.removeLast()
sumEvens(arr: newArr)
}
return sum
}

sumEvens(arr: [10, 5, 1, 2, 12])







- ### Recursive range

Write a function called `range` which takes in two numbers (num1, num2) as arguments. The function should return an array of numbers between num1 and num2.

```js
range(2,10); // returns [2, 3, 4, 5, 6,7, 8, 9, 10]
range(17,20); // returns [17, 18, 19, 20]
```

var numsBetween = [Int]()


func range(num1: Int, num2: Int) -> [Int] {
var startNum = Int()
var endNum = Int()

if num1 <= num2 {
startNum = num1
endNum = num2
numsBetween.append(startNum)
startNum += 1
range(num1: startNum, num2: endNum)
//  } else {
//    if num1 >= num2 {
//    startNum = num2
//    endNum = num1
//    numsBetween.append(startNum)
//    startNum += 1
//    range(num1: startNum, num2: endNum)
//  }
}
return(numsBetween)
}

print(range(num1: 2, num2: 10))





- ### Triple Step

A child is running up a staircase with n steps and can hop either 1 step 2 steps or 3 steps at a time. Write a function called 'tripleStep', that takes in an argument `n` that represents the number of steps in the staircase, and returns a count of how many possible ways the child can run up the stairs.

```js
tripleStep(3); //returns 4
tripleStep(4); //returns 7
tripleStep(5); //returns 13
tripleStep(10); //returns 274
```

Source: Cracking the Coding Interview

- ### Coin Combos

Given an infinite number of quarters, dimes, nickels, and pennies, write code to calculate the number of possible ways of giving exact change for `n` cents.

In other words, write a function called `coinCombos` that takes in one argument: `n`, which represents the total amount of money (in cents) that you need to make change for. Your function should return the amount of possible combinations you can make to return that exact amount of change.

For example:
```js
coinCombos(5); //returns 2
coinCombos(10); //returns 4
coinCombos(25); //returns 13
coinCombos(60); //returns 73
```

Source: CTCI

# Resources
- [JavaScript Recursion Exercises](http://www.w3resource.com/javascript-exercises/javascript-recursion-functions-exercises.php)
- [Swift Recursion Exercises](https://www.weheartswift.com/recursion/)
