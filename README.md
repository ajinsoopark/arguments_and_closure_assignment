# Exercises

1. Create two functions: `double` and `square`.
`double` should take a number and return the number times two.
`square` should take a number and return the number squared.

 * Create a third function `doubleSquare` that uses both of the functions to return a number that is first doubled and then squared.

 ```js
 function double (number) {
   return number * 2;
 };

 const square = (number) => {
   return number * number;
 };

 function doubleSquare (number) {
   let doubleNumber = double (number);
   return square (doubleNumber);
 };
 ```

2. Create a function `classyGreeting` that takes as input the strings `firstName`  and `lastName`,
and returns a string with a greeting using the two.

  * Create a second function `yell`  that takes string as input and returns the string in all capitalized letters.
  * Create a third function  `yellGreeting`  that will take the `firstName`  and `lastName`  as inputs and yell a greeting using the two.

```js
const classyGreeting = (firstName, lastName) => {
  return `Hello ${firstName} ${lastName}.`;
};

function yell (string) {
  let capitalizedString = string.toUpperCase();
  return capitalizedString;
};

const yellGreeting = (firstName, lastName) => {
  let capitalizedGreeting = `Hello ${firstName} ${lastName}.`.toUpperCase();
  return capitalizedGreeting;
};
```

3. The [concat](https://www.w3schools.com/jsreF/jsref_concat_array.asp) array method is used to merge two (or more) arrays.
Write a `removeDupes` function that takes an array as an argument and returns a copy without any duplicate elements.
Then, write a function `concatAndRemoveDupes`  that combines two arrays and removes any duplicates.

  _Hint:_ Use the array method `includes`, an object, or a Set. Or the spread operator instead of concat.

```js
function removeDupes (array) {
  let dupeObj = {};
  let newArray = [];
  for (let i = 0; i < array.length; i++) {
    if (!(dupeObj[array[i]])) {
      dupeObj[array[i]] = 1;
      newArray.push(array[i])}
  }
  return newArray;
};

function concatAndRemoveDupes (array1, array2) {
  array1.push(...array2);
  return removeDupes(array1);
};
```

4. Given a list of grades, we can get the median grade by sorting the list and taking the middle element, or the average of the two middle elements.
Create the functions `sort` and `middleElement`, and then use them to create the functions `median`.

let grades = [91, 85, 100, 92, 88];

console.log(median(grades)); // Should log 91

```js
const sort = (array) => {
  function sortNumber(a, b) {
    return a - b;
  };
  return array.sort(sortNumber);
};

function middleElement (array) {
  let middle = [];
  let sortedArray = sort(array);
  if (!(sortedArray.length % 2)) {
    middle.push(sortedArray[sortedArray.length / 2 - 1], sortedArray[sortedArray.length / 2])
  } else {
    middle.push(sortedArray[Math.floor(sortedArray.length / 2)])
  }
  return middle;
};

const median = (array) => {
  let medianGrade;
  let middleArray = middleElement(array);
  if (middleArray.length > 1) {
    medianGrade = (middleArray[0] + middleArray[1]) / 2;
  } else {
    medianGrade = middleArray[0]
  }
  return medianGrade;
};
```

5. Write a function called `repeat` that takes in a string and numberOfTimes. The function should log to the screen the string however
many times as numberOfTimes. If the user does not enter a numberOfTimes it should default to 2.

```js

const repeat = (string, numberOfTimes = 2) => {
  for (let i = 0; i <= numberOfTimes; i++) {
    console.log(string);
  }
  return;
};
```


6. Using the spread operator, write a function that can take any number of arguments and return the sum of all of them.

```js
function sumOfAll (...arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum = sum + arr[i];
  }
  return sum;
};
```

7. Write a function called `adder` takes in one number and returns a function that will add that number with another number.
Using `adder` create an `add5` and an `add9` function. Hint: Closures!

```js
function adder (number) {
  return (addingNumber) => {
    return number + addingNumber;
  };
};

const add5 = adder(5);
const add9 = adder(9);
```
