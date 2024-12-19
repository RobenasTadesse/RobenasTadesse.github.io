---
Day 2 (December 11th)
---
  
  I decided to focus on three components/behaviors for today's work, button clicking (drawing an "X" or "O" on the 3x3 grid), switching the player, and the configuration of the 3x3 grid. 
  
I needed to define a function that I could call to configure the behavior of a button click. In other words, I needed to make a function saying what would happen when you click a button on the 3x3 grid. The way I implemented this was to start with a variable called `current_player`, which would be equal to a "X," because Xs go first in tic-tac-toe. The biggest challenge on this day was trying to organize my thoughts about the grid and interaction behavior and bring them to life on the Juypter notebook. I knew that I would have to split the game into several user-defined functions. I decided on 6 functions: `button_click(), switch_player(), check_winner(), display_winner(), game_over(),` and `reset_game()`. These functions should have everything I need to create the game. 

  The **button_click()** function updates the button with the current player's symbol only if the cell is empty and the game is not over. It should also switches the turn to the other player if no winner is detected. It takes in two arguments, `row` and `col`.For this function, I learned an very helpful new statement called `global` (much like `for`, `if-elif-else`, and `import`). What `global` does is gives you the ability to change the value of a variable inside a function, but still refers to the global variable defined outside the function. In the case of the variable "X," it is defined outside any function, making it a global variable. Without global, if you try to refer to a global variable inside a function, Python assumes the variable to be local, which would cause issues in the GUI.

  The `switch_player()` function also uses `global` to refer to `current_player` and switch depending on conditions. 

  To create the 3x3 grid of buttons for tic-tac-toe, a function is not required, you can just use two for loops and an empty list one for rows, and another for columns. 

  A challenge encountered on this day was the creation of the 3x3 grid. More importantly, a grid that would respond to clicks the way I want. After looking through many resources, I saw that the syntax was very foreign to me and I didn't understand one expression that seemed consistently used in many GUI games: the `lambda` function. This function was basically the backbone of coordinating the row/column button clicking on the grid, and I couldn't seem to find a way around it using the simpler methods we practiced in class. In the end, I went to Python documentation and "6.14. Lambdas" and read many explanations. I also watched a helpful YouTube video and tried using `lambda` myself on some very simple cases. The general syntax is `lambda[PARAMETER(S)] :[EXPRESSION]`. The `lambda` is a helpful tool in Python because it condenses a lot of code into a smaller space. The function is anonymous, meaning it does not have a name and thus should only be used if you use the function once. 
  
   - EXAMPLE 1: `names = ['joe', 'mike', 'sarah']
               uppercase = lambda s: s.upper()
               for name in names:
                 print(uppercase(name))** # Outputs JOE MIKE SARAH`
  - EXAMPLE 2: `numbers = [1, 2, 3]
               cubed = lambda x: x ** 3
               for num in numbers:
                 print(cubed(num))** # Outputs 1 8 27`

  This day took a very long time, and I am relieved to be done. Tomorrow I will begin working on implementing `check_winner()` and `display_winner`.

