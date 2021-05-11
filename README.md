# Beginner-Level-Python-Project-ideas-
Here we have listed python projects for beginners level Python Developer.

# 1. Mad Libs Generator 
This python beginner project is a good start for beginner software developers as it has concepts like strings, variables, and concatenation. Mad Libs Generator teaches to manipulate user-inputted data as the Mad Libs refer to a series of inputs that a user enters. The input from the user could be anything from an adjective, a pronoun, or even a verb. After all the inputs are entered the application takes all the data and arranges it to build a story template. 

Source Code:

```python
""" Mad Libs Generator
----------------------------------------
"""
//Loop back to this point once code finishes
loop = 1
while (loop < 10):
// All the questions that the program asks the user
    noun = input("Choose a noun: ")
    p_noun = input("Choose a plural noun: ")
    noun2 = input("Choose a noun: ")
    place = input("Name a place: ")
    adjective = input("Choose an adjective (Describing word): ")
    noun3 = input("Choose a noun: ")
// Displays the story based on the users input
    print ("------------------------------------------")
    print ("Be kind to your",noun,"- footed", p_noun)
    print ("For a duck may be somebody's", noun2,",")
    print ("Be kind to your",p_noun,"in",place)
    print ("Where the weather is always",adjective,".")
    print ()
    print ("You may think that is this the",noun3,",")
    print ("Well it is.")
    print ("------------------------------------------")
// Loop back to "loop = 1"
    loop = loop + 1
```


# 2. Number Guessing 

This project is an exciting fun game for beginners to build up. The program generates a random number from 1 to 10, or 1 to 100 any range that is specified and the user must guess the number after a hint from the computer. Every time a user’s guess is wrong they are prompted with more hints to make it easier for them to guess the number but at the cost of reducing the score. The clue any math clue like multiples, divisible, greater or smaller, or a combination of all. 

The program also requires functions to check if an actual number is entered by the user or not, to compare the input number with the actual number, to find the difference between the two numbers. 

Source Code:

```python
""" Number Guessing Game
----------------------------------------
"""
import random
attempts_list = []
def show_score():
    if len(attempts_list) <= 0:
        print("There is currently no high score, it's yours for the taking!")
    else:
        print("The current high score is {} attempts".format(min(attempts_list)))
def start_game():
    random_number = int(random.randint(1, 10))
    print("Hello traveler! Welcome to the game of guesses!")
    player_name = input("What is your name? ")
    wanna_play = input("Hi, {}, would you like to play the guessing game? (Enter Yes/No) ".format(player_name))
    // Where the show_score function USED to be
    attempts = 0
    show_score()
    while wanna_play.lower() == "yes":
        try:
            guess = input("Pick a number between 1 and 10 ")
            if int(guess) < 1 or int(guess) > 10:
                raise ValueError("Please guess a number within the given range")
            if int(guess) == random_number:
                print("Nice! You got it!")
                attempts += 1
                attempts_list.append(attempts)
                print("It took you {} attempts".format(attempts))
                play_again = input("Would you like to play again? (Enter Yes/No) ")
                attempts = 0
                show_score()
                random_number = int(random.randint(1, 10))
                if play_again.lower() == "no":
                    print("That's cool, have a good one!")
                    break
            elif int(guess) > random_number:
                print("It's lower")
                attempts += 1
            elif int(guess) < random_number:
                print("It's higher")
                attempts += 1
        except ValueError as err:
            print("Oh no!, that is not a valid value. Try again...")
            print("({})".format(err))
    else:
        print("That's cool, have a good one!")
if __name__ == '__main__':
    start_game()
    
```

# 3. Rock Paper Scissors

This program or a mini-game is designed when you don’t have anyone to play or you are under lockdown alone. There are a number of functions that this program requires so let us have an overview of each.

*a random function:*  to generate rock, paper, or scissors. 
*valid function:* to check the validity of the move.
*result function:* to declare the winner of the round.
*scorekeeper:* to keep track of the score.

The program requires the user to make the first move before it makes one the move. Once the move is validated the input is evaluated, the input entered could be a string or an alphabet. After evaluating the input string a winner is decided by the result function and the score of the round is updated by the scorekeeper function. 

Source code:

