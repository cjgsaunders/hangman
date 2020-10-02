import random

print("H A N G M A N")


# Menu function
def menu():
    game_state = input('Type "play" to play the game, "exit" to quit: ')
    while game_state != "exit" and game_state != "play":
        game_state = input('Type "play" to play the game, "exit" to quit: ')
    if game_state == "play":
        run()


# Game function
def run():
    # VARIABLES
    lives = 8
    words_list = ["python", "java", "kotlin", "javascript"]
    chosen_word = random.choice(words_list)
    hidden_word_list = list("-" * len(chosen_word))
    correct_letters = frozenset(chosen_word)
    no_improvement_set = set()
    # ---------------------------------------------------

    # Game logic
    while lives > 0:
        print("\n", ''.join(hidden_word_list))

        user_input = input("Input a letter: ")

        # Check for valid input in this if statement
        if len(user_input) == 0 or len(user_input) > 1:
            print("You should input a single letter")
            continue
        elif not user_input.isalpha() or user_input.isupper():
            print("It is not an ASCII lowercase letter")
            continue
        elif user_input in no_improvement_set:
            print("You already typed this letter")
            continue

        no_improvement_set.add(user_input)

        if user_input in correct_letters:
            for i, letter in enumerate(chosen_word):
                if letter == user_input:
                    hidden_word_list[i] = user_input
            if chosen_word == ''.join(hidden_word_list):
                print("You survived!\n The correct word was", ''.join(hidden_word_list))
                menu()
                break
        else:
            print("No such letter in the word")
            lives -= 1

    else:
        print("You lost!\n")
        menu()


menu()
