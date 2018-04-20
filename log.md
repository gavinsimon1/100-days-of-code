# 100 Days Of Code - Log

********Gavin's Day 1: 2/26/2018********

Today's Progress: 
Worked on the "Factorialize a Number" FCC Algorithm Challenge.  Ended up needing to see the answer.  There are two interesting ways to solve the challenge.  
  1) function factorialize(num) {
      if (num===0){return 1;}
        return num * factorialize (num-1);
      }
    factorialize(5);
  2) function factorialize(num) {
      for (a = 1; num >=1; num --){a= num * a;}
      return a;
      }
    factorialize(5);
    
Next I studied the Udacity Intro to AJAX course.  I'm finding it very helpful.  AJAX is a way to get information for a page without refreshing.  XML and HTMl can be used, but JSON is more common.  JSON is a way to intereact with data and javascript. In the class we scrolled to the bottom of a Facebook page and recorded the Network in the inspect area to watch as an AJAX call was made.
 

Thoughts: So I can call factorialize within my factorialize function?  I want to better understand how that works with Global and Local scope.  The 2nd way to solve the problem used a for loop.  They set a to 1, but then used num for the other 2 perameters.  I didn't know I could do this.  I'm still trying to wrap my head around the rules here.  

********Day 2: 2/27/2018********

I worked on the Into to AJAX class today.  Watching the videos has been helpful in getting an idea of how it all works together.  I'm trying to use JQUERY to display coordinates in Google Maps at the moment.

********Day 44: 4/11/2018********

It's been a long time since I've updated this.  I've been posting to Twitter everyday, but neglected this journal.  I worked through the Free Code Camp Intermediate Algorithm DNA PAIRING.  
function pairElement(str) {
  var newPair=[];
  for(var x=0; x<str.length; x++){
    if(str[x]==='G'){
      newPair.push((str[x] + 'C').split(''));    
    } else if (str[x]==='C'){
      newPair.push((str[x] + 'G').split(''));
    }
    else if (str[x]==='T'){
      newPair.push((str[x] + 'A').split(''));
    }
    else if (str[x]==='A'){
      newPair.push((str[x] + 'T').split(''));
    }
  }
   return newPair;
}

pairElement("GCG");

I'm also playing around with portfolio templates on Github Pages.

********Day 45: 4/12/18********
Got my portfolio up on Github https://gavinsimon1.github.io  I'm stoked because this was a goal of mine.  I still need to improve the design and add projects.  But I'm excited that everything I build will be displayed.  

Missing Letters Solution:
function fearNotLetter(str) {

   for(var x=0; x < str.length - 1; x++){
     if (str.charCodeAt(x+1)- str.charCodeAt(x) != 1){
       return String.fromCharCode(str.charCodeAt(x) + 1);
     }
   }
}

fearNotLetter("abce");

Explanation:
The for loop give the index of the string.  If the next index number less the index number is not equal to 1, then return the index number plus 1. So a has an index of 97, b is 98, c is 99, e is 101.  101 less 99 is not 1, so it returns the missing index number of 100.  I use String.fromCharCode to change the index number back to an alphabet letter.  Cool beans.

********Day 46 4/13/2018 Friday the 13th AKA "Lucky Friday"********
Solved Boo who Challenge

function booWho(bool) {
  // What is the new fad diet for ghost developers? The Boolean.
 var cool = typeof(bool) === "boolean";
  return cool;
}

booWho(null);

Explanation:
I found the initial explanation confusing.  The different types are:
1) Primative value booleans: The most common way is to set a variable to true or false. 
       var cat = true; console.log(cat); // returns true
       var dog = false;  console.log(dog); // returns false
2) Boolean functions: 
       Boolean(2>1) returns true and Boolean(1>2) returns false. 
3) Boolean functions can be used as a constructor by adding New
4) Use var x = new Boolean().  I tried using new Boolean as a constructor but JS Bin didn't like that
It was helpful to get an overview of the complex world of booleans, but turned out to be more of a detour. 

It turns out that typeof() is the key to this challenge. 
    console.log(typeof(bool)); //returns boolean, object, number, string, or undefined.
So if the variable is true or false it will return "boolean" which will return true in the solution above.  If it doesn't equal "boolean" it will return false.
********Day 47 4/14/2018 Saturday******
Sorted Union Algorithm Challenge

function uniteUnique(arr) {
  var args = [];
  for(var x=0; x<arguments.length; x++){
    var blue = arguments[x];
    for(var y=0; y<blue.length; y++){
      var balls = blue[y];
      if(args.indexOf(balls)<0){
        args.push(balls);
      }
    }
  }
  return args;
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);

