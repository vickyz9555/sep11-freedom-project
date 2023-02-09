# Tinkering with Kaboom

### Content

##### Changing Background Color
```js
kaboom({
  background: [ 0, 200, 255 ],
})
```


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
```

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
