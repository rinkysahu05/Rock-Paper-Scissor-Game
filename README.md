# Rock-Paper-Scissor-Game
# Rock Paper Scissor Game  Using Python  the user gets the first chance to pick the option between Rock, paper, and scissors. After the computer select from the remaining two choices, the winner is decided as per the rules. Winning Rules as follows:  Rock vs paper-> paper wins  Rock vs scissor-> Rock wins  paper vs scissor-> scissor wins
# TASK - 2
# Rock Paper Scissor 
# Using Python

import random

def get_user_choice():
    choice = input("Enter your choice (rock/paper/scissors): ").lower()
    while choice not in ["rock", "paper", "scissors"]:
        choice = input("Invalid choice. Please enter rock, paper, or scissors: ").lower()
    return choice

def get_computer_choice(user_choice):
    options = ["rock", "paper", "scissors"]
    options.remove(user_choice)
    return random.choice(options)

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "scissors" and computer_choice == "paper") or \
         (user_choice == "paper" and computer_choice == "rock"):
        return "You win!"
    else:
        return "Computer wins!"

def main():
    print("Welcome to Rock-Paper-Scissors game!")
    user_choice = get_user_choice()
    computer_choice = get_computer_choice(user_choice)
    
    print(f"Your choice: {user_choice}")
    print(f"Computer's choice: {computer_choice}")
    
    result = determine_winner(user_choice, computer_choice)
    print(result)

if __name__ == "__main__":
    main()
