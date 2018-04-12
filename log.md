# 100 Days Of Code - Log

Gavin's Day 1: 2/26/2018 

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

Day 2: 2/27/2018

I worked on the Into to AJAX class today.  Watching the videos has been helpful in getting an idea of how it all works together.  I'm trying to use JQUERY to display coordinates in Google Maps at the moment.

Day 44: 4/11/2018

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

Day 45: 4/12/18
Got my portfolio up on Github https://gavinsimon1.github.io  I'm stoked because this was a goal of mine.  I still need to improve the design and add projects.  But I'm excited that everything I build will be displayed.  

