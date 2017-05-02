# Problem-Solving-Algorithms


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
