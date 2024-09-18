# Twist on Hangman - WIP.

This is my first project in Unreal Engine and my initial experience working with Blueprints. The game combines the classic concept of Hangman with the challenge of "The Floor is Lava," set in an arena-style level. Players must guess a secret word by collecting and dropping letters found throughout the level. You can win by guessing the word correctly, but you lose if you run out of chances or fall into the lava.
While the current version is basic, with no detailed level design yet, the core mechanics—letter guessing, winning, and losing conditions—are functional. I’m excited about this idea and plan to continue developing it further!

![haangman omslag](https://github.com/user-attachments/assets/8e23d2e1-b8b2-4a09-8900-47074d6a5ebc)

## Key features:

### So far, I have these features: 

* Dynamic Letter Generation: Players collect letters dynamically that's placed in the level.
* Lava Hazard: The lava floor rises the more time passes.
* Timer: As of now, the timer is 4 minutes. If the player guesses correct, they gain for example 5 seconds. If they guess wrong, they lose 5 seconds.
* Multiple Guess Chances: Players get several attempts to guess the word.
* Blueprint-Driven Mechanics: Everything is built using Unreal Engine Blueprints for a clean, visual workflow.

## Blueprint

### Letter Generation Blueprint

How I dynamically generate letters for players to collect and guess.


Having shown a part of the process, this it the result:

https://github.com/user-attachments/assets/1eef12ec-39e8-426c-b27e-0b98f8c27e85



