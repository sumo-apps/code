[Go back to index](index.md)

# Brush

You can use Brush to paint.

Controllable Brush:
```javascript
var brush = new Brush(Color.Beige);

// Add user input
var gamepad = new Gamepad()
gamepad.manage(brush)
```

<details markdown="1">
  <summary>See other examples</summary>

Moving controllable image that draws its path:
```javascript
var image = new Image();

var brush = new Brush(Color.Red);
image.add(brush)

var gamepad = new Gamepad()
gamepad.manage(image)

Update(() => {
    image.position.add(Vector.One)
})
```

</details>

## paintOnPress

Brush paints only when specified key is held down.

```javascript
var brush = new Brush(Color.Beige);
brush.paintOnPress('e')
```
