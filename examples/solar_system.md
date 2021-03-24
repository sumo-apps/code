[Go back to index](../index.md)

# Solar system

Creating a solar system with planets orbiting the sun:
```javascript
let starImage = await ImportImage('star');

const variance = 50;
for (let x = 0; x < 10; x++) {
  for (let y = 0; y < 10; y++) {
    let star = new Image(starImage)
    star.position = new Vector(x * (width / 10) + Math.random() * variance, y * (height / 10) + Math.random() * variance)
    star.size = new Vector(16, 16)
    star.rotation = new Vector(0, 0, 360 * Math.random())
  }
}

var center = new Vector(width / 2, height / 2 - 50)

var sun = await ImportImage('sun')
sun.position = center
sun.size = new Vector(100, 100)

var planets = []

async function createPlanet(name, position, size) {
  const planet = await ImportImage(name)
  planet.position = center.add(position)
  planet.size = size

  planet.speed = Math.random() * 10 + 1
  planet.startPos = Math.random() * 1000
  planets.push(planet)
}

await createPlanet('mercury', new Vector(60, 60), new Vector(20, 20));
await createPlanet('venus', new Vector(90, 90), new Vector(25, 25));
await createPlanet('earth', new Vector(120, 120), new Vector(25, 25));
await createPlanet('mars', new Vector(150, 150), new Vector(20, 20));
await createPlanet('jupiter', new SVector(200, 200), new Vector(60, 60));
await createPlanet('saturn', new Vector(250, 250), new Vector(100, 100));
await createPlanet('uranus', new Vector(300, 300), new Vector(30, 30));
await createPlanet('neptune', new Vector(340, 340), new Vector(30, 30));

var time = 0;
function planetsRotate() {
  for (let i = 0; i < planets.length; i++) {
    let planet = planets[i]
    planet.rotateAround(sun.position, time * 0.01 * planet.speed + planet.startPos)
  }

  time++;
}

Update(planetsRotate);

```

## See also

- [Images](../images.md)
- [GameObjects](../gameobjects.md)
- [Vectors](../vectors.md)
