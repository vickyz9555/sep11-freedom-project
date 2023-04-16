# Working Towards MVP
##### 03/13/2023

### Content 
During the past few weeks, me and my partner have started working towards our MVP (Minimum Viable Product).

#### 02/27/2023 - 03/13/2023
Following the steps on our [MVP plan](https://docs.google.com/document/d/1szrDrbG5V1n9tMBLlT8e83kK7NH4SLwHRD-YPeLCInE/edit), we have decided on how our sprites will look like and have been making our sprites using [pixilart](https://www.pixilart.com/).

* Main Character (Koala)
* Enemy (Owl)
* Key
* Door
* Blocks
* Coin

![koala](https://user-images.githubusercontent.com/91750499/226217471-cc73ab54-22c8-475f-9af4-61c250ae4ff9.png)
![owl](https://user-images.githubusercontent.com/91750499/226219884-cb15141b-4f7f-41ad-8a74-7a11fb630285.png)
![door](https://user-images.githubusercontent.com/91750499/229255806-54cf049a-07ef-4ba3-885d-5fbe7ec88d62.png)
![coin](https://user-images.githubusercontent.com/91750499/226217476-38f84490-37f2-41d3-8479-7c0b793ca6b1.png)
![key](https://user-images.githubusercontent.com/91750499/226219003-17be3e4a-09d4-45e3-9953-86491ddd1bd9.png)

During the previous blog entry, I've had a brief intro to `solid()` and what it actually does. In the following code, I added a sprite onto the screen, including the `solid()` component which makes an object, in this case it's a sprite, can't move pass other solid objects. I added a sprite name block and also gave it the `solid()` component. Therefore, when I move the sprite near the block, it wouldn't go pass it, in other words, the block is acting as an obstable, blocking its way. 

```js
const player = add([
  sprite("koala"),
  pos(100,100),
  area(),
  solid(),
])

add([
  sprite("block"),
  pos(center()),
  area(),
  solid(),
])
```
#### Scenes
```js
scene("main", (levelIdx) => {
  const levels = [ // level layout
    // level 1
    [
      "=========================|===",
      "=px x  x      x       xx    =",
      "=  x           x      x     =",
      "=    x  x           xx   x  =",
      "= x  x            xx    x   =",
      "=   x   x     x x           =",
      "=          xxx              =",
      "=   x  o         x     x    =",
      "=        x     xx       x   =",
      "=     x    x x   x  x       =",
      "=x        x    x x x    kxx =",
      "=    x       xxx     x      =",
      "=============================",
      ], 
    // level 2
    [
      "=========================|===",
      "=p  x   x xx     x    xxx   =",
      "=  x           o      x     =",
      "= xxx xxx xx     xx   x     =",
      "= x  xxx          xx    x   =",
      "=   x   xxx     x       x   =",
      "=      x     xx  x   xxx    =",
      "=   x    xx  xxx    x    x  =",
      "=    x    x     xx       x  =",
      "=   x xx k    x x   x  x   x=",
      "=x        x  x x     xx     =",
      "= x   x  x  x     x    x   x=",
      "=============================",
      ],
    ]
```
For my mvp, I have added 2 levels to my main scene. In order to make these symbols (p, x, o, k, =, |) to work, I have assigned these symbols to its corresponding sprites. The code is shown below: 

```js
// assigning sprite to symbol
  addLevel(levels[levelIdx],{
    width: 64,
    height: 64,
    pos: vec2(64,64),
    "=": () => [
      sprite("block"),
      area(),
      solid(),
      ],
    "p": () => [
      sprite("koala"),
      area(),
      solid(),
      "player",
      ],
    "x": () => [
      sprite("coin"),
      area(),
      "coin",
      ],
    "o": () => [
      sprite("owl"),
      area(),
      solid(),
      "character",
      // message of the owl
      { msg: "Have Fun!!"},
      ],
  })

``` 

### Engineering Design Process + Skills
I am currently on step 5 of the [Engineering Design Process](https://hstatsep.github.io/students/#edp), which is creating a prototype. Throughout the whole process, me and my partner are still tinkering with our tool using the playground. We are slowly working towards the MVP of our freedom project. So far, we have make our own sprites for our platformer game. As I continue to tinker and explore with the components, I have a better understanding of how my interactive game is going to do. My next step is to continue making progress on making our own platformer game and try to improve it by adding additional pieces to our game after we have completed our MVP. Throughout this progress, I had improved in skills such as collaboration and communication. Me and my partner had to communicate with each other about how and what kind of character we want our sprites to look like. We were cooperating with each other by splitting up the sprites, where we each do a few. 

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
