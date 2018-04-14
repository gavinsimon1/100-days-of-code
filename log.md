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
  return Array.prototype.concat(Array).concat.apply([],    arguments).filter(function(elem, index, array){
    return array.indexOf(elem) === index;
  });
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);

Explanation:
Array.prototype.concat(Array)
