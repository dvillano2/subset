# Subset

A Python class for representing subsets of vector spaces over the integers modulo a prime, with built-in tracking of directions and incidence structures (lines and planes).

---

## Features

- Tracks all directions determined by a subset of points.
- Computes line and plane incidence counts.
- Checks equidistribution over planes.

---

## Installation

Clone the repo and make sure you have all the following files:
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

# Create a subset of F_7^5 (vectors over integers mod 7, dimension 5)
subset_0 = Subset(prime=7, dimension=5)

# Add a few points
subset_0.add_point((0, 0, 0, 0, 0))
subset_0.add_point((1, 3, 4, 1, 1))
subset_0.add_point((2, 3, 4, 0, 6))

# Check the current subset size
print("Subset size:", subset_0.size)

# See how many directions have been determined
print("Number of directions determined:", subset_0.number_of_directions_determined)

# Check line incidence
print("Max line incidence:", subset_0.max_line_incidence)

# Check for equidistributed planes
print("Number of equidistributed planes:", subset_0.number_equidistributed_planes)

# Remove a point
subset_0.remove_point((1, 3, 4, 1, 1))
```

---

## Notes

- Removing a point with `remove_point` also updates all statistics.
- This class is designed for small primes and low dimensions.
