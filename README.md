# generative-sounds

```javascript
function setup() {
  createCanvas(450, 300);
  background(255);
}

function draw() {
  background(255);
  ellipse(width/2,height/2,100,100)
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
