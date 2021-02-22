# SumoCode

Each object has
- ```position: { x: 0, y: 0, z: 0 }```
- ```rotation: { x: 0, y: 0, z: 0 }```
- ```size: { x: 0, y: 0, z: 0 }```

## Sumo.Update

Update is called once per frame

### Example 1

```js
var sumo = new Sumo.Core()

var sprite = new Sumo.Sprite()
sprite.position.x = 400
sprite.position.y = 200

sumo.add(sprite)

Sumo.Update(() => {
    sprite.position.y++;
});
```
