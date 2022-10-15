# Love2d is a game framework

## Main functions
The `love.load()` function is a function that runs once when the game starts. you can use this to initiate variables and functions and what-not.
```
function love.load()
	number = 0
end
```

The `love.upadate()` function runs every frame, 60fps by default. this function acts as your main game loop. notice it takes an argument `dt`.
```
function love.update(dt)
	number = number + 1
end
```

The last main function is `love.draw()`. this draws objects to the screen, and also runs every frame.
```
function love.draw()
	love.graphics.print(number)
end
```

keep in mind that this specific `love.graphics.print()` function will only work in the `love.draw()` function.

## Graphics functions
Most graphical functions take some variant of these parameters:
- `mode`: either `"fill"` or `"line"` which decided whether or not the primative graphic is filled or not.
- `x` and `y`: the position of the top left coner of the object within the world
- `width` and `height`: the actual size of the graphic, its width and height repsectivly.

## Creating a .love file
on linux:
```
zip -9 -r SuperGame.love .
```
