# Python-Games

These are just a couple examples of some simple python projects that I have created in the past. 

## Avatar Random Quiz Game 

This is a 15-question quiz game that quizzes the user on fun facts from the popular show: Avatar-The Last Airbenders. The questions are generated in random order using the random module: 

```
import random 

```
Two of the main concepts in this game (Lists and the Random module) are highlighted below 

### Use of Lists 

A total of three lists are used in the game: a question bank list, an answer key list, and a corresponding answer choices list. The answer choices list is a nested list that contains multiple choice options for the user to pick through. 

An example of the lists is shown below: 

```
Questions_list = ["Who is Katara's brother?", "Which nation does Aang belong to?"] 

Answer_choices = [['A. Aang', 'B. Sokka', 'C. Momo'],['A. Fire Nation', 'B. Air Nation', 'C. Water Nation']]

Answer_key = ["B","B"] 

```
The most important characteristic of the lists is that the answer choices, questions, and key correspond with each other because of the order that they are in. For the above code, the first question (referenced as Questions_list[0]) corresponds to the first nested list in the Answer_choices list and the first item in the Answer_key list. 

### Use of Random module 

A random list of non-repeating integers is created using the function: 

```
random.sample(range(15), 15) 
```

This function ensures that the integers called are non-repeating and are in the range of 0-14 (which is equivalent to 15 items/questions). 

A for loop is used to traverse through the random list and use the random list value as an index position for the question and answer lists. The question and answer choices that are position wise equivalent to the random number are printed and the user's inputs are matched with the answer key to the question. 

Finally, at the end of the game, the player's score is printed. 










