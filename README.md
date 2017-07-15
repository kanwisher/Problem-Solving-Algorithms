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
 
 
 X's And O's
Created by Matt in JavaScripton February 13th 2017
conditionssortingstrings
Create a function that takes a string, checks if it has the same number of 'x's and 'o's and returns either true or false.
Rules
Return a boolean value (true or false).
The string can contain any character.
When no x or o is in the string, return true.
Examples
"ooxx" => true
"xooxx" => false
"ooxXm" => true (case insensitive)
"zpzpzpp" => true (returns true if no x and o)
"zzoo" => false
Gotchas
Remember to return true if there aren't any x's or o's.
Must be case insensitive.

My solution: (oooh this is ugly)

function XO(str) {
  console.log(str);
  let xCount = str.toLowerCase()
    .split("")
    .filter((letter)=> letter === "x")
    .join("");
  
  let oCount = str.toLowerCase()
    .split("")
    .filter((letter)=> letter === "o")
    .join("");
  
  console.log(xCount.length);
	console.log(oCount.length);
  
  if(xCount.length === 0 && oCount.length === 0){
    return true;
  } else if (xCount.length === oCount.length){
    return true;
  }else {
    return false;
  }
}


alternate solution:

function XO(str) {
  let x = str.toLowerCase().split('').filter(x => x === 'x').length;
  let o = str.toLowerCase().split('').filter(x => x === 'o').length;
  return x === o;
}

Capitalize The Names
Created by Matt in JavaScripton February 18th 2017
arraysformattingloops
Create a function that takes an array of names and returns an array with the first letter capitalized.
Rules
Return an array.
Don't change the order of the original array.
Examples
['mavis', 'senaida', 'letty'] => ['Mavis', 'Senaida', 'Letty']
['samuel', 'MABELLE', 'letitia', 'meridith'] => ['Samuel', 'Mabelle', 'Letitia', 'Meridith']
['Slyvia', 'Kristal', 'Sharilyn', 'Calista'] => ['Slyvia', 'Kristal', 'Sharilyn', 'Calista']

My solution:

function capMe(arr) {
	return arr.map(function (item) {
                 let splitArray = item.toLowerCase().split('');
  		 splitArray[0] = splitArray[0].toUpperCase();
  		 return splitArray.join('')
  });
}

alternate solution:

function capMe(arr) {
	return arr.map(x => x = x[0].toString().toUpperCase() + x.substring(1).toLowerCase());
}

Positive Count / Negative Sum
Created by Matt in JavaScripton February 12th 2017
completearraysconditions
Create a function that takes an array of positive and negative numbers. Return an array where the first element is the count of positive numbers and the second element is the sum of negative numbers.
Examples
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15] => [10, -65]
[92, 6, 73, -77, 81, -90, 99, 8, -85, 34] => [7, -252]
[91, -4, 80, -73, -28] => [2, -105]
Gotchas
If the input array is empty or null, return an empty array

My solution:

function countPosSumNeg(nums) {
 	if(!nums || !nums.length) return [];
  posTotal = nums.filter((num) => num >= 0).length;
  negTotal = nums.filter((num) => num < 0).reduce((total, nim) => total += nim);
  return [posTotal, negTotal];

}

Return The Middle Character(s) In A String
Created by Matt in JavaScripton February 12th 2017
formattingmathstrings
Create a function that takes a string and returns the middle character(s). If the word's length is odd, return the middle character. If the word's length is even, return the middle two characters.
Examples
"test" => "es"
"testing" => "t"
"middle" => "dd"
"A" => "A"
Gotchas
No gotchas. All test cases contain a single word (as a string).

My solution:
function getMiddle(str) {
  let firstLetter = str.length / 2
  if(str.length % 2 === 0){    
    return str.substring(firstLetter - 1, firstLetter + 1);
  }else{
    return str.charAt(firstLetter);
  }
}

Alternate solution:

function getMiddle(str) {

  if(str.length % 2){    
    return str.charAt((str.length-1) / 2);
  }else{
    return str.substr((str.length - 2) / 2, 2); //substr() is more in line with what I needed!
  }
}

Create a function that returns true if a number is a prime, and false if it is not. A prime is a natural number that is only divisible by 1 and itself. 
Examples:
7 => true
9 => false
10 => false

My solution:

function isPrime(num){
  if(num < 2) return false;
  for(let i = 2; i < num; i++){
    if(num % i === 0){
      return false;
    	}     
    }
 return true;
}
  
  Calculate The Mean Average
Created by Matt in JavaScripton February 12th 2017
math
Create a function that takes an array of numbers and returns the mean average (fixed to two decimal places).
Rules
Return mean average.
Round to two decimal places.
Examples
[1, 0, 4, 5, 2, 4, 1, 2, 3, 3, 3] => 2.54
[2, 3, 2, 3] => 2.50
[3, 3, 3, 3, 3] => 3.00
Gotchas
No gotchas. You can expect an integer ranging from 0 to 10000.

My solution: (after a few hiccups!);

