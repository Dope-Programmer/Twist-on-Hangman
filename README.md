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
* Blueprint-Driven Mechanics: Everything is built using Unreal Engine Blueprints.

## Blueprint Overview

In this section, I'll explain a little bit the key logic behind how my hangman game works.

#### Select a random word
To begin, just like in a traditional hangman game, we need to pick a secret word. I created an actor in my scene called WordLogic that includes a function called Select Random Word. This function randomly picks a word from a list for the player to guess, ensuring each playthrough feels fresh. Instead of importing word files, I chose to create a custom word list directly in the Blueprint, giving me more control over the gameplay. I also included a separate function to generate baselines, which visually show the length of the secret word.

![WordLogic](https://github.com/user-attachments/assets/efe40b26-67da-4cab-b50f-99b3b2838f6c)

#### Create Widgets
Next, I created another actor called DisplayLettersActor, which handles generating letter placeholders, or "widgets," for the player to interact with. The function Create Widgets matches the number of placeholders to the length of the secret word. These placeholders are updated as the player guesses letters, ensuring the game stays responsive and visually aligned with each guess.

![CreateWidgetFunction](https://github.com/user-attachments/assets/8d45d2fa-1a10-4fcc-a657-6772aa485029)

The Create Widgets function ensures that the widgets are generated with the correct index placement. This will later on be of help when we want to reveal the letter at the correct place inside the word.

![CreateWidgetFunction2](https://github.com/user-attachments/assets/bd1ba6dc-cd39-45be-9644-474dc1787c18)

#### Letter holder
Inside another widget, I created a Letter Holder. This acts as a placeholder for each letter the player guesses correctly. Initially, it shows a generic symbol (I used the letter "N" as a placeholder), which is replaced with the correct letter once the player makes a right guess.

![LetterHolder](https://github.com/user-attachments/assets/2b32ff93-8a53-469e-9b1a-a877e10592d7)

#### Letter Conatins?
Once the player selects a letter and drops it into the game, the Blueprint runs a function to check if the guessed letter exists in the secret word. This process goes through the letter list and compares it with the secret word, as shown in my inventory system Blueprint.

![InventorySystem-LetterConatins](https://github.com/user-attachments/assets/f1849569-39ff-41c5-8a9e-c240a7b77cec)

#### Save letter and index
If the player's guess is correct, the Blueprint saves the letter and its position in the word using a data structure (struct). This makes sure that the game remembers which letters have been guessed correctly and where they belong in the word.

![saveIndexAndLetter-Drongo](https://github.com/user-attachments/assets/df6adcd8-feae-4541-92f2-37e464384160) ![SaveIndexAndLetterFunction-Drongo2](https://github.com/user-attachments/assets/37f46384-99e6-4e6f-9f14-53857295a182)

#### Reveal letter
Now, it's time to reveal the correct letter. When a correct guess is made, the Blueprint retrieves the saved letter and its index. Using the index, the game updates the correct placeholder in the letter-widget array, revealing the letter in the right spot on the screen.  

![RevealLetterFunction](https://github.com/user-attachments/assets/70721cb0-806e-4cfa-a147-4c1cfe04fe86)

## Result:
Now that you've seen a little bit of the Blueprint logic in action, here are the results. 

In this first video, the player guesses the word correctly, leading to a satisfying victory. Yay!

https://github.com/user-attachments/assets/231eb474-44e0-4682-ae33-efbe9b78eb33

And here, you can see what happens when the player guesses wrong—they either run out of time or fall into the lava, ending the game.

![Hangman-NO HD2 Speed1 8-gif](https://github.com/user-attachments/assets/2a0ca817-e7f8-4aba-9ee6-68758f1a2bcd)
![Lavadead HD-gif](https://github.com/user-attachments/assets/f9df5ef3-2a17-4bb9-a697-b2eed238597d)

##  Reflections

This project has taught me a lot about using Blueprints to manage game logic more efficiently. By working on the dynamic letter generation and player consequences, I gained experience with visual scripting and logic flow in Unreal Engine. This is also a project with the most managing of arrays i have ever had in a game. 

## Plans

I plan to refine the level design, add levels, rooms with different themes, more action and enemies to the gameplay, polish the player interactions and broaden the hangman logic. In th end, it would be interesting to make into more of Call Of Duty style. 
