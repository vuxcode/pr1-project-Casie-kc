[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/o69wxeYp)
# Project Instructions
Follow the instructions here: https://vuxcode.netlify.app/new/pr1/lessons/major-project-brief/

REMEMBER TO "COMMIT" YOUR CHANGES REGULARLY TO SHOW HOW YOU HAVE BUILT THIS PROJECT! 

The final program is not the goal! The aim of the project is to show how you have developed your program, the steps you have taken and the problems you have solved!

# Project Notes

> You can use this section of the file to keep notes about your project as you work on it.
> Hiding and displaying problem: 
I tried putting the hidden play button to show again in the beginning that is supposed show after play’s name is entered. But the button didn’t show. Therefore, I tried playing around by moving the code to different places such  as up and down, outside function or inside function. Finally, it showed up the way I intended after putting the code inside the function playername() as it is supposed to show up after the player’s name is entered. So I figured out where to write the code for others as well.          
Another similar problem happened to the unblocking the hidden button 0-9. I wrote numButton.style.sisplay = “block”; between function playbutton() but it didn’t show. I had no idea why it is not unveiling the hidden button and ask Colin for help. He actually found the problem and told me to debug by for-looping and displaying, instead of just displaying.  
The next one was the “Enter” button didn’t disappear after player’s name is entered. I asked Colin to help me debug this as well since I couldn’t find the problem. The problem was I hid the text box for the player’s name, not the “Enter” button and Colin found out that I forgot to put id and call it. So I added id in button click from this:
<button onclick="playername()">Enter</button>
To this: 
<button id="enterBtn" onclick ="playername()">Enter</button>
 And call it .getElementById so we can find the element and hide it. 
 

Button 0-9 
When I was thinking about hiding the 0-9 buttons in the beginning and showing them again, I thought about using arrays so I could hide or show them all at one instead of working one by one. So I revised lesson 9 and 10. I tried to make an array in this way first: 
var numButton = ["button0", "button1", "button2", "button3", "button4", "button5", "button6", "button7", "button8", "button9"];

But that didn’t work for so I tried to make the way in example, the last part in Lesson 9. But I didn’t quite get it so I went to Lesson 7 “For-loop” to understand better how to make it work. 
I wanted to display the button 0-9 again after hiding, it didn’t show up again but simply writing style.display =”block”;. So I tried searching for why and couldn’t find the reason. So I asked my teacher for help and he told me that I have use for-loop so that it goes through one by one since it is an array. 


  

Creating secret number 
Now I got to the part where I had to create 4 hidden digits, but each of them has to be different in value. I was lost how to do that so I started googling and found some videos of how to generate a random number and also a site where a person asked how to make 4 random digits. There are some different advices people gave and I tried some of their ways. But as they have no explanation for each code’s purpose, I went to our lesson to break them down and understand them as most of them are what we have learned, such as Math function, for-loop, return, .push and slice.  I also came across css and <style> in some of videos and thought of watching and learning how improve and style my webpage.

Place for player to input their answer 
For the next step, the player need to click the button and guess the hidden numbers. I thought of doing 4 boxes to put a number in each that player has to guess. So I googled about it and dug more into button, I watched some video about HTML, button, how to call javascript function and also about building a calculator. I have understanding of button and how to call javascript function from lesson 12 but I would be making box that will be filled with a number not a button to click.  But I decided to go with a text box instead since mine is a bit specific and there is none I could find of. 
The video of building JS calculator was a great help in this. Also in one of the HTML video that I have watched included how to make a password box and how to have limited letter, so I thought of making use of it as well.  
Since the text box is a string, and the number written in the answer box is a string. Therefore when checking for the correct number, there were a problem since hidden number is number not a string. So it needed to change the string into number with the help from lesson 6.  Then again, problem arose comparing number guess to hidden, each number needed to check with each “guessAns [0]   secretNum[0]”, 1 to 1 and so. So each digit guessed need to split into individual and put them in array. 

 
Answer box kept adding 2 digits:
When we click that number buttons the number we click is supposed to show on the answer box, for example if we click 9, it shows 9 in the answer box. But it wasn’t the case, it would show “10” no matter which button we clicked. 
The code I had written was: 
var button = numButton = [i];       //variable for number of button 0-9 array
Button.addEventListener(“click”, function ()    //when we click the button 0-9 
ansBox.value +=i})      //add to the answer box.
I went to my teacher to help me with this and Colin helped me out by substituting “evernt.target” there. 
So it became:  ansBox.value += event.target.innerHTML
What event.target does is it grab the exact element that the player has clicked instead of the button variable or the loop index.  


Feedback problem
I had problem with show feedbacks were shown on the page. Instead of showing each feedback line after line after each guess, it output side by side. I asked Colin what we could do to fix this and he told me to try putting code <br> to the end of each output and it work. 


Correct number problem  
The code below was the one I had originally written. 
for (var a = 0; a < 4; a++) {

        if(guessArr[a] === secretNum[a]) {
            //do nothing  
        }
        
        else {
            for(var b =0; b < 4; b++) {

            /* here we use "AND" operater bc noth condition must be true
        1-check if the each number guessed is equal to one of the hidden number 
        2-if a number is in a differnet position */ 
        if(guessArr[a] === secretNum[b] && a !== b) {

            correctNumber++; 
 
But it had a problem and didn’t output the correct output for how many numbers that the player has guessed are correct. The problem seems that since I had written to add to the correctNumber if the guessed numbers are equal to the hidden numbers and if they are not exactly strictly equal to the hidden number, meaning if they are all in the same position. These eliminated the numbers that are strictly equal to the hidden number (numbers in same position) and only counted the numbers that are in the hidden number, when both all the strictly equal ones and are not equal but are in the hidden number are correct.
Therefore I removed “a !== b” and went the simple way that we had learned in class, “includes”. Includes check if something includes in something/array. So the code become; 
if(secretNum.includes(guessArr [a])); 
 
# Project Summary

> Before the final submission date you should include a "PROJECT SUMMARY" in this section here.
> Finishing 
I also searched about css and watched many videos to style html so my game is designed to my liking. While I was trying to design my game, I came to learn many things about css as well which was very helpful in this lesson. Trying repeatedly and finding what is lacking and what needed to be fixed made me realized how detailed programming is. Like how a small detail can significantly affect your program or change everything.  During the process of testing and playing the game, every attempt and actions I had made are often accompanied by repeated work or mistakes while trying or identify and fix issues. In several cases, a single action in the game had to be added or adjusted in multiple parts of the code. On top of that, connecting lesson parts we had learned and making things work by adding these pieces can be complicating and confusing.  
Later, I worked on details like fixing the answer box not emptying when you click give up button without admitting the answer. The answer remained full even after clicking new game button and we had to guess the answered that was filled so the answer box is empty again. Adding the give up button and attempt count.  

# User Guide


> Write a clear user guide for how someone should use your program.
