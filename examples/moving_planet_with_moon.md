[Go back to index](../index.md)

# Moving planet with moon

Moving planet and moon that spins around it:
```javascript
var planet = new Image()
planet.position.x = 400
planet.position.y = 400
planet.size = { x: 100, y: 100, z: 100 }

var time = 0;
function planetMove() {
  planet.position.x = 600 + Math.sin(time / 100) * 300
  planet.rotation.z += 0.01;
  time++;
}

Update(planetMove);

var moon = new Image()

function moonRotate() {
  moon.rotateAround(planet.position, time)
}

Update(moonRotate);

```

_Note that having multiple Update() functions is possible_

## See also

- [Images](../images.md)
- [GameObjects](../gameobjects.md)
- [Vectors](../vectors.md)