```Python
""" Rock Paper Scissors
----------------------------------------
"""
import random
import os
import re
os.system('cls' if os.name=='nt' else 'clear')
while (1 < 2):
    print "\n"
    print "Rock, Paper, Scissors - Shoot!"
    userChoice = raw_input("Choose your weapon [R]ock], [P]aper, or [S]cissors: ")
    if not re.match("[SsRrPp]", userChoice):
        print "Please choose a letter:"
        print "[R]ock, [S]cissors or [P]aper."
        continue
    // Echo the user's choice
    print "You chose: " + userChoice
    choices = ['R', 'P', 'S']
    opponenetChoice = random.choice(choices)
    print "I chose: " + opponenetChoice
    if opponenetChoice == str.upper(userChoice):
        print "Tie! "
    #if opponenetChoice == str("R") and str.upper(userChoice) == "P"
    elif opponenetChoice == 'R' and userChoice.upper() == 'S':      
        print "Scissors beats rock, I win! "
        continue
    elif opponenetChoice == 'S' and userChoice.upper() == 'P':      
        print "Scissors beats paper! I win! "
        continue
    elif opponenetChoice == 'P' and userChoice.upper() == 'R':      
        print "Paper beat rock, I win! "
        continue
    else:       
        print "You win!"
        
```


# 4. Website Blocker
We all know while surfing through the net many unwanted sites popup to distract us. This project comes at help in such cases as it can be built up to block certain websites from opening. The program is beneficial for people who get easily distracted to switch to social media sites while into something serious. 

Source code:

```Python 

""" Website Blocker
----------------------------------------
"""
import time
from datetime import datetime as dt
hosts_path = r"/etc/hosts"   // r is for raw string
hosts_temp = "hosts"
redirect = "127.0.0.1"
web_sites_list = ["www.facebook.com", "facebook.com"]    // users can modify the list of the websites they want to block
while True:
   if dt(dt.now().year, dt.now().month, dt.now().day, 9) < dt.now() < dt(dt.now().year, dt.now().month, dt.now().day,22):
       print("Working hours")
       with open(hosts_path, "r+") as file:
           content = file.read()
           for website in web_sites_list:
               if website in content:
                   pass
               else:
                   file.write(redirect+" "+website+"\n")
   else:
       print("Fun time")
       with open(hosts_path, "r+") as file:
           content = file.readlines()
           file.seek(0)  // reset the pointer to the top of the text file
           for line in content:
               // here comes the tricky line, basically we overwrite the whole file
               if not any(website in line for website in web_sites_list):
                   file.write(line)
               // do nothing otherwise
           file.truncate() // this line is used to delete the trailing lines (that contain DNS)
    time.sleep(5)

```

# 5. Binary Search Algorithm 
The name is evident enough to give an overview of the project. The program requires you to create a list of numbers between 0 to whatever range you prefer, with every succeeding number having a difference of 2 between them. 

When the user inputs a random number to be searched the program begins its search by dividing the list into two halves. The first half is searched for the required number and if found, the other half is rejected and vice versa. The search continues until the number is found or the subarray size becomes zero. This Python project idea could also help you write a program to search an element in the list. 

Source code:

```Python 

""" Binary Search Algorithm 
----------------------------------------
"""
// iterative implementation of binary search in Python
def binary_search(a_list, item):
    """Performs iterative binary search to find the position of an integer in a given, sorted, list.
    a_list -- sorted list of integers
    item -- integer you are searching for the position of
    """
    first = 0
    last = len(a_list) - 1
    while first <= last:
        i = (first + last) / 2
        if a_list[i] == item:
            return ' found at position '.format(item=item, i=i)
        elif a_list[i] > item:
            last = i - 1
        elif a_list[i] < item:
            first = i + 1
        else:
            return ' not found in the list'.format(item=item)
// recursive implementation of binary search in Python
def binary_search_recursive(a_list, item):
    """Performs recursive binary search of an integer in a given, sorted, list.
    a_list -- sorted list of integers
    item -- integer you are searching for the position of
    """
    first = 0
    last = len(a_list) - 1
    if len(a_list) == 0:
        return ' was not found in the list'.format(item=item)
    else:
        i = (first + last) // 2
        if item == a_list[i]:
            return ' found'.format(item=item)
        else:
            if a_list[i] < item:
                return binary_search_recursive(a_list[i+1:], item)
            else:
                return binary_search_recursive(a_list[:i], item)

```