function mean(arr) {
  return parseFloat((arr.reduce((a, b) => a + b) / arr.length).toFixed(2));
}


Phone Number Formatting
Created by Matt in JavaScripton February 12th 2017
arraysformatting
Create a function that accepts an array of 10 integers (between 0 and 9) and returns a string of those numbers in the form of a phone number.
Examples
[1, 2, 3, 4, 5, 6, 7, 8, 9, 0] => "(123) 456-7890"
[5, 1, 9, 5, 5, 5, 4, 4, 6, 8] => "(519) 555-4468"
[3, 4, 5, 5, 0, 1, 2, 5, 2, 7] => "(345) 501-2527"
Gotchas
Don't forget the space after the closing parenthese.

My solution: (struggled with eloquent solution)


function formatPhoneNumber(numbers) {
  return numbers.join('').replace(/(...)(...)(....)/, '($1) $2-$3');
}

Return The Sum Of The Two Smallest Numbers
Created by Matt in JavaScripton February 14th 2017
arraysmath
Create a function that takes an array of numbers and returns the sum of the two lowest positive integers. No floats or empty arrays will be used in any of the test cases.
Examples
[19, 5, 42, 2, 77] => 7
[10, 343445353, 3453445, 3453545353453] => 3453455
[2, 9, 6, -1] => 8
[879, 953, 694, -847, 342, 221, -91, -723, 791, -587] => 563
[3683, 2902, 3951, -475, 1617, -2385] => 4519
Gotchas
Don't count negative integers.

my solution:

function sumTwoSmallestNums(arr) {
  let sortedArray =  arr.filter((index) => index >= 0).sort((a,b) => a - b);
  return sortedArray[0] + sortedArray[1];
}


Return The Objects Keys And Values
Created by Matt in JavaScripton February 13th 2017
formattingobjects
Create a function that takes an object and returns the keys and values as separate arrays.
Examples
{a: 1, b: 2, c: 3} => [["a", "b", "c"], [1, 2, 3]]
{a: "Apple", b: "Microsoft", c: "Google"} => [["a", "b", "c"], ["Apple", "Microsoft", "Google"]]
{key1: true, key2: false, key3: undefined} => [["key1", "key2", "key3"], [true, false, undefined]]
Gotchas
No gotchas. Expect all test cases to contain valid objects.

My solution:

function keysAndValues(obj) {
  let keyArray = [];
  let propertyArray = [];
  for(prop in obj){
    keyArray.push(prop)
    propertyArray.push(obj[prop])
  }
  return [keyArray, propertyArray];
}


#Task:

Mr. despair wants to jump off Dutch act, So he came to the top of a building.

Scientific research shows that a man jumped from the top of the roof, when the floor more than 6, the person will often die in an instant; When the floor is less than or equal to 6, the person will not immediately die, he would scream. (without proof)

Input: ```floor```, The height of the building (floor)

Output: a string, The voice of despair(When jumping Dutch act)
#Example:

sc(2)  should return ```"Aa~ Pa! Aa!"```

It means: 
```
Mr. despair jumped from the 2 floor, the voice is "Aa~"
He fell on the ground, the voice is "Pa!"
He did not die immediately, and the final voice was "Aa!"
```
sc(6)  should return ```"Aa~ Aa~ Aa~ Aa~ Aa~ Pa! Aa!"```

sc(7)  should return ```"Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Pa!"```

sc(10)  should return ```"Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Pa!"```

if ```floor```<=1, Mr. despair is safe, return ```""```

My solution:

function sc(floor){
  let answer = "";
  
  if(floor > 6){
    for(let i = 1; i < floor; i++){
      answer += "Aa~ ";
    }
    answer += "Pa!";
   }
   
   if(floor <= 6 && floor > 1){
      for(let i = 1; i < floor; i++){
        answer += "Aa~ ";
      }
      answer += "Pa! Aa!";
   }
        
  return answer;
}

better solution:

function sc(floor) {
  if (floor <= 1) return "";
  var SCREAM = "";
  for (let i = 0; i < floor - 1; i++) {
    SCREAM += "Aa~ ";
  }
  SCREAM += "Pa!";
  if (floor <= 6) SCREAM += " Aa!";
  return SCREAM;
}

How many bees are in the beehive?

bees can be facing UP, DOWN, LEFT, or RIGHT
bees can share parts of other bees
Examples

Ex1

bee.bee     
.e..e..
.b..eeb
Answer: 5

Ex2
bee.bee     
e.e.e.e
eeb.eeb
Answer: 8

Notes

The hive may be empty or null
Python: the hive is passed as a list of lists (not a list of strings)
FUNDAMENTALS

My solution: (definitely my most time consuming algo to date)


