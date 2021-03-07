[Go back to index](../index.md)

# Solar system

_Note: this Sumo.Something syntax is deprecated_

Creating a solar system with planets orbiting the sun:
```javascript
var sumo = new Sumo.Core();
sumo.background = '#111'

let starImage = await Sumo.ImportImage('star');

const variance = 50;
for (let x = 0; x < 10; x++) {
  for (let y = 0; y < 10; y++) {
    let star = new Sumo.Image(starImage)
    star.position = new Sumo.Vector(x * (sumo.width / 10) + Math.random() * variance, y * (sumo.height / 10) + Math.random() * variance)
    star.size = new Sumo.Vector(16, 16)
    star.rotation = new Sumo.Vector(0, 0, 360 * Math.random())
    sumo.add(star)
  }
}

var center = new Sumo.Vector(sumo.width / 2, sumo.height / 2 - 50)

var sun = await Sumo.ImportImage('sun')
sun.position = center
sun.size = new Sumo.Vector(100, 100)
sumo.add(sun)

var planets = []

async function createPlanet(name, position, size) {
  const planet = await Sumo.ImportImage(name)
  planet.position = center.add(position)
  planet.size = size
  sumo.add(planet)

  planet.speed = Math.random() * 10 + 1
  planet.startPos = Math.random() * 1000
  planets.push(planet)
}

await createPlanet('mercury', new Sumo.Vector(60, 60), new Sumo.Vector(20, 20));
await createPlanet('venus',     new Sumo.Vector(90, 90), new Sumo.Vector(25, 25));
await createPlanet('earth',      new Sumo.Vector(120, 120), new Sumo.Vector(25, 25));
await createPlanet('mars',      new Sumo.Vector(150, 150), new Sumo.Vector(20, 20));
await createPlanet('jupiter',    new Sumo.Vector(200, 200), new Sumo.Vector(60, 60));
await createPlanet('saturn',    new Sumo.Vector(250, 250), new Sumo.Vector(100, 100));
await createPlanet('uranus',   new Sumo.Vector(300, 300), new Sumo.Vector(30, 30));
await createPlanet('neptune', new Sumo.Vector(340, 340), new Sumo.Vector(30, 30));

var time = 0;
function planetsRotate() {
  for (let i = 0; i < planets.length; i++) {
    let planet = planets[i]
    planet.rotateAround(sun.position, time * 0.01 * planet.speed + planet.startPos)
  }

  time++;
}

Sumo.Update(planetsRotate);

```

## See also

- [Images](../images.md)
- [GameObjects](../gameobjects.md)
- [Vectors](../vectors.md)
