# 2D - Image

## Creating image

To create image:
```javascript
var sumo = new Sumo.Core();

var image = new Sumo.Image()

sumo.add(image)
```

You can give image source in constructor:

```javascript
var sumo = new Sumo.Core();

var image = new Sumo.Image('/images/icon.png')
image.position.x = 300
image.position.y = 300
image.size = { x: 100, y: 100, z: 100 }

sumo.add(image)
```

You can also give an object in constructor:

```javascript
var sumo = new Sumo.Core();

var image = new Sumo.Image({ source: '/images/icon.png', position: { x: 300, y: 300 } });

sumo.add(image)
```