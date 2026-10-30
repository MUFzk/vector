# vector3d

A small 3D vector class for the *OOP in Physics* course. Internals are covered in Week 4.

## Import

```python
from vector3d import Vector3D
```

## Operations

```python
a = Vector3D(1.0, 2.0, 3.0)
b = Vector3D(0.5, 0.0, -1.0)
```

| Operation | Example | Result |
|---|---|---|
| Create | `Vector3D(1.0, 2.0, 3.0)` | `(1.0, 2.0, 3.0)` |
| Components | `a.x, a.y, a.z` | `1.0 2.0 3.0` |
| Add | `a + b` | `(1.5, 2.0, 2.0)` |
| Subtract | `a - b` | `(0.5, 2.0, 4.0)` |
| Scalar multiply | `a * 2.0` or `2.0 * a` | `(2.0, 4.0, 6.0)` |
| Scalar divide | `a / 2.0` | `(0.5, 1.0, 1.5)` |
| Negate | `-a` | `(-1.0, -2.0, -3.0)` |
| Norm | `abs(b)` | `1.118...` |
| Dot product | `a.dot(b)` | `-2.5` |
| Cross product | `a.cross(b)` | `(-2.0, 2.5, -1.0)` |
| Print | `print(a)` | `(1.0, 2.0, 3.0)` |
| Repr | `a` | `Vector3D(1.0, 2.0, 3.0)` |

## Not available

- `a == b` compares identity, not components; it is `False` even for equal vectors.
- `s / a` and `s + a` raise `TypeError`.
- `a * b` (vector times vector) does **not** raise; it silently returns a tuple of vectors, which is meaningless. Use `a.dot(b)` or `a.cross(b)`.

## Physics example

```python
r = Vector3D(1.0, 2.0, 3.0)   # position, m
v = Vector3D(0.5, 0.0, -1.0)  # velocity, m/s

r_new = r + v * 0.1           # position after 0.1 s
L = r.cross(v) * 2.0          # angular momentum, m = 2 kg
```
