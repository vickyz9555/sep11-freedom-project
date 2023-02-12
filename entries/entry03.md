# Tinkering with Kaboom

#### 02/06/2023

### Content

After a couple weeks of tinkering with [Kaboom](https://kaboomjs.com/)

#### Changing Background Color
```js
kaboom({
  background: [ 0, 200, 255 ],
})
```

#### Loading Sprite
```js
loadSprite("cinamoroll", "/sprites/cinamoroll.png")
loadSprite("coin", "/sprites/coin.png")
```

```js
for (let i = 0; i < 100; i++) {
  const x = rand(width())
  const y = rand(height())

    add([
      sprite("coin"),
      pos(x, y),
    ])
}
```h

### Engineering Design Process + Skills
I am currently still on step 5 of the [Engineering Design Process](https://hstatsep.github.io/students/#edp), which is creating a prototype. Throughout the whole process of tinkering with Kaboom, I have strengthened and improved my understanding on how to make a mini interactive game with the users. As I continue to tinker and explore with the components, I have a better understanding of what and how I want my freedom project to do. Now, it is my time to combine all the components I've learned from all the tutorials and documentations into one whole piece. My next step is to continue making my own platformer game and try to improve it. I have developed many skills throughout these few weeks on tinkering. Some skills that I had been working on is embracing failure and organization. Due to the fact that I had to learn this tool by myself, I would definitely have challenges and would have mistakes when making my mini platformer game. However, rather than being discouraged by my mistake or an error message, I had to embrace failure and keep trying. I also improve skills on organization because since I am learning this tool for the whole year, I had to take notes and keep all the things I learned in one whole place. So, when it comes to make my final freedom project, it is easier for me to comprehend and put all the pieces together.

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
