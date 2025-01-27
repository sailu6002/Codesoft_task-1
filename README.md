# Codesoft_task-1
import random
#import hangman_stages
word_list=["tomato","anion","beautiful","potato"]
lives=6
chosen_word=random.choice(word_list)
print(chosen_word)
display=[]
for i in range(len(chosen_word)):
    display+="-"
print(display)
game_over=False
while not game_over:
    guessed_latter=input("guess a latter: ").lower()
    for position in range(len(chosen_word)):
        latter=chosen_word[position]
        if latter==guessed_latter:
            display[position]=guessed_latter
    print(display)
    if guessed_latter not in chosen_word:
        lives-=1
        if lives==0:
            game_over=True
            print("you lose!!")
    if "-" not in display:
        game_over =True
        print("you win")
   # print(Hangman_stages.stages[lives])
