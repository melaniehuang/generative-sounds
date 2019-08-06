# Generative Sounds x Linden New Art

Today we're going to make visuals from sound with a programming language called Processing.
Processing is a programming language specifically designed for visual artists, designers and hobbyists as well as those learning how to code(so you're in safe hands!).

To run and write Processing, you would generally [download the latest version of Processing](https://processing.org/download/) but given we don't have a lot of time today - we're going to get up and running right in our browser on a variant called p5. p5.js is a JavaScript library based on Processing but is written slightly differently.

## p5 Editor
[Sign up for an account](https://editor.p5js.org/) to write your code in the browser. Create an account and make sure you're signed in successfully. You can only save files when you're signed in. So to make sure you don't lose any work - make sure you're signed in. Once you're in - press 'Play'. A gray square should appear to the right of the text on screen.

![](https://i.imgur.com/uvsn0PS.png)

When you've signed in, copy and paste the following into the left-hand side and let's chat about what it's doing. Press 'Play'.

```javascript
function setup() {
  //this runs once
  createCanvas(450, 300);
  console.log("Hello world!");
}

function draw() {
  //this runs over and over and over
  console.log("Hello friend!");
}
```

You've successfully written your first sketch!

Functions are like mini programs and the main two functions that exist in p5 are setup() and draw(). setup() runs once at the start of our sketch and draw() runs over and over again on repeat until you press stop.

So here we've told the computer to:
1. Create a canvas 450px wide and 300px tall
2. Log the words "Hello world!" in the console
3. Every time we run the function draw(), log the words "Hello friend!"

## My first rectangle
Now let's do something more exciting. Let's draw a rectangle and see what's going on.

```javascript
function setup() {
  //this runs once
  createCanvas(450, 300);
  console.log("Hello world!");
}

function draw() {
  //this runs over and over and over
  rect(100,100,50,50);
}
```

Can you describe what is happening in this sketch in plain english? Change some numbers and it should become fairly obvious :)

## Co-ordinates

To tell the computer where to draw something, you will need to give it an x and y coordinate. You may remember these bad boys from maths class but in Computer Graphics, it’s a little different.

The top left corner (x,y) is (0,0). The x coordinates increase to the right, the y coordinates INCREASE moving down the canvas.

```javascript
(0,0)___________ (900,0)
|                      |
|                      |
|                      |
|                      |
|                      |
|                      |
|                      |
(0,900) ________ (900,900)
```

Therefore rect() accepts the following 4 parameters:

```javascript
//rect(x, y, width, height);
rect(0, 0, 200, 200);
```

By default, rect() accepts the x & y position of the rectangle’s top left corner.
Now, let’s add some colour!

## Colours!


```javascript
var mic;

function setup() {
  createCanvas(1800, 1200);
  background(255);
  mic = new p5.AudioIn();
  mic.start();
}

function draw() {
  //background(255);
  micLevel = mic.getLevel();
  ellipse(width/2,height/2,micLevel*3000,micLevel*3000)
}

function keyPressed(){
  if(key == 's'){
    save("frame.jpg");
  }
}
```
