---
layout: post
title: Day 3
--- 

# Day 3 (December 12th)

  To begin, I needed to create what message would be displayed after the `check_winner` function, which was a fairly easy function. I just used the knowledge I gained from Day 1 and applied it to the label. I learned how to change font, font color, and font size:
  
   - `lbl.config(text=(TEXT), fg="(COLOR)")` to be put inside the `display_winner` function, so it can be updated on whether the winner is X, O, or a draw.  
  - `lbl = tk.Label(root, text="(TEXT)", font=("NAME OF FONT", FONT SIZE))` to be put at the end of everything because it's done        once, and nothing changes.

  Overall, the `display_winner` function was pretty easy and straightforward compared to the functions I've made so far, although the tricky thing about GUIs is that you can't really know if you did everything right until the final product is run.
  
  For `check_winner()`, I had to create a series of `if-else-elif` statements to encapsulate all the possible winning positions comparing each button to the next to check if they are equal, using the button indices in this format: `buttons[row][column]["text"]`. I figured a comprehensive and compact way to do this was to use a `for loop` and `range()`. I had the vague in my head idea but it was annoyingly challenging to implement. I would start typing and then think, "Wait, does this make sense?" I got a pen and paper and drew each possible tic-tac-toe combination, and what it would correspond to for the `for loop`/`if statement`. 
  
  I set up the `for loop` with a `range(3)`, and just like rows and columns, the `range()` start value is 0. The first if statement under the **for loop** had the index (i) in the row position, and the second if statement had the index as the column position, with the column and row position increasing by one in order to access each button. It's really hard to describe in writing but this ensured that after all three iterations were complete, you would capture each of the row/column winning patterns. "But that only handles the horizontal/vertical winning positions, what about the diagonals?" You may ask. Well, those were handled with two separate if statements outside of the `for loop`, accounting for the diagonal from left to right and the opposite diagonal from right to left.
  
  A mistake that I took extreme scrutiny to find out was forgetting to make sure the buttons aren't blank because technically the if statements could be `True` if the buttons were blank and equal. To avoid this issue, I placed `and != ""` at the end. 
  
  Also, it's important to note that when using `tkinter`, `"text"` is part of the syntax, because each button or label has a built-in dictionary-like structure that holds different properties, and in this case, `"text"` refers to the text displayed on the button or label.
  
  Finally, for the case of a draw, where no winning position is found, I made a giant if statement with all of the positions not equal to a blank space. 
  
  Next, I will work on the smaller details of the GUI, like resetting. 
    
    
