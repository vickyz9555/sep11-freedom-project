# Tinkering with Kaboom

#### 02/06/2023

### Content

After a couple weeks of tinkering with [Kaboom](https://kaboomjs.com/), I have learned many more components and have added them into my own mini platformer game. In the last entry, I have talked about setting up Kaboom and loading & adding a sprite onto my game, allowing it to move around the map with different speeds. Looking back towards my winter goals, I have completed on creating my own character and adding it to my page. 

#### Changing Background Color
```js
kaboom({
  background: [ 0, 200, 255 ],
})
```

```js
loadSprite("cinamoroll", "/sprites/cinamoroll.png")
loadSprite("coin", "/sprites/coin.png")

for (let i = 0; i < 100; i++) {
  const x = rand(width())
  const y = rand(height())

    add([
      sprite("coin"),
      pos(x, y),
    ])
}
```

For the code above, this would load two sprites: one called cinamoroll and another one called coin. What the code on lines 20 to 27 do will make 100 of the sprite coin appear on the page at random places. Since I set the x to a random width and the y to a random height, and adding the sprite position at (x,y), this will place the sprites in different places. If you want them to appear at a specific place, you would let x and y be at a specific number. 

#### Changing Size
```js
kaboom({
	width: #,
	height: #,
	stretch: true / false,
	letterbox: true / false,
})
```
In Kaboom, if you didn't specify the width and the height, it will automatically size to the container by default. 
* `stretch` - stretches the defined width and height to fullscreen
* `letterbox` - makes stretching keeps aspect ratio (leaving black bars on empty spaces) but it will have no effect without using `stretch`

Examples: 

![Screenshot 2023-02-12 10 27 01 PM](https://user-images.githubusercontent.com/91750499/218363719-26120592-5b18-4838-a463-f082350c8373.png)

![Screenshot 2023-02-12 10 27 54 PM](https://user-images.githubusercontent.com/91750499/218363804-cfc98bd7-3920-4ccb-a9bd-4954fe305aa6.png)


#### What I plan on learning next
The plan for my next step is to learn how to make my sprite collect an object. After I completed that, I am thinking to learn about levels and adding them onto my mini platformer game to advance it. 

### Engineering Design Process + Skills
I am currently still on step 5 of the [Engineering Design Process](https://hstatsep.github.io/students/#edp), which is creating a prototype. Throughout the whole process of tinkering with Kaboom, I have strengthened and improved my understanding on how to make a mini interactive game with the users. As I continue to tinker and explore with the components, I have a better understanding of what and how I want my freedom project to do. Now, it is my time to combine all the components I've learned from all the tutorials and documentations into one whole piece. My next step is to continue making my own platformer game and try to improve it. I have developed many skills throughout these few weeks on tinkering. Some skills that I had been working on is embracing failure and organization. Due to the fact that I had to learn this tool by myself, I would definitely have challenges and would have mistakes when making my mini platformer game. However, rather than being discouraged by my mistake or an error message, I had to embrace failure and keep trying. I also improve skills on organization because since I am learning this tool for the whole year, I had to take notes and keep all the things I learned in one whole place. So, when it comes to make my final freedom project, it is easier for me to comprehend and put all the pieces together.

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
