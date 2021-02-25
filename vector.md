[Go back to index](index.md)

# Vector

Vector represents a point in space.
Either in 3D or in 2D.

## moveAlongCurve

`moveAlongCurve(duration, curve)` moves vector for the set duration on given [bézier curve](https://en.wikipedia.org/wiki/B%C3%A9zier_curve).

- `duration` duration of movement in milliseconds
- `curve` 4 points that represent the curve

```javascript
var sumo = new Sumo.Core();

var image = new Sumo.Image();
sumo.add(image);

image.position = new Sumo.Vector(200, 150);

image.moveAlongCurve(1000, {
    p0: { x: 200, y: 150 },
    p1: { x: 300, y: 450 },
    p2: { x: 50, y: 340 },
    p3: { x: 200, y: 150 }
})
```

![preview](images/curve-preview.gif)

<details>
  <summary>See other examples</summary>

Curve can also be given as an array:
```javascript
image.moveAlongCurve(1000, [
    { x: 350, y: 350 },
    { x: 600, y: 350 },
    { x: 360, y: 350 },
    { x: 350, y: 350 }
]);
```

Curve can also be in 3D:
```javascript
image.moveAlongCurve(1000, {
    p0: { x: 350, y: 350, z: 400 },
    p1: { x: 600, y: 350, z: 400 },
    p2: { x: 360, y: 350, z: 400 },
    p3: { x: 350, y: 350, z: 400 }
})
```

Or with vectors:
```javascript
image.moveAlongCurve(1000, {
    p0: new Sumo.Vector(350, 350, 400),
    p1: new Sumo.Vector(600, 350, 400),
    p2: new Sumo.Vector(360, 350, 400),
    p3: new Sumo.Vector(350, 350, 400),
})
```
</details>
