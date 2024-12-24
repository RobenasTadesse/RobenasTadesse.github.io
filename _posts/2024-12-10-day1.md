---
layout: post
title: Day 1
---

# December 10th

Hello! Apologies for the lateness, I was busy.

  On December 10th, I began my journey to create a Graphical User Interface for the tic-tac-toe game. I decided to dive right in and took Lux's advice to use the `tkinter` library. Tkinter is one of the standard libraries in Python, like `plotly`, `math`, and `random`.

  I think this project would be interesting to implement because games are playable, cool, and enjoyable to interact with. I also feel like we've talked about GUIs a lot these past several months and I would like to bring my thoughts to life. When (hopefully not if?) I am successful at completing this project, I would be proud of my accomplishment because I think what most people think of when coding comes to mind is somebody who can either make a website or a game. Actually, even if I get a bug that I cannot solve in time, I would still feel proud of the amount I will learn. 
  
  Now, for just one day, I learned much more than I expected. The first thing I learned was that I could not use the `tkinter` library in Google Colab, because it does not support GUI stuff. So then I downloaded Homebrew from my Terminal application, and I already had Python on my computer so that was good. Next, I decided it would be a good idea to install and launch Jupyter Notebook because I could edit it from my web browser kind of like Colab, but it would support `tkinter`. Here I made it sound like the process was smooth, but there was a lot of troubleshooting and dumbfoundedness. But the problems were pretty simple, just being told `zsh: command not found: brew` and `zsh: command not found: jupyter` and on my Terminal. Nevertheless, it required quite a bit of research to solve.   
  
  Next, I familiarized myself with the Juypter and began learning about the basics of tkinter. I honestly love how straightforward the library is, the syntax just feels so logical. To start off anything with `tkinter`, you have to `import tkinter as tk`. To test if everything is up and running, you write `tk._test`, causing a Python window to pop up confirming that everything is working. A tedious thing with the Jupyter Notebook-Python window setup is when you run the code, it won't change anything on the window until you close out of it and run the code on Juypter again.  
  
  To initialize a new window for the GUI, you say `root = tk.Tk()`. Something I found really interesting as was that if you run that, alone, nothing new will pop up. This is because the application is being opened and closed too quickly to notice. A way to solve that issue is to say `root.mainloop()`, and this basically keeps the window open for you to see. What we have right now is the template/scaffolding/canvas for the whole GUI. All the code will be sandwiched between **import tkinter as tk** and `root.mainloop()` To name the window you do `root.title("(TITLE GOES HERE)")`. I named mine "Tic-Tac_Toe GUI."
  
  I then moved on to the basics of actually implementing a GUI: 
  - To make a button you say `btn = tk.Button(root, text = "(WRITING ON THE BUTTON)", command = (A FUNCTION NAME))`.
      - Position the button: `btn.grid(row = __ , column = __)` rows/columns start at 0, just like `range()`
  - Above the button to make a label: `lbl = tk.Label(root, text = "(WRITING FOR LABEL)")`
      - Position the button: `lbl.grid(row = __, column = __, columnspan =__)` columnspan indicates how many columns are take up         by the label, and also starts at 0.  

The next day I worked on creating a basic interface with a grid and buttons that update based on player moves. I am thinking of doing a thing where each mouse click will alternate after each click. Like it will start with "X" and then go to "O" and so on until there is a winner or draw. After I achieve this I'll add the ability to actually claim a winner (either "X"/"O" or perhaps asking for each player's name?). But anyway, after I make the game I will make the game look colorful and fun to interact with. Also, I think this post is too long so I'll try to condense it in the next post. 
