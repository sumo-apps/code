# Vector

Vector represents a point in space.
Either in 3D or in 2D.

## moveAlongCurve
```javascript
var sumo = new Sumo.Core();

var image = new Sumo.Image();
sumo.add(image);

image.position = new Sumo.Vector(100, 350);

image.moveAlongCurve(1000, {
    p0: { x: 350, y: 350 },
    p1: { x: 600, y: 350 },
    p2: { x: 360, y: 350 },
    p3: { x: 350, y: 350 }
})
```

Second parameter can also be given as an array:
```javascript
image.moveAlongCurve(1000, [
    { x: 350, y: 350 },
    { x: 600, y: 350 },
    { x: 360, y: 350 },
    { x: 350, y: 350 }
]);
```


