# Finalizing MVP
##### 04/17/2023

### Context
During the past month, me and my partner have come to an end of finishing our [MVP](https://kaboommvp.joeyl2331.repl.co/). As shown in the previous blog, we have build our scene. Adding on, we have added the movement of our main character sprite, levels, dialogs, getting the key and going to the next level, and a win & lose scene.

#### Movement 
We added the directions which gave the character sprite the ability to move left, right, up, and down using the `keyDown` component. Everytime the key is pressed, we gave it a scale of 300 which is the movement speed (how fast or slow the sprite moves).

```js
// directions
  const dirs = {
    "left": LEFT,
    "right": RIGHT,
    "up": UP,
    "down": DOWN,
  }

  
  for (const dir in dirs){
    onKeyDown(dir,() => {
      player.move(dirs[dir].scale(300)) // movement speed
    })
  }
```

#### Levels
We have also added more levels to our game, increasing the difficulty as the level increases. The way our game works is that you have to collect the key without touching the owls and getting to the next level by touching the door after you have gotten the key. Once you touch the owl, it brings you to the lose scene, but if you have completed all the levels, it would bring you to the win scene. In the previous blog, we have added level 1 and 2. We then added levels 3 and 4, where we placed more and more owls (the enemy).

```js
// level 3
    [
      "=========================|===",
      "=p  x   x xx     x    xxx   =",
      "=   x           o      x    =",
      "= xx o  x xx      x   x   o =",
      "= x              xx    x    =",
      "=   x   x x     x  ko   x   =",
      "=      x     xx  x    xx    =",
      "=   x     x  x x    x    x  =",
      "=    x    x     xx       x  =",
      "=   x xx  o   x x   x  x   x=",
      "=x           x x      x     =",
      "= x   x  x  x     x    x   x=",
      "=============================",
      ],
    // level 4
    [
      "=========================|===",
      "=p  x        x    o x o x   =",
      "=        o     o x      x   =",
      "= xxx o x  xx      x   x  o =",
      "= x  x            xx    x   =",
      "=   x     x    o x       x  =",
      "=      x      x  x   xxx    =",
      "=   o    xx  o xx    x    x =",
      "=       ko      xx     xx   =",
      "=   x xx      xx     xx     =",
      "=x           x x  o  xx  o  =",
      "= x xxx         x    xxx    =",
      "=============================",
      ],
    ]
 ```
 
#### Collision
###### Step 1: Player has No Key
`let hasKey = false`
###### Step 2: Coin Disappear if Touched
```js
// when player touches coin, coin disappears
player.onCollide("coin", (coin) => {
  destroy(coin)
})
```
###### Step 3: Key Disappear if Touched & Player has Key
```js
player.onCollide("key", (key) => {
  destroy(key)
  hasKey = true // player has key
})
```
###### Step 4: When Player Touches the Door
```js
player.onCollide("door", () => {
    if (hasKey){ // has key
      // go next level
      if(levelIdx + 1 < levels.length){ 
          go("main", levelIdx + 1)
      } else { // player was on the last level
          go("win")
      }
    } else { // has no key
      dialog.text = "you need a key!" // the dialog that would appear on the screen if the character touches the door AND has no key
    }
})
```
###### Step 5: Creating Lose Scene
```js
// lose scene
scene("lose", () => {
  add([
    text("You Lose"),
    pos(width()/2, height()/2),
    origin("center"),
  ])
})

// sprite touches owl and goes to lose scene
player.onCollide("character", () => {
  go("lose")
})
``` 
###### Step 6: Creating Win Scene
```js
scene("win", () =>{
  add([
    text("YAYYY You Win!"),
    pos(width()/2, height()/2),
    origin("center"),
  ])
})
```

### Engineering Design Process + Skills
We are currently on step 5 of the [EDP](https://hstatsep.github.io/students/#edp) which is creating a prototype. We have made an interactive game between the users and the sprites. our next step is to continue working towards our prototype and improving it as needed, going beyond our MVP. We can make it more advanced by adding some data based information or timing each level (any sort of ways to make the game more fun and interesting). Throughout this process of making this MVP, I have gained several [skills](https://hstatsep.github.io/students/#skills) such as <strong>problem decomposition / debugging, growth mindset, </strong> and <strong> embracing failure.</strong> I had been learning how to debug by reading the errors using the console. Many times, I have realized that it was mostly the brackets that made an error so I had to go back and check where I'm missing a bracket or wrote an extra bracket. But it was so difficult finding where the mistake is and rather than being discouraged by this, I had a growth mindset. Therefore, I tried re-writing the code one step at a time and this time carefully checking all the bracket notations specifically, making sure I don't make the mistake over and over again. 

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
