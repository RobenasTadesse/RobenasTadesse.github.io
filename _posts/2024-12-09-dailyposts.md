
---
Day 1 (December 10th) 
---
Hello! Apologies for the lateness, I was busy.

  On December 10th, I began my journey to create a Graphical User Interface for the Tic-Tac-Toe game. I decided to dive right in, and took Lux's advice to use the **tkinter** library. Tkinter is one of the standard libraries in Python, like **plotly**, **math**, and **random**. 
  
  Now, for just one day, I learned a lot more than I was expecting. The first thing I learned was that I could not use the **tkinter** library in Google Colab, because it does not support GUI stuff. So then I downloaded Homebrew from my Terminal application, and I already had Python on my computer so that was good. Next, I decided it would be a good idea to install and launch Jupyter Notebook, because I could edit it from my web browser kind of like Colab, but it would support **tkinter**. Here I made it sound like the process was smooth, but there was lot of troubleshooting and dumbfoundedness. But the problems themselves were pretty simple, just being told **zsh: command not found: brew** and **zsh: command not found: jupyter** and on my Terminal. Nevertheless, it required a quite a bit of research to solve.   
  
  Next I familiarized myself with the Juypter and began learning about the basics of tkinter. I honestly love how straightforward the library is, the syntax just feels so logical. To start off anything with **tkinter**, you have to **import tkinter as tk**. To test if everything is up and running, you write **tk._test**, causing a Python window to pop up confirming that everything is working. A tedious thing with the Jupyter Notebook-Python window set up is when you run the code, it won't change anything on the window until you close out of it and run the code on Juypter again.  
  
  To initialize a new window for the GUI, you say **root = tk.Tk()**. Something I found really interesting as was that if you run that, alone, nothing new will pop up. This is becuase the application is being opened and closed too quickly to notice. A way to solve that issue is to say **root.mainloop()**, and this basically keeps the window open for you to see. What we have right now is the template/scaffolding/canvas for the whole GUI. All the code will be sandwiched between **import tkinter as tk** and **root.mainloop()** To name the window you do **root.title("(TITLE GOES HERE)")**. I named mine "Tic-Tac_Toe GUI."
  
  I then moved on to the basics of actually implementing a GUI: 
  - To make a button you say **btn = tk.Button(root, text = "(WRITING ON THE BUTTON)", command = (A FUNCTION NAME))**.
      - Position the button: **btn.grid(row = __ , column = __)** rows/columns start at 0, just like **range()**
  - Above the button to make a label: **lbl = tk.Label(root, text = "(WRITING FOR LABEL)")**
      - Position the button: **lbl.grid(row = __, column = __, columnspan =__)** columnspan indicates how many columns are taken up         by the label, and also starts at 0.  

The next day I worked on creating a basic interface with a grid and buttons that update based on player moves. I am thinking of doing a thing where each mouse click will alternate after each click. Like it will start with "X" and then go to "O" and so on until there is a winner or draw. After I achieve this I'll add the ability to actually claim a winner (either "X"/"O" or perhaps asking for each player's name?). But anyway, after I make the game I will make the game look colorful and fun to interact with. Also I think this post is too long so I'll try to condense it in the next post. 


---
Day 2 (December 11th)
---
  I decided to focus on three components/behaviors for today's work, button clicking (drawing an "X" or "O" on the 3x3 grid), switching the player, and the configuration of the 3x3 grid. 
I needed to define a funciton that I could call to configure the behavior of a button click. In other words, I needed to make a function saying what would happen when you click a button on the 3x3 grid. The way I implemented this was to start with a variable called **current_player**, which would be equal to a "X," becuase Xs go first in tic-tac-toe. The biggest challenge on this day was trying to orgainze my thoughts about the grid and interaction behavior and bring them to life on the Juypter notebook. I knew that I would have to split the game into several user-defined functions. I decided on 6 functions: **button_click(), switch_player(), check_winner(), display_winner(), game_over(),** and **reset_game()**. These functions should have everything I need to create the game. 

  The **button_click()** function updates the button with the current player's symbol only if the cell is empty and the game is not over. It should also switches the turn to the other player if no winner is detected. It takes in two arguments, **row** and **col**.
