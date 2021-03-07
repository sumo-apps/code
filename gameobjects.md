[Go back to index](index.md)

# GameObjects

_GameObject is the base class that all other objects derive from._

To create a GameObject:
```javascript
var gameObject = new GameObject()
```

## position

[Vector](vectors.md), defines position in pixels.

## rotation

[Vector](vectors.md), defines rotation in degrees.

## size

[Vector](vectors.md), defines size in pixel.

## rotateAround

Please see [Image.rotateAround](images.md#rotatearound) for examples.

- `rotateAround(position, angle)`
- `rotateAround(position, angle, axis)`

Axis can also be given to rotate around an object in 3D space.
By default rotates around Z axis in 2D.

## moveAlongCurve

Please see [Image.moveAlongCurve](images.md#movealongcurve) for examples.

## Grouping

GameObjects can be grouped.

Child GameObjects will be scaled, rotated and positioned relative to the parent.

```javascript
var group = new GameObject({ position: {x: 400, y: 400}})
	
var image = new Image({ position: {x: 300, y: 300}})
var image2 = new Image({ position: {x: 500, y: 500}})

group.add(image)
group.add(image2)

group.position = { x: 400, y: 400 }
group.size = { x: 1.5, y: 1.5 }

function rotateImages() {
  group.rotation.add({ z: -1 })
}

Update(rotateImages);
```


