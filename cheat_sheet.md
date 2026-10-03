# Cheat Sheet

## NumPy basics
- Shape: `(3,)` is a flat line. `(1, 3)` is 1 row. `(3, 1)` is 1 column. Count the brackets.
- Create: `np.array`, `np.zeros((r, c))`, `np.ones`, `np.arange(0, 10, 2)`, `np.linspace(0, 1, 5)`, `np.eye(3)`
- Check: `x.shape`, `x.ndim`, `x.size`, `x.dtype`

## Reshape
- `x.reshape(3, 4)`: total items must stay the same
- `-1` means "numpy works it out": `x.reshape(-1, 1)` makes a column
- `.T` flips rows and columns

## Slicing
- `m[row, col]`, slice is `start:stop:step`, stop is NOT included
- A single number removes a direction. A slice keeps it.
- `m[0]` is the same as `m[0, :]`
- Want a column? `m[:, 0]`

## Axis
- `axis=0` goes down, one answer per column
- `axis=1` goes across, one answer per row
- The axis you use disappears from the shape. `keepdims=True` leaves a 1.

## Broadcasting
- Compare shapes from the right. Sizes must be equal or 1.
- `(3,)` does not match `(3, 4)`. Use `.reshape(3, 1)` to make a column.

## Matrix multiply
- `A @ B`: inner numbers must match, outer numbers give the result shape
- `A * B` is item-by-item, not matrix multiply