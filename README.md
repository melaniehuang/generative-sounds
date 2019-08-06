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
