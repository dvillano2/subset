# Subset

A Python class for representing subsets of vector spaces over the integers modulo a prime, with built-in tracking of directions and incidence structures (lines and planes).
This was designed to work for dimension three. Computations become too slow very quickly as demension grows.
This is a part of the pointconfig repo that I've broken off for independent use. 

---

## Features

- Tracks all directions determined by a subset of points.
- Computes line and plane incidence counts.
- Checks equidistribution over planes.

---

## Installation

Clone the repo:

```
git clone https://github.com/dvillano2/subset.git
cd subset
```

Make sure you have all the following files:
>
> - `subset.py`
> - `check_inputs.py`
> - `utils.py`
> - `ambientspace.py`
> - `config_types.py`

---

## Basic Usage

After cloning the repo, you can use the `Subset` class like this:

```python
from subset import Subset

# Create a subset of F_7^5 (vectors over integers mod 7, dimension 3)
subset_0 = Subset(prime=7, dimension=3)

# Add a few points
subset_0.add_point((0, 0, 0))
subset_0.add_point((1, 3, 4))
subset_0.add_point((2, 3, 4))

# Check the current points
print("Subset points:", subset_0.points)

# Check the current subset size
print("Subset size:", subset_0.size)

# See how many directions have been determined
print("Number of directions determined:", subset_0.number_of_directions_determined)

# Check line incidence
print("Max line incidence:", subset_0.max_line_incidence)

# Check for equidistributed planes
print("Number of equidistributed planes:", subset_0.number_equidistributed_planes)

# Remove a point
subset_0.remove_point((1, 3, 4))

# Check the current points
print("Subset points:", subset_0.points)

# Check the current subset size
print("Subset size:", subset_0.size)

# Add a few more points
subset_0.add_point((1, 3, 4))
subset_0.add_point((3, 3, 4))
subset_0.add_point((6, 2, 4))
subset_0.add_point((5, 1, 3))
subset_0.add_point((4, 1, 3))

# Check the current points
print("Subset points:", subset_0.points)

# Check for equidistributed planes
print("Number of equidistributed planes:", subset_0.number_equidistributed_planes)

# See the directions along which there's equidistribution
print("Equidistributed normal to the following directions:", subset_0.equidistributed_planes)
```

---

## Notes

- Removing a point with `remove_point` also updates all statistics.
- This class is really desined for three dimensions and gets too slow very quickly. For example
    ```python
    subset_0 = Subset(7, 5)
    ```
  is unworkably slow.
