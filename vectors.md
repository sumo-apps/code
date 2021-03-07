[Go back to index](index.md)

# Vectors

Vector represents a point in space with (x, y, z) coordinates.
Either in 3D or in 2D.

## rotateAround

Please see [Image.rotateAround](images.md#rotatearound) for examples.

- `rotateAround(position, angle)`
- `rotateAround(position, angle, axis)`

Axis can also be given to rotate around an object in 3D space.
By default rotates around Z axis in 2D.

## moveAlongCurve

Please see [Image.moveAlongCurve](images.md#movealongcurve) for examples.

## Shorthands

```javascript
Vector.One // new Vector(1, 1, 1)
Vector.Right // new Vector(1, 0, 0)
Vector.Left // new Vector(-1, 0, 0)
Vector.Up // new Vector(0, 1, 0)
Vector.Down // new Vector(0, -1, 0)
Vector.Toward // new Vector(0, 0, 1)
Vector.Away // new Vector(0, 0, -1)
```

## add

```javascript
var v = new Vector(2, 2, 2)
v.add(2)

// (4,4,4)
```

<details markdown="1">
  <summary>See other examples</summary>

```javascript
var v = new Vector(2, 2, 2)
v.add(new Vector(1, 2, 3))

// (3,4,5)
```

or

```javascript
var v = new Vector(2, 2, 2)
v = Vector.add(v, new Vector(1, 2, 3))

// (3,4,5)

```

or

```javascript
var v = new Vector(2, 2, 2)
v.add({ y: 2 })

// (2,4,2)
```

</details>

## subtract

```javascript
var v = new Vector(2, 2, 2)
v.subtract(1)

// (1,1,1)
```

<details markdown="1">
  <summary>See other examples</summary>

```javascript
var v = new Vector(2, 2, 2)
v = Vector.subtract(v, new Vector(1, 2, 3))

// (1,0,-1)

```

or

```javascript
var v = new Vector(2, 2, 2)
v.subtract(new Vector(1, 2, 3))

// (1,0,-1)
```

</details>

## multiply
```javascript
var v = new Vector(2, 2, 2)
v.multiply(2)

// (4,4,4)
```

<details markdown="1">
  <summary>See other examples</summary>

```javascript
var v = new Vector(2, 2, 2)
v.multiply(new Vector(1, 2, 3))

// (2,4,6)
```

</details>

## divide

```javascript
var v = new Vector(6, 6, 6)
v.divide(2)

// (3,3,3)
```

<details markdown="1">
  <summary>See other examples</summary>

```javascript
var v = new Vector(6, 6, 6)
v.divide(new Vector(3, 2, 1))

// (2,3,6)
```

</details>
