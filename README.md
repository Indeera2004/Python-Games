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


## War Card Game

The second python game is based on the card game War. There are a couple of main rules in this game: 

- The deck is split between the computer and the player 
- The first card from each deck is drawn and the card values are compared 
- If the player's card is greater than the computer's card, both cards are added to the deck of the winner 
- If both of the cards are the same value, the fourth card is drawn and the values are compared similarly to above 
- The winner of the draw gains the four cards from the loser's deck 
- The game ends when the player has no more cards in their player deck 

The main concept in this game is the calling of functions

### Use of Functions 

There are a total of four functions used in this program. 

The first one is determinevalue(firstchar) shown below: 

```
def determinevalue(firstchar):
  if firstchar == "K":
    value= 13
  elif firstchar == "Q":
    value= 12
  elif firstchar == "J":
    value= 11
  elif firstchar == "A":
    value = 1
  else: value = int(str(firstchar))
  return value
```

The determine value function is used to find the numerical value of the string card. For example, if given the card: '5♥', the parameter for the determinevalue funcion would be 5 (indiciating the first character of the card). Then, a series of if statements determine the numerical value of the card in case the first character is a face card. 

The second function is called checkwinner: 

```
checkwinner(cardone, cardtwo, valueone, valuetwo) 

```

This function uses both cardone and cardtwo that were drawn for the round as well as the numerical values of the cards (valueone and valuetwo). 

While there are cards in the player's deck, the code proceeds to the following if statements: 

- if valueone > valuetwo: add the two cards to the computers card deck 
- if the opposite is true: add the cards to the player's deck 
- if the values are equivalent then the function war_game is called 


if the while loop is false, then the game ends since the player has no more cards to play with. 

The third function is called war_game() and is only called when the card drawn in the round are numerically equivalent. This function uses both the computer's deck and the player's deck as parameters. 

```
war_game(compdeck, playerdeck) 

```
This function isolates the the first character of the fourth card of both decks and calls the determinevalue function to fnd the numerical value of the first characters. If the computer's card has a higher value, the first four cards of the player's deck are added to the computer's deck. The vice versa is true. 


The fourth and final function calls all of the three previous functions into one: 

drawcards(list_a, list_b) 

```
def drawcards(list_a, list_b):
  
 
  cardone = random.choice(list_a)
  cardtwo = random.choice(list_b)

  print("This is computer's card:", cardone+ "\n"+ "This is your card:", cardtwo)
 
 #isolates the value of the card 

  firstcharone = cardone[:-1] 
  firstchartwo = cardtwo[:-1]
  
 #calculates the integer value of the card 

  valueone = determinevalue(firstcharone)
  valuetwo = determinevalue(firstchartwo) 
  

  checkwinner(cardone, cardtwo, valueone, valuetwo)
  
 ```
The function uses list_a and list_b as parameters and calls random values from the deck. It then isolates the first character of the string in the list (deck of cards) and feed them through the determinevalue() functions. The return values from determinevalue functions are stored as values and used as parameters for the checkwinner function. 