For this function, I learned an very helpful new statement called **global** (much like **for**, **if-elif-else**, and **import**). What **global** does is gives you the ability to change the value of a variable inside a function, but still refers to the global variable defined outside the function. In the case of the varible "X," it is defined outside any function, making it a global variable. Without global, if you try to refer to a global variable inside a funcion, Python assumes the varibale to be local, which would cause issues in the GUI.

  The **switch_player()** function also uses **global** to refer to **current_player** and switch depending on conditions. 

  To create the create the 3x3 grid of buttons for tic-tac-toe, a function is not required, you can just use two **for loop**s and an empty list one for rows, and another columns. 

  A challenge encountered on this day was the creation of the 3x3 grid. More importantly, a grid that would respond to clicks the way I want. After looking through many resources, I saw that the syntax was very foreign to me and I didn't understand one an expression that seemed consistently used in many GUI games: the **lambda** function. This function was basically the backbone of cordinating the row/column button clicking on the grid, and I couldn't seem to find a way around it using simpler methods we practiced in class. In the end, I went to Python documentation and "6.14. Lambdas" and read many explainations. I also watched a helpful YouTube video and tried using **lambda** myself on some very simple cases. The general syntax is **lambda[PARAMETER(S)]** :**[EXPRESSION]**. The **lambda** is a helpful tool in python becuase it condenses a lot of code into a smaller space. The function is anonymous, meaning it does not have a name and thus should only be used if you use the function once. 
  - EXAMPLE 1: **names = ['joe', 'mike', 'sarah']
               uppercase = lambda s: s.upper()
               for name in names:
                 print(uppercase(name))** # Outputs JOE MIKE SARAH 
  - EXAMPLE 2: **numbers = [1, 2, 3]
               cubed = lambda x: x ** 3
               for num in numbers:
                 print(cubed(num))** # Outputs 1 8 27

  This day took a very long time, and I am relieved to be done. Tomorrow I will begin working on implementing **check_winner()** and **display_winner**. 


---
Day 3 (December 12th)
---

  To begin, I needed create what message would be displayed after the **check_winner** function, which was a fairly easy function. I just used the knowledge I gained from Day 1 and applied it to the label. I learned how to change font, font color, and font size:
  
   - **lbl.config(text=(TEXT), fg="(COLOR)")** to be put inside the **display_winner** function, so it can be updated on whether the winner is X, O, or a draw.  
  - **lbl = tk.Label(root, text="(TEXT)", font=("NAME OF FONT", FONT SIZE))** to be put at the end of everything becuase it's done        once and nothing changes.

  Overall, **display_winner** function was pretty easy and straightforward compared to the functions I've made so far, although the tricky thing about GUIs is that you can't really know if you did everything right until the final product is run.
  
  For **check_winner()**, I had to create a series of **if-else-elif** statements to encapsulate all the possible winning positions comparing each button to the next to check if they are equal, using the button indicies in this format: **buttons[row][column]["text"]**. I figrued a comprehensive and compact way to do this was to use a **for loop** and **range()**. The had the vague in my head idea but it was annoyingly challenging to implement. I would start typing and then think, "Wait, does this make sense?" I got a pen and paper and and drew each possible tic-tac-toe combination, and what it would correspond to for the **for loop**/**if statement**. 
  
  I set up the **for loop** with a **range(3)**, and just like rows and columns, the **range()** start value is 0. The first **if statement** under the **for loop** had the index (i) in the row position, and the second if satement had the index as the column position, with the column and row position incrmenting by one in order to access each button. It's really hard to describe in writing but this ensured that after all three iterations were complete, you would capture each of row/column winning patterns. "But that only handles the horizontal/vertical winning positions, what about the diagonals?" You may ask. Well those were handled with two seperate **if statements** outside of the **for loop**, accounting for the diagonal from left to right and the opposite diagonal from right to left.
  
  A mistake that I almost made was forgetting to make sure the buttons aren't blank, because technically the **if statements** could be **True** if the buttons were blank but equal. To avoid this issue, I placed **and != ""** at the end. 
  
  Also, it's important to not that when using **tkinter**, **"text"** is part of the syntax, because each button or label has a built-in dictionary-like structure that holds different properties, and in this case, **"text"** refers to the text displayed on the button or label.
  
  Finally for the case of a draw, where no winning position is found, I made a giant if statement with all of the positions not equal to a blank space. 
  
  Next I will work on the smaller details of the the GUI, like resetting. 
    
    
---
Day 4 (December 13th)
---

  I didn't do much this day because I've been spending all the time I take for homework in genral on working on my tic-tac-toe GUI, and that's my fault, I should have been more organized and effcient with my time. But I'll use this day to give advice for incoming Programming Fundamentals semester 2 students:

  Specifically for those of you who have never or barely coded using Python, this class WILL be hard, expect it and prepare with necessary measures. And as I'm writing this I know it won't do much because I was basically told the same thing but made the same mistakes you guys are about to do: letting your questions go unanswered, being afraid to speak up in class, not asking for help, avoiding offic hours, and putting off homework. For a lot of you this is unlike any class you've ever taken, and any advice I could give would sound cliché and over iterated. So prove me wrong and have an amazing second semester, I'm rooting for you!

---
Day 5 (December 14th)
---

  On December 14th, the stress of not being able to finish on time (warranted in my opinion) wore off significantly once I was in the swing of things and saw how much I got done. At this point I realized it would be a good idea to create a my **game_over** function for my **button_click** function to call, which is really it's only purpose. This is when I had a little burst of excitement. The only thing **game_over** has to do is **return check_winner**. But then... oh wait, as I'm writing this I realize there's actually no point for a **game_over** function if my **if statemetns** give me **bool** values in the end. I think I was just so set on my orginial idea-which I will give myself credit, made some sort of sense in the vague beginning-that after refining and tweaking that I disregarded logic until the last second. Well, I guess I'm down to five functions.
  
  This means that I slightly over-estimated the work I would be doing today, but within the upcoming days, I will figure out a way to reset the whole grid after a draw or winner, activated by a reset button under the grid. 

---
Day 6 (December 15th)
---
