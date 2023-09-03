# Color-Game-Using-Python
# import the modules
import tkinter
import random
 
# list of possible colour.
colours = ['Red','Blue','Green','Pink','Black',
           'Yellow','Orange','White','Purple','Brown']
score = 0
 
# the game time left, initially 30 seconds.
timeleft = 30
 
# function that will start the game.
def startGame(event):
     
    if timeleft == 30:
         
        # start the countdown timer.
        countdown()
         
    # run the function to
    # choose the next colour.
    nextColour()
 
# Function to choose and
# display the next colour.
def nextColour():
 
    # use the globally declared 'score'
    # and 'play' variables above.
    global score
    global timeleft
 
    # if a game is currently in play
    if timeleft > 0:
 
        # make the text entry box active.
        e.focus_set()
 
        # if the colour typed is equal
        # to the colour of the text
        if e.get().lower() == colours[1].lower():
             
            score += 1
 
        # clear the text entry box.
        e.delete(0, tkinter.END)
         
        random.shuffle(colours)
         
        # change the colour to type, by changing the
        # text _and_ the colour to a random colour value
        label.config(fg = str(colours[1]), text = str(colours[0]))
         
        # update the score.
        scoreLabel.config(text = "Score: " + str(score))
 
 
# Countdown timer function
def countdown():
 
    global timeleft
 
    # if a game is in play
    if timeleft > 0:
 
        # decrement the timer.
        timeleft -= 1
         
        # update the time left label
        timeLabel.config(text = "Time left: "
                               + str(timeleft))
                                
        # run the function again after 1 second.
        timeLabel.after(1000, countdown)
 
 
# Driver Code
 
# create a GUI window
root = tkinter.Tk()
 
# set the title
root.title("COLORGAME")
 
# set the size
root.geometry("375x200")
 
# add an instructions label
instructions = tkinter.Label(root, text = "Type in the colour"
                        "of the words, and not the word text!",
                                      font = ('Helvetica', 12))
instructions.pack()
 
# add a score label
scoreLabel = tkinter.Label(root, text = "Press enter to start",
                                      font = ('Helvetica', 12))
scoreLabel.pack()
 
# add a time left label
timeLabel = tkinter.Label(root, text = "Time left: " +
              str(timeleft), font = ('Helvetica', 12))
               
timeLabel.pack()
 
# add a label for displaying the colours
label = tkinter.Label(root, font = ('Helvetica', 60))
label.pack()
 
# add a text entry box for
# typing in colours
e = tkinter.Entry(root)
 
# run the 'startGame' function
# when the enter key is pressed
root.bind('<Return>', startGame)
e.pack()
 
# set focus on the entry box
e.focus_set()
 
# start the GUI
root.mainloop()



Code Explanation:

The code starts by importing the necessary modules.
The tkinter module provides the basic interface for creating graphical user interfaces in Python.
Next, the colors variable stores a list of six colours, as well as a score variable.
The startGame() function is called when the game starts.
This function initializes some variables and sets up the game play.
First, it checks to see if time has expired (in which case the game is over).
If time hasn’t expired, then it runs the countdown() function to keep track of how much time is left in the game.
Finally, it sets up two labels—one to display the current time left and another to display the player’s score.
Next, we create a driver code block that creates and displays a window onscreen.
We set its title and size before adding an instructions label to it.
The instructions label contains text that tells players what they need to do in order to play this game: type in one of six colour values into the text entry box below it, not just word text!
After you type in your colour value, hit enter key on your keyboard to submit it and begin playing!
The code creates a window that has the title “COLORGAME” and a label for instructions.
The window is 375×200 pixels in size, and the label is added to the window at (0, 0).

The next section of code sets up some variables.
The first variable, ‘colours’, stores an array of six colours: Red, Blue, Green, Pink, Black, and Yellow.
The second variable, ‘score’, stores the current score of the game.
The third variable, ‘timeleft’, keeps track of how much time is left in the game.
The next section of code creates a function called ‘startGame’.
This function will be used to start the game timer when it is clicked on by the user.
