# Workshop 1: Introducing JavaScript with P5.js

Collaborators: [your github username] & [your partners github username]

Make sure you’re working in pairs - on a single laptop. You’ll be **pair
programming**. In pair programming, there are two roles - **driver** and
**navigator**.

The **driver** is at the keyboard. They’re responsible for typing and figuring
out syntax. They shouldn’t make decisions though! That’s the responsibility of
the **navigator**. They make decisions, and ask the driver to implement them.

Start by forking this repo:
![fork button](https://readme-pics.s3.amazonaws.com/fork_button.jpg)

Forking creates a copy of this repo in your own GitHub account. Add your partner
as a collaborator by going to 'Settings' > 'Collaborators & teams' and entering
their GitHub username in the 'Collaborators' box. That means you'll both have
access to the repo.

You should now have a copy of this git repository in your own github account.
Now, we need to get a copy on our own laptop for us to work with. Start by
opening a terminal and creating a projects/ada folder if you don't already have
one:

```sh
cd Desktop
mkdir Projects
cd Projects
```

Next, we need to clone the repo. This copies all the files and history from
github to our own computer:

```sh
git clone https://github.com/<your github username>/di-workshop-01-intro-to-p5.git
cd di-workshop-01-intro-to-p5
```

You can see that it's a git repository and some of the history by running these
commands:

```sh
git status
git log
```

> **Note:** If you get stuck in `git log`, it's because you're in something
> called a pager. This is a really old bit of software from before computers
> could scroll in the way we're used to. You can move up and down in the pager
> with your arrow keys, and exit it by pressing `q`

Finally, we need to install some bits and pieces that in our new repo to finish
setting it up:

```sh
npm install
```

---

We’ll be working with some software called P5. P5 is a **JavaScript library**
for drawing shapes - it’s used for making simple games and cool generative art.

For each of the **bold** questions below:

<h3 align="center">
  🗣 Discuss &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  👩‍💻 Change &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  👀 Observe &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  🔄 Repeat
</h3>

1. **🗣 Discuss** the question with your partner
1. **👩‍💻 Change the code** - what do you expect your changes to do?
1. **👀 Observe the results** - what happened when you ran your code? How did it
   differ from your expectations
1. **🔄 Repeat** - keep discussing, changing, and running the code until you
   feel you understand it

**The aim of this workshop is _exploration_, hopefully leading to
_understanding_. It’s really important that you _take your time_. The questions
below are _guidelines_, meant to prompt your _curiosity_. If you can’t answer a
question, use a search engine or ask someone nearby. Don’t move on until you
_fully understand_ what’s happening.**

**Explore and have fun! Be curious!**

# Setup

Now you've got the repo cloned and installed, we need to start it up:

```sh
npm start
```

This runs a web server - a little program that your browser can connect to so
that the files you write in this project can run in there. Now, when you visit
http://localhost:5000/, you'll see all your files right there.

Open the workshop folder in your editor. In VSCode, choose File > Open and
select the folder - _not any of the files inside it_. You should see all the
workshop files in the left-hand file pane.

Open this file - README.md - in your editor. Make notes in here about everything
you do. If you don't know the answer to a question, it's your job to experiment
with the code to see what you can find out.

# Sketch A

Open the `part-a` sketch in your browser, and open `part-a/sketch.js` in your
editor. The code in `sketch.js` is what's running on the page. Every time you
make a change in `sketch.js`, you need to save the file (ctrl-S or cmd-S) and
refresh your web browser (ctrl-r or cmd-r) to see the change.

---

Look at these lines:

```js
var r = 255
var g = 80
var b = 0
```

**What might these lines do?**
They store information under each declared variable e.g. variable r = colour code 255
**What happens if you change the numbers?**
Changes the colour code assigned to the variable. It calls the background function, which uses the varaibles as parameters
**What numbers are allowed / What numbers have an effect?**
0-255
Look at this line:

```js
createCanvas(400, 400)
```

**What does createCanvas do?**
Creates a square with a pixel dimension of 400x400
**What happens if you change the numbers?**
Changes the size and shape of the square
**What numbers are allowed/what numbers have an effect?**
Only positive numbers
**What happens if you add/remove a number?**
The parameters width and height are required when declaring the createCanvas variable. If one of those parameters are to be removed, a default canvas is created 100px by 100px - but doesn't allow colour.

**Can you guess what the `function setup() {` part does? What happens if you
change the name of setup?**
The setup function is predefined in the P5 library and allows the browser to execute the functions stored within that library.

L ook at this line:

```js
background(r, g, b)
```

**What does background do?**
The background function takes the parameters (numbers) and sets the background colour for the shape we created with createCanvas function. Parameters are numbers between 0-255, we store them in r, g and b variables

**What happens if you change the order of the letters in background? What does
this tell you about how the computer uses them?**

It would change the colour of the shape. Function 'background' takes 3 parameters in the order: red, green and blue.

**What happens if you change the number of letters?**
It only retrieves information from the three parameters r, g and b. If anything else is declared it'll be ignored and an error/bug may occur 
**What happens if you change the letters for different ones?**
The function wont be called and an error will occur. We must declare the new variables to allow it to work.
# Sketch B

Open the `part-b` sketch in your browser, and open `part-b/sketch.js` in your
editor.

Read the code and play with the sketch in your browser.

> **Note**: There's two main sections in the code - the bit called `setup` and
> the bit called `draw`. The code in the `setup` section runs **once**, when
> your program first starts up. The code in the `draw` section runs again and
> again and again - 60 times every second.

Look at these lines:

```js
function setup() {
  createCanvas(400, 400)
  background(0, 0, 0)
}
```

**What does setup do?**
The setup function retrieves information from the project files and declares the canvas size and the background colour of the canvas

**What do `{` `}` mean? What happens if you remove one?**
The { brackets limit the function. Removing one will not allow the code to be executed.

**What do the numbers in `background(0, 0, 0)` do? What happens when you change
them? How is this different from Sketch A?**

Now look at these lines:

```js
function draw() {
  fill(255, 0, 0)
  ellipse(mouseX, mouseY, 30, 30)
}
```

**What does draw do?**
The draw function takes the information from the fill and ellipse variables. These variables produce a result of a 30x30 circles to be created in accordance with the position of the mouse. The circles are filled with the colour declared in the fill variable.
Now look at:

```js
fill(255, 0, 0)
```

**What do these numbers do? What happens when you change them?**
These numbers are rgb colour variables and inform the program to produce a particular colours based on the set parameters.
**What does fill mean? What happens if you change it to stroke?**
The fill variable infroms the program to fill the ellipses with the rgb colour 255, 0, 0. If changed to a 
storke variable then only the outline of function will change colour
**What happens if you remove (or comment out) this line? What about if you include both fill and stroke on seperate lines?**
If you include both fill and stroke variables then it allows the user to change the colour of both the outline and fill of the shape.
Now look at this line:

```js
ellipse(mouseX, mouseY, 30, 30)
```

**What does `ellipse` do?**
It makes the draw function produce a circle.
**What happens if you change the numbers?**
The size of the ellipses produce changes in accordance with the size of the numbers
**What do `mouseX` and `mouseY` mean?**
These are declared variables that track the position of the mouse along x and y axis. 
**What happens if you change the order of the items between the `(` `)`?**

---

**What happens if you add `background(0)` after `draw() {`? Why?**
The program no longer fills the background of the canvas, meaning that the canvas can no longer be seen.

Replace the ellipse with a triangle. Use https://p5js.org/reference/ (the 2D
primitives section) to help.

Play around with the sketch - how else can you change it?

# Sketch C

Open the `part-c` sketch in your browser, and open `part-c/sketch.js` in your
editor.

Read the code, then play with the sketch and observe what happens - try clicking
the mouse on the sketch.

Look at:

```js
if (mouseIsPressed) {
  fill(255, 0, 0)
} else {
  fill(0, 255, 0)
}
```

**What does `mouseIsPressed` mean?**
The mouseIsPressed variable creates the instruction for the program to fill the ellipse with rgb(255, 0, 0) when the mouse is pressed. An if/else statement is used, meaning that when the mouse isn't pressed, the ellipse is filled with
rgb(0, 255, 0).
**What happens if you change `mouseIsPressed` to `keyIsPressed`?** You’ll need
to click on the sketch so it registers keyboard events – use the ctrl key if you
have issues with the keyboard.
The mouseIsPressed doesn't contain any information of the function, so nothing changes.
**What does if / else do?**
An if/else statement is used to determine whether an action should be taken, based on whether or not of the statement is true. The else part of the if/else statement creates an exception to the if statement, allowing for new actions to commence if the original statement is false.
**What happens if you remove the { } or ( )? Why?**
The parentheses contain the expressions which are to be executed if they are removed then the expressions cannont be executed so only a blank page is shown.
**What happens if you change 255 to mouseX ? Why?**
the 255 variable controls the width of the shape, it changed to mouseX then the width of the shape will be controlled by the mouses position on the X axis
**Remove the outline of the circle. Use Google and the P5.js reference to help
you.**

# Challenge

In your pairs, take the code in sketch c and adapt it into a simple paint
program. The user should be able

- click and drag to paint on the screen
- press keys on the keyboard to choose a colour
  - e.g. pressing ‘r’ changes the paint colour to red, pressing ‘g’ changes the
    paint colour to green.

Use this code as a starting point:

```js
if (keyIsPressed) {
  if (key == 'r') {
    // set paint colour to red
  }
  if (key == 'g') {
    // set paint colour to green
  }
  // add more keys/colours
}
```

**Document your process in this file.**

## Extension

- Change the shape of the brush (explore other shapes like squares or triangles)
  based on a key pressed
- Change the size of the brush based on a key pressed.

Notes