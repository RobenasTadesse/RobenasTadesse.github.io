---
Day 8 (December 17th)
---

  I just realized that each of our functions needed to **assert** statements because I overheard Lux talking to another student, so I quickly did those. I ran into the challenge of testing for the display messages because I didn't have a way to test for the "current" message. After some thinking that got me nowhere, I decided to look through the numerous methods **tkinter** had under Python 3.13.1 documentation. A method called **.cget()** seemed to serve my purpose. I don't know if this is true but I like to think that **.cget()** stands for "current get," and it basically retrieves the current state of a widget (for my purpose widgets are buttons or labels). It was really helpful for me when I was creating my **assert** statements. Here's the general syntax:

  **label = tk.Label(root, text="Hello")**
  
  **label.pack()**
  
  **print(label.cget("text")) # It would print "Hello" from the label.** 
