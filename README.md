# Problem-Solving-Algorithms
```javascript

Create a function that takes a string and returns a string in which each character is repeated once.
Examples
"String" => "SSttrriinngg"
"Hello World!" => "HHeelllloo  WWoorrlldd!!"
"1234!_ " => "11223344!!__  "

My solution:

function doubleChar(str) {
  let final = "";
   for(let i = 0; i < str.length; i++){
      final += str[i] + str[i];
   }
  return final;
}

Alternative solution:

function doubleChar(str) {
  return str.split("").map((x) =>  x + x).join("");
}


Check If String Ending Matches Second String
Created by Matt in JavaScripton February 13th 2017
stringsvalidation
Create a function that takes a two strings and returns true if the first argument ends with the 2nd argument (also a string).
Rules
Take two strings as arguments.
Determine if second string matches ending of first string.
Return boolean value.
Examples
"abc", "bc" => true
"abc", "d" => false
"samurai", "zi" => false
"feminine", "nine" => true
"convention", "tio" => false
Gotchas
No gotchas. All test cases will be valid one word strings.


My solution: 
function checkEnding(str1, str2) {
  return str1.endsWith(str2);
}
Create a function that takes any nonnegative number as an argument and return it with it's digits in descending order. Descending order is when you sort from highest to lowest.
Examples

123 => 321
1254859723 => 9875543221
73065 => 03567
Gotchas

No gotchas. You can expect a non-negative number for all test cases.

My solution:

function sortDecending(num) {
return parseInt(num.toString().split("").sort((a,b)=>b-a).join(""))
};

Alternate solution:

function sortDecending(num) {
return parseInt(num.toString().split("").sort().reverse().join(""))
};

Silence President Trump!
Created by Matt in JavaScripton February 11th 2017
formattingfunnyregexstrings
Congratulations, you're the new CTO of Twitter. You've received direct orders from Jack Dorsey to silence Donald Trump, but not by deleting his account. How is that possible? By removing every vowel from his tweets, essentially neutering him.
Rules

Create a function that takes a string as an argument. 
Return a new string with all vowels removed.
"y" is not considered a vowel.
Examples

"This website is for losers LOL!" => "Ths wbst s fr lsrs LL!"
"Stupid nerds!" => "Stpd nrds!"
"We're gonna build a wall!" => "W'r gnn bld  wll!"
Gotchas

No gotchas. You can expect a valid string for all test cases.


My solution:

function silenceTrump(str) {
  return str.replace(/[aeiou]/ig, '');
}



Filter Strings From Array
Created by Matt in JavaScripton February 12th 2017
arraysformattingloops
Create a function that takes an array of non-negative numbers and strings and returns a new array without the strings.
Rules
Filter out all strings.
Return only numbers.
Example
[1, 2, "a", "b"] => [1, 2]
[1, "a", "b", 0, 15] => [1, 0, 15]
[1, 2, "aasf", "1", "123", 123] => [1, 2, 123]
Gotchas
Zero is a non-negative number.


My solution:

function filterArray(arr) {
  return arr.filter(num => Number.isInteger(num));
}


Alternate:


InstructionsCodeResourcesSolutionsDiscussion
function filterArray(arr) {
  return arr.filter(n => typeof n === 'number');
}


Create a function that takes a string as an argument and converts the first character of each word to uppercase. Return the newly formatted string.
Examples

"This is a title" => "This Is A Title"
"capitalize every word" => "Capitalize Every Word"
"I Like Pizza" => "I Like Pizza"
"PIZZA PIZZA PIZZA" => "PIZZA PIZZA PIZZA"
Gotchas

Don't worry about gotchas, you can expect a valid string for each lab test.


My Solution:

function makeTitle(str) {
return str.split(" ").map((item) => item[0].toUpperCase() + item.slice(1)).join(" ");

}


Sort Numbers In Ascending Order
Created by Matt in JavaScripton February 13th 2017
completearrayssorting
Create a function that takes an array of numbers and returns a new array, sorted in ascending order (smallest to biggest).
Rules
Sort numbers array in ascending order.
If functions argument is null, an empty array or undefined, return an empty array.
Return new array of sorted numbers.
Examples
[1, 2, 10, 50, 5] => [1, 2, 5, 10, 50]
[80, 29, 4, -95, -24, 85] => [-95, -24, 4, 29, 80, 85]
null => []
[] => []
Gotchas
The numbers being passed to sortNumsAscending() can be positive or negative.


My Solution: function sortNumsAscending(arr) {
  if(arr==null) return []; 
  return arr.sort((a,b) => a - b);
}


Basic E-Mail Validation
Created by Matt in JavaScripton February 11th 2017
stringsvalidation
Your job is to create a function that accepts a string as its only argument. The function will return true if the email is valid and false if it's not. Super simple.
Rules
The string must contain an " @ " character.
The string must contain a " . " character.
The "@" character must have a minimum of one character in front of it.
e@edabit.com is valid while @edabit.com is invalid.
The " . " and the "@" must be in the appropriate places.
hello.email@com is invalid while john.smith@email.com is valid.
If the string passes these tests, it will be considered a valid email.
Examples
'@gmail.com' => false
'hello.gmail@com' => false
'gmail' => false
'hello@gmail' => false
'hello@edabit.com' => true
'' => false (an empty string)
Email validation can get more complicated than what we're going for here, but this challenge will satisfy 95% of use cases. If you're unsure of something, check out the lab tests to understand exactly what's being evaluated.

My solution:

function validateEmail(str) {
  return /\w+[@]\w+[.]\w+/g.test(str);
}

Find The Minimum, Maximum, Length And Average Values
Created by Matt in JavaScripton February 11th 2017
arraysvalidation
Create a function that takes an array of numbers and returns the  following statistics:
Minimum Value
Maximum Value
Sequence Length
Average Value
Examples
[6, 9, 15, -2, 92, 11] => [-2, 92, 6, 21.833333333333332]
[30, 43, 20, 92, 3, 74] => [3, 92, 6, 43.666666666666664]
[4.54, 8.32, 5.20] => [4.54, 8.32, 3, 6.02]
Gotchas
No gotchas. You don't even have to round the average.

My solution:

function minMaxLengthAverage(arr) {
  let solution = [];
solution.push(Math.min(...arr));
solution.push(Math.max(...arr));
solution.push(arr.length);
solution.push(arr.reduce((a, b)=>a+b) / arr.length);
return solution;
}

Alternate solution:

function minMaxLengthAverage(arr) {
 return [
 Math.min(...arr),
 Math.max(...arr),
 arr.length,
 arr.reduce((a,b)=>a+b) /arr.length
 ]
```
