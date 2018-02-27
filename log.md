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