********Day 48 4/15/2018 Sunday******
Explanation:
When I console logged arr, I only got the first object in the array.  I wasn't sure how to access the other parts of the array.  But using the arguments object worked. Free Code Camp provides a great overview of arguments: https://forum.freecodecamp.org/t/javascript-arguments/14283 
console.log(arguments); //returns all the objects in the array. 
[object Arguments] {
  0: [1, 3, 2],
  1: [5, 2, 1, 4],
  2: [2, 1]
}
I can access specific parts of the arry with console.log(arguments[x]);
However, arguments is not an array.  The same link also explains that the best way to convert arguments into an array is:  
var args = []; // Empty array, at first.
for (var i = 0; i < arguments.length; i++) {
    args.push(arguments[i])
} 
This will return all of the arguments as an array: [[1, 3, 2], [5, 2, 1, 4], [2, 1]]
Now we have all of the arguments as an array, but we still need to combine them.  Removing push and setting arguments[x] equal to a variable returns:
[1, 3, 2]
[5, 2, 1, 4]
[2, 1]
A second loop through returns all of the elements of the arrays as:
1
3
2
5
2
1
4
2
1
console.log(args.indexOf(balls)) returns:
-1
-1
-1
-1
2
0
-1
2
0
So 1,3,2,5 are not found in args. But 2 and 1 are.  4 is not, but 2 and 1 are again.  So if it's less than 0, we push it to args.


**Day 49 4/16/2018 Monday**
Diving into regular expressions today
I found out there are two ways to write regular expressions.  The longway:
regexp = new RegExp("pattern", "flags");
And the short way:
regexp = /pattern/; // no flags
regexp = /pattern/gmi; // with flags g,m and i 
I like this example of a simple regular expression:

let str = "I love JavaScript!"; 
let regexp = /love/;
alert( str.search(regexp) ); // 2
alert( str.search(/LOVE/i) ); // 2

**Day 50 4/17/2018 Tuesday**
Convert HTML Entities Challenge
function convertHTML(str) {
 var object = {
   '&': '&amp;',
   '<': '&lt;',
   '>': '&gt;',
   '"': '&quot;',
   "'": '&apos;',
 };
  for (var x in object){
    var before = x;
    var after = object[x];
    var pattern = new RegExp(before, 'g');
    str = str.replace(pattern, after);
   
  }
   return str;
}

convertHTML("Dolce & Gabbana");

Explanation: for(variable in object) can be used with an object.  When I console.log(before); I get:
"&"
"<"
">"
"\""
"'"
console.log(after); results in:
"&amp;"
"&lt;"
"&gt;"
"&quot;"
"&apos;"

So this part of the code is giving me the two pieces I need.  
for (x in object){
var before = x;
var after = object[x];

Now, to put them together.
The new RegExp constructor creates a regular expression object for matching text with a pattern.  "Use the constructor function when you know the regular expression pattern will be changing, or you don't know the pattern and are getting it from another source, such as user input."

Finally replace allows me to change the regular expression to after. 

Spinal Tap Case
str=str.toLowerCase().split(" ").join('-'); works for some of the cases but not all of them.  

**Day 51 4/18/2018 Wednesday**
function spinalCase(str) {
 var blue = str.replace(/_/g, '');
   var balls = blue.replace(/([A-Z])/g, ' $1');
   var dog = balls.replace(/\s+/g, '-').toLowerCase();
   var hairy = dog.replace(/^-/, '');

   return hairy;
}

spinalCase('thisIsSpinalTap');

Explanation:
This one took a lot of tinkering.  First I replace all of the underscores with spaces.  I found this great article https://codeburst.io/javascript-learn-regular-expressions-for-beginners-bb6107015d91 explaining regular expressions.  He specifically explains how to replace camel case with spaces.  He shows how to use capturing parenthesis to remember the matched capital letters which are accessed with $1.  So now we have spaces between words.  Next I remove the spaces and add a dash.  I thought I was done, but there are dashes at the beginning of some of the cases.  The final line uses ^- to remove the first dash while keeping the rest.  

**Day 52 4/19/2018 Thursday**
Sum All Odd Fibonacci Numbers
function sumFibs(num) {
  var num1 = 0;
  var num2 = 1;
  var result =1;
  var odd =[];
  
  for(var i=0; i <= num; i++){
    next = num1 + num2;
    num1 = num2;
    num2 = result;
   
     if(num1%2==1 && num1<=num){
     odd.push(num1);
   } 

  } 
 console.log(odd);
  var sum = odd.reduce(add, 0);

      function add(a, b) {
              return a + b;
     }

   return (sum);
      
}

sumFibs(4);

Explanation:
Fibonacci sequence: every number after the first two is the sum of the two preceding ones. The sequence is: 1,1,2,3,5,8,13,21,34,55,89,144,... 
Within the loop for loop 
//num1 returns 1,1,2,3,5
//num2 returns 1,2,3,5,8
//result returns 1,2,3,5,8
//num remains 4
Then I needed to check if the number was odd and less than or equal to the number.  Numbers that pass that test get pushed into the odd array.  I used another function to add the numbers together.  
