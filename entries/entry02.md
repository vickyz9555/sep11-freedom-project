# Changing + Tinkering New Tool
#### 12/12/2022


### Content
After tinkering with [threejs](https://threejs.org/), I realized that this tool isn't really the best for the game I wanted to make since it is best use for making 3D models or buildings. For me, I wanted to make a game where there is a player and it can move around. Therefore, I closely look through the [tool list](https://docs.google.com/document/d/1oJFrErlAZvB-0V923QGOm4X3CwiceJsKot2R6Jz8Mdc/preview) again and tinkered a little through each of these tools. Then, I realized that [Kaboom](https://kaboomjs.com/) is a better choice for me to use because I can use this library to simplify creating scenes, adding layers, creating sprites, dealing with actions and collisions, adding key events, and much more others. 


#### Setting Up Kaboom
The following is how I set up my code:

```js
<script type="module">
import kaboom from "https://unpkg.com/kaboom/dist/kaboom.mjs"
kaboom();
</script>
```

##### What does the following code do?

```js
kaboom()
loadSprite("bean", "/sprites/bean.png")
const SPEED = 320
const player = add([
    sprite("bean"),
    pos(center()),
])
onKeyDown("left", () => {
    player.move(-SPEED, 0)
})
add([
    text("Press arrow keys", { width: width() / 2 }),
    pos(12, 12),
])
```

You have to use `kaboom()` to start (this is the initial code). First, this code would load assests or the character. Then, I defined the player's movement speed in pixels per second, in this case I set it to a speed of 320. The higher the number is, the faster the speed it is. Later, the player game object is added and the `center()` returns the center point which means that the player will be placed in the center whenever you restart the game. The `onKeyDown()` registers an event that runs every frame as long as user is holding a certain key. For example, if you do `onKeyDown("left",...)`, this means that the action would take place anytime you hold the left key on your keyboard. Same thing would happen with the right, up, and down key. `onClick()` registers an event that runs once when the mouse is clicked. `.moveTo()` is provided by pos() component, changing the position. In this case, it would bring your player to where the mouse is being clicked. The `text()` component is similar to `sprite()` but renders text. In the code above, it adds the text "Press arrow keys, giving it a with of width() / 2 place it at the position of (12,12).

#### Goal for Winter Break
During the winter break, my goals will be to explore how to add a [scene](https://docs.replit.com/tutorials/build-mario-with-kaboom) and trying to make my own characters and objects. If I have time, I would also try learning how to add complexity to my game such as adding levels to it. 

### Engineering Design Process + Skills
I am currently on stage 4 and 5 of the [EDP (Engineering Design Process)](https://hstatsep.github.io/students/#edp) where the main goal is to plan the most promising solution and create a prototype. To plan the most precising solution, I was tinkering with tools to see which one is the best to use for my game that I wanted to make. After deciding and locking a tool, in this case Kaboom, I started to create a small mini project and making my own platformer game using this tool which can also be known as creating a prototype. I tried adding a text to my page and letting it move freely around. Throughtout weeks of researching and tinkering, I have improved on many of the [skills](https://hstatsep.github.io/students/#skills). The most important skill I had improved on was collaboration and communication. Due to the fact that the previous tool me and my partner chose weren't the best one for us to use, we had to communicate with each other, thinking about whether or not we should change our tool, and if yes, change to what tool? I also improved skills on how to read and how to learn because I am learning Kaboom on my own through reading documentations and watching tutorials. 


[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
