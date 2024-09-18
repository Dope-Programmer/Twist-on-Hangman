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

## Blueprint

To keep it simple, I will show briefly the hangman logic.

##### Select a random word
Like in the hangman game, I want a secret word to be chosen, so this is where I will start. I have an actor in my scene called WordLogic with a function named Select Random Word. This is where the game selects a random word for the player to guess, which adds variety. To make the logic easier to manage for myself, I manually created a list of possible words in the Blueprint. In order for the player to know the length of the word, I have a separete function that generates the baselines. 

![WordLogic](https://github.com/user-attachments/assets/efe40b26-67da-4cab-b50f-99b3b2838f6c)

##### Create Widgets
I have another actor name DisplaylettersActor. Inside this actor I have a function called Create Widgets. This function generates letter-widgets in the same length as the secret word that is selected during the start, just like the baselines.

![CreateWidgetFunction](https://github.com/user-attachments/assets/8d45d2fa-1a10-4fcc-a657-6772aa485029)

The Create Widgets function ensures that the widgets are generated with the correct index placement. This will later on be of help when we want to reveal the letter at the correct place inside the word.

![CreateWidgetFunction2](https://github.com/user-attachments/assets/bd1ba6dc-cd39-45be-9644-474dc1787c18)

##### Letter holder
In another widget, I have a letter that acts as a "Letter holder" that will later be replaced with the letter player guessed correctly. N simply stands for "Name".

![LetterHolder](https://github.com/user-attachments/assets/2b32ff93-8a53-469e-9b1a-a877e10592d7)

#### Letter Conatins?
Now, let's say the player has finally picked up a letter and dumps it. During the "dumping" process, have functions that goes through lists and checks if the letter that the player dropped exists in the secret word, such as this one below from my Inventory system.

![InventorySystem-LetterConatins](https://github.com/user-attachments/assets/f1849569-39ff-41c5-8a9e-c240a7b77cec)

##### Save letter and index
If the letter exists, it will lead to the function inside the player that saves the correct gussed letter and its index in a struct.

![saveIndexAndLetter-Drongo](https://github.com/user-attachments/assets/df6adcd8-feae-4541-92f2-37e464384160) ![SaveIndexAndLetterFunction-Drongo2](https://github.com/user-attachments/assets/37f46384-99e6-4e6f-9f14-53857295a182)

##### Reveal letter
This leads us to the next step: to reveal the letter. When we want to reveal the correct guessed letter, we get the structure that holds the saved letter and index. To reveal it, we get the correct index in the array of the letter-widgets we generated in the Create Widgets function.

![RevealLetterFunction](https://github.com/user-attachments/assets/70721cb0-806e-4cfa-a147-4c1cfe04fe86)

## Result:
Having shown a part of the process, this is the result:

In this video you see if the player guesses all wordscorrect, along with a victory scene.



And here it's where the player guesses wrong:

![Hangman-NO HD2 Speed1 8-gif](https://github.com/user-attachments/assets/2a0ca817-e7f8-4aba-9ee6-68758f1a2bcd)

And well, if you touch the lava, or runs out of time and chances, you die.

![Lavadead HD-gif](https://github.com/user-attachments/assets/f9df5ef3-2a17-4bb9-a697-b2eed238597d)

##  Reflection and Learning

This project has taught me a lot about using Blueprints to manage game logic more efficiently. By working on the dynamic letter generation and player consequences, I gained experience with visual scripting and logic flow in Unreal Engine. Next, I plan to refine the level design, add levels and more action to the gameplay, as well as polish more the player interactions.