howManyBees = function(hive) {
  let hiveCount = 0;  
  
  
  if(hive === null || hive.length === 0){
    return 0;
  }  
  

  for(let i = 0; i < hive.length; i++){ //horizontal test
    
    for(let j = 0; j < hive[i].length - 2; j++){
    
      let horizontalTest = hive[i].slice(j, j + 3).join("");
      
      console.log("horizontalTest results: " + horizontalTest);

      
   
     
       if(horizontalTest === "eeb" || horizontalTest === "bee"){
                hiveCount++
                console.log(hiveCount);
              }
    }
  }
    
    for(let i = 0; i < hive[0].length; i++){
         let verticalTest = "";
          for(let j = 0; j < hive.length; j++){
            verticalTest += hive[j][i];              
             
          } 
          tester(verticalTest);
    }
    
    function tester(value){
            for(i = 0; i < value.length - 2; i++){
            let hereWeGo = value.substr(i, 3);
            
            console.log(hereWeGo);
            
             if(hereWeGo === "eeb" || hereWeGo === "bee"){
                hiveCount++
                console.log(hiveCount);
              }
            }
      }
      
          
 return hiveCount;
  
  
  Eloquent solution: (not my own)
  
  howManyBees = function(hive) {
    if(!hive){
        return 0;
    }
    var count = 0;
    for(var i=0;i<hive.length;i++){
        for(var j=0;j<hive[i].length;j++){
            if(hive[i][j] === "b"){
                if(hive[i-2] && hive[i-1][j] === "e" && hive[i-2][j] === "e"){
                    count++;
                }
                if(hive[i][j+1] === "e" && hive[i][j+2] === "e"){
                    count++;
                }
                if(hive[i+2] && hive[i+1][j] === "e" && hive[i+2][j] === "e"){
                    count++;
                }
                if(hive[i][j-1] === "e" && hive[i][j-2] === "e"){
                    count++;
                }
            }
        }
    }
    return count;
}
}

Merge Two Arrays
Created by Matt in JavaScripton February 12th 2017
arraysformattingloops
Create a function that takes two arrays and combines them by alternatingly taking elements from each array in turn.
Rules
The arrays may be of different lengths, with at least one character / digit.
The first array will contain string characters (lowercase, a-z),
The second array will contain integers (all positive).
Examples
["a", "b", "c", "d", "e"], [1, 2, 3, 4, 5] =>  ["a", 1, "b", 2, "c", 3, "d", 4, "e", 5]
[1, 2, 3], ["a", "b", "c", "d", "e", "f"] => [1, "a", 2, "b", 3, "c", "d", "e", "f"]
["f", "d", "w", "t"], [5, 3, 7, 8] => ["f", 5, "d", 3, "w", 7, "t", 8]
Gotchas
No intentional gotchas.

My solution: (almost stumped on this one)

function mergeArrays(a, b) {
  let finalArray = [];  
  for(let i = 0; i < a.length || i < b.length; i++){
    if(a[i]){
      finalArray.push(a[i])
    }
    if(b[i]){
      finalArray.push(b[i])
    }    
  }  
  return finalArray;
}

Find The Largest Numbers In A Group Of Arrays
Published by Matt about 4 months ago in JavaScript
arrayssorting
Create a function that takes an array of arrays with numbers. Return a new (single) array with the largest numbers of each.
Examples
[[4, 2, 7, 1], [20, 70, 40, 90], [1, 2, 0]] => [7, 90, 2]
[[-34, -54, -74], [-32, -2, -65], [-54, 7, -43]] => [-34, -2, 7]
[[0.4321, 0.7634, 0.652], [1.324, 9.32, 2.5423, 6.4314], [9, 3, 6, 3]] => [0.7634, 9.32, 9]
Gotchas
Watch out for negative integers.

My solution: 
function findLargestNums(arr) {
  let sortedArray = [];
  arr.map(function(currentArray){
    let currentSort = currentArray
                      .sort(function(a, b) {
                      return b - a		
                      })
    sortedArray.push(currentSort[0]);
  });
  return sortedArray;                          
}

My one-liner solution: 
function findLargestNums(arr) {
	return arr.map((x) => Math.max(...x));            
}

Remove All Duplicates From An Array
Published by Matt about 4 months ago in JavaScript
arraysstringsvalidation
Create a function that accepts an array as an argument. Remove all duplicate items from the array and return the new array.
Rules

Remove duplicate items from array.
New array should be sequentially the same as old array, minus duplicate items.
Examples

["John", "Taylor", "John"] => ["John", "Taylor"]
[1, 0, 1, 0] => [1, 0]
['The', 'big', 'cat'] => ['The', 'big', 'cat']
Gotchas
Test cases contain arrays with both strings and numbers.
Is case sensitive.

My solution:
```





Problem: reverse array in place;
solution:

function reverseArrayInPlace(arrayValue){
  	var length = arrayValue.length;
	for(var i = 0; i < (length - 1) / 2; i++){
    	var temp = arrayValue[length - 1 - i];
      	arrayValue[length - 1 - i] = arrayValue[i];
      	arrayValue[i] = temp;     	
    }
}


var arrayValue = [1, 2, 3, 4];
reverseArrayInPlace(arrayValue);
console.log(arrayValue);
// → [5, 4, 3, 2, 1]
