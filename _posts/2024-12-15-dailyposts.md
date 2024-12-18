---
Day 6 (December 15th)
---

  Today I configured the the reset button and connected it to a function. I just reused the concepts I learned for creating and positioning buttons, there is nothing new about the reset button. So I know the **reset_game()** function needs to do three things: reset the **global** variable, **current_player**, reset the 3x3 grid of buttons back to their original blank state, and clear the winner/draw message. The first part was easy: calling the global variable **current_player** and setting it back to "X." The next step was to clear the board, reverting each button to a blank state. To do this, I used the same two nested **for loops** with **range(3)** in the "create 3x3 grid" part of the program. After that it was just a matter of using **buttons[row][col].config(text = "")**. Lastly, to remove the winner/draw message I used the same **.config()** method but outside of the two **for loops** because it only needed to happen once. 
  
  Next, I will spend the final days preparing for my presentation, because even though people tell me I don't seem nervous while presenting, my mind is always frantically racing when I have to present anything. So I'll plan everything so things go smoothly and naturally. 
