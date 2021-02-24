# 2D

- [Image](image.md)

## Examples

Moving planet and moon that spins around it:
```javascript
var sumo = new Sumo.Core();

var planet = new Sumo.Image()
planet.position.x = 400
planet.position.y = 400
planet.size = { x: 100, y: 100, z: 100 }
sumo.add(planet)

var time = 0;
function planetMove() {
  planet.position.x = 600 + Math.sin(time / 100) * 300
  planet.rotation.z += 0.01;
  time++;
}

Sumo.Update(planetMove);

var moon = new Sumo.Image()
sumo.add(moon)

function moonRotate() {
  moon.rotateAround(planet.position, time)
}

Sumo.Update(moonRotate);

```

_Note that having multiple Sumo.Update() functions is possible_
