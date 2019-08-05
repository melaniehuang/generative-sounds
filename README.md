# Generative Sounds x Linden New Art gallery

Today we're going to make visuals from sound with a programming language called Processing.
Processing is a programming language specifically designed for visual artists, designers and hobbyists as well as those learning how to code(so you're in safe hands!).

To run and write Processing, you would generally [download the latest version of Processing](https://processing.org/download/) but given we don't have a lot of time today - we're going to get up and running right in our browser on a variant called p5. p5.js is a JavaScript library based on Processing but is written slightly differently.

## p5 Editor
[Sign up for an account](https://editor.p5js.org/) to write your code in the browser. Create an account and press play. You can only save files when you're logged in. So to make sure you don't lose any work - make sure you're logged in.

When you've signed in, copy and paste the following into the left-hand side and let's chat about what it's doing. Press 'Play'.

```javascript
function setup() {
  //everything inside these brackets runs once
  createCanvas(450, 300);
  background(255);
}

function draw() {
  //everything inside these brackets runs over and over and over
  background(255);
  ellipse(400,400,100,100);
}
```




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
