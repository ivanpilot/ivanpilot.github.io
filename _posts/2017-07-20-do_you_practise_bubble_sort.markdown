---
layout: post
title:  "Do you practise bubble sort?"
date:   2017-07-20 11:54:46 +0000
---


Bubble sort is a basic algorithm that could be used to sort a list of numbers. I always wanted to write an article on bubble sort because I feel this basic algorithm is a good representation to explain "non coder” people how detailed and thorough a computer program has to be in order to reflect our complex human thinking process even when this process feels as natural and obvious. Sorting a list of number, pretty straight forward right? Imagine you are given an unsorted list of 10 figures and you are required to sort it in an ascending order. How easy is that? It will take you about 5 seconds to do that, even less. And what about explaining your thinking process when sorting this list? You will probably think that there is nothing to explain, right? You just look at the list, identify the smallest number and put it in the first position, and then you identify the smallest number in the remaining list and put it in the second position, and it goes on until there is no number left in this remaining list. 

Imagine that you are now given an unordered list of a billion number, without a computer, it will take days not to say weeks, to sort this list. Because computers are better than humans at repeating operations and at executing these operations faster, it makes sense to spend a few minutes explaining the bubble sort algorithm to the computer so you can save time later down the road. No question about it.

#### So how does that work?

Well, it is no different than the human thinking process we just described. You see the list, identify the smallest number, put this number first and repeat this process with the remaining numbers in the unsorted part of the list until the list is entirely sorted out. Not too hard but … quite not enough for a computer to understand what we want him to do. Why? Because this is not specific enough. What is the list? What does that mean to identify the smallest number? What does that mean to put the smallest number first? Where is first? First of what? There are too many ways to interpret these instructions and it won't even make sense to a computer. 

#### How that would translate into computer language

*We will use an example with a list of 5 numbers and will write the algorithm in javascript. The list of numbers will be stored in an array (an array is a specific data type which allow us to store a sequence of values) and we will use a bubble sort algorithm to sort this array.*

The whole idea behind a bubble sort algorithm is that we take the first element of an array, isolate this element in a variable and assume that this first element is the smallest number of the array. We will call minValue the variable storing this first element.

Then we iterate through the rest of the array and compare each element of this remaining array to minValue. To do this, each element in this remaining array will be successively stored in a variable called currentPosition and will be compared to minValue. As we iterate through this remaining array, the value of currentPosition will change. Each time we move to the next element of the remaining array, we compare minValue with currentPosition. If minValue is above currentPosition, it means that minValue is not the smallest value of the array. As a consequence, we will reassign minValue to currentPosition so that minValue ends up being the smallest value of the part of the array we already iterated on. If minValue is lower than currentPosition, minValue is unchanged and we move to the next element of the remaining array. 
We repeat this process until we have iterated through the entire remaining array. When we are done iterating we know what is the smallest value and its index within the array. 

The only thing left is to swap this minValue with the first element of the array so that the first element of the array will become the actual smallest value. We repeat this entire process until the array is sorted out. 
At any point in time, if you try to visually represent this sorting process, you realise that the array is composed of two inner arrays. One sorted and one unsorted. The sorted array is initially just the first element that we arbitrarily defined as the minValue until we iterate through the array and find a smaller value than the first element if any. The unsorted array is what we called the “remaining array” i.e. the list of numbers to which we compared minValue for each iteration. 

#### Let’s now see a concrete example with code written in javascript

*The unordered list of numbers represented by an array would be held in a variable called “unorderedList” and we will write the bubble sort algorithm in a function call “sortList”.*

```
1. var unorderedList = [4, 3, 5, 2, 1]
2. 
3. function sortList (unorderedList) {    
4.     var array = Object.assign([], unorderedList);
5.   
6.     for (let j = 0; j < array.length; j++) {
7.         var minValue = array[j];
8.         minIndex = j;
9. 
10.         for (let i = j + 1; i < array.length; i++) {
11.             var currentPosition = array[i];
12.             if (currentPosition < minValue) {
13.                 minValue = currentPosition;
14.                 minIndex = i;
15.             }
16.         }
17.     
18.         array[minIndex] = array[j];
19.         array[j] = minValue;
20.     }
21.   
22.     return array;
23. }
24.  
25. var sortedList = sortList(unorderedList)
```



#### The above example will go like this:

**Row 1 to 4**  
Declare the variable unorderedList and assign it an array which is our unordered list of numbers  
Declare a function called sortList which takes one argument that we arbitrarily called unorderedList (so it makes more sense for us, humans, when we read the instructions we are giving to the computer)  

*Row 4 is optional but we put it as we do not want to modify the original unorderedList array. We want the computer to return an new array that will be sorted out. This line is copying unorderedList to a new array called “array” and the rest of the function sortList will modify array while unorderedList remains intact.*

**Row 6 to 20**  
Start the first for-loop where j = 0. Check if j is below the length of the array (0 < 5) which is true  
Declare variables and assign them values such that minValue = 4 and minIndex = 0  

Start the second for-loop where i = 1; Check if i is below the length of the array (1 < 5) which is true  
Declare a variable and assign it value such that currentPosition = 3  
Check if currentPosition is below minValue (3 < 4) which is true so enter inside the ‘if' block  
Reassign minValue to 3 and minIndex to 1  
*// the second for-loop has been executed so increment the index i by one and start again*  

Check if i is below the length of the array (2 < 5) which is true  
Declare a variable and assign it value such that currentPosition = 5  
Check if currentPosition is below minValue (5 < 3) which is false so ignore the code inside the ‘if’ block  
*// the second for-loop has been executed so increment the index i by one and start again*  
           
Check if i is below the length of the array (3 < 5) which is true  
Declare a variable and assign it value such that currentPosition = 2  
Check if currentPosition is below minValue (2 < 3) which is true so enter inside the ‘if' block  
Reassign minValue to 2 and minIndex to 3  
*// the second for-loop has been executed so increment the index i by one and start again*  
    
Check if i is below the length of the array (4 < 5) which is true  
Declare a variable and assign it value such that currentPosition = 1  
Check if currentPosition is below minValue (1 < 2) which is true so enter inside the ‘if' block  
Reassign minValue to 1 and minIndex to 4  
*// the second for-loop has been executed so increment the index i by one and start again*  
        
Check if i is below the length of the array (5 < 5) which is false so ignore the code inside the second for-loop  
*// minValue is 1 and minIndex is 4*  
  
Assign array[j] to array[minIndex] so array[4] = 4  
Assign minValue to array[j] so array[0] = 1  
*// array is now [1, 3, 5, 2, 4]*  
*// the first for-loop has been executed so increment the index j by one and repeat the whole process*  
    
*// When j = 5, the first loop won’t execute again because the condition 5 < 5 is false. So by that time, array will be [1, 2, 3, 4, 5] and the computer will move directly to row 22*  

**Row 22**  
It tells the computer to return array meaning to hand over array to which ever object called the function sortList  

**Row 25**  
In our case, we see that on row 25 we declare a variable called sortedList and assign it the function sortList. sortList will be invoked taking unsortedList as an argument, run the block of code between row 3 and row 23, and will return array to the variable sortedList.  


**That’s it!**  
We just wrote a bubble sort algorithm allowing us to sort any given list of numbers in an ascending order. So you can see how our most basic human thinking-process is already quite complex and how specific and thorough we had to be in order to tell the computer how to sort a list which seems entirely natural to us. We can now use the computer to sort a list holdings a billion numbers and the computer will do it much faster than we do!

Folks, stay tuned!
