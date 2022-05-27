# Shooter game

[Here](https://benjaminfox1.github.io/ShooterExperiment/) is a quick experiment with using the sin function to oscillate the movements of enemies rather than using a conditional loop.

Left mouse button fires, no collision detection yet though.

<details><summary>Code Below</summary>
<p>

```javascript
// Experimenting with the sin function as a means to move aliens across a screen
// Using an array to store and then fire bullets at the enemy

var myX;
var myY;
var myOscillator;
let bullets = [];

function setup() {
  createCanvas(400, 400);
  myOscillator=1;

}

function draw() {
  background(50,150,200);

  //my hero
    fill(150,150,150);
    ellipse(
      mouseX,
      height,
      50,
      50
  );

  //enemies
  fill(250,0,100)
  
  noStroke();
  // Enemy 1
  rect(
    sin(myOscillator)*150+160,
    60,
    70,
    25
  );
  rect(
    sin(myOscillator)*150+170,
    50,
    50,
    50
  );

  // Enemy 2
  rect(
    sin(myOscillator)*-150+170,
    100,
    50,
    50
  );

  rect(
    sin(myOscillator)*-150+170,
    120,
    60,
    25
  );
  
  // Enemy 3
  rect(
    sin(myOscillator)*150+170,
    150,
    50,
    50
  );

  rect(
    sin(myOscillator)*150+160,
    160,
    75,
    20
  );

  // Enemy 4
  rect(
    sin(myOscillator)*-150+170,
    200,
    50,
    50
  );

  myOscillator = myOscillator + 0.01;

  for (let bullet of bullets)
  { 
    rect(bullet.x,bullet.y,5)
    bullet.y -=3;
  }
  strokeWeight(1);
  stroke(0);
}

function mousePressed () {
  // Create a bullet
  let bullet = {
    x: mouseX,
    y: height - 50
  }
  //push it to array labelled bullets
  bullets.push(bullet)
}
```
</p>
</details>
