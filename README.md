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
```
