# Day 1

## Numpy Tutorial 

Install the package using pip
```
pip install numpy
```
To check the version of a specific library using the command line interface (CLI), you can use the following command:


```
pip freeze | grep <package-name>
```

## NumPy Features

NumPy provides a fast and space-efficient **ndarray** (n-dimensional array) that supports vectorized arithmetic operations and sophisticated broadcasting capabilities.

### Key Features:
- **Standard mathematical functions** for fast operations on entire arrays of data without writing loops.
- **Tools** for reading/writing array data to disk and working with memory-mapped files.
- **Linear algebra**, **random number generation**, and **Fourier transform** capabilities.
- **Integration** with code written in C, C++, and Fortran.

### NumPy Functions

#### 1. `array`
Converts input data (list, tuple, array, or other sequence types) to an ndarray, either by inferring a dtype or explicitly specifying one. It copies the input data by default.

#### 2. `asarray`
Converts input to an ndarray but does not copy if the input is already an ndarray.

#### 3. `arange`
Similar to Python’s built-in `range` function but returns an ndarray instead of a list.

#### 4. `ones`, `ones_like`
Produces an array of all 1’s with a given shape and dtype. `ones_like` takes another array and produces a ones array of the same shape and dtype.

#### 5. `zeros`, `zeros_like`
Like `ones` and `ones_like`, but produces arrays of 0’s instead.

#### 6. `empty`, `empty_like`
Creates new arrays by allocating memory but does not populate them with values like `ones` and `zeros`.

#### 7. `eye`, `identity`
Creates a square N x N identity matrix (1’s on the diagonal and 0’s elsewhere).

## Data Types in NumPy

### Common Data Types:
| Type            | Type Code | Description                                               |
|-----------------|-----------|-----------------------------------------------------------|
| `int8`, `uint8` | `i1`, `u1`| Signed and unsigned 8-bit integer types                   |
| `int16`, `uint16`| `i2`, `u2`| Signed and unsigned 16-bit integer types                  |
| `int32`, `uint32`| `i4`, `u4`| Signed and unsigned 32-bit integer types                  |
| `int64`, `uint64`| `i8`, `u8`| Signed and unsigned 64-bit integer types                  |
| `float16`       | `f2`      | Half-precision floating point                             |
| `float32`       | `f4`, `f` | Standard single-precision floating point (C float)        |
| `float64`, `float128`| `f8`, `d`| Standard double-precision floating point (C double, Python float)|
| `float128`      | `f16`, `g`| Extended-precision floating point                         |
| `complex64`, `complex128`, `complex256`| `c8`, `c16`, `c32`| Complex numbers represented by two 32, 64, or 128 floats respectively |
| `bool`          | `?`       | Boolean type storing True and False values                |
| `object`        | `O`       | Python object type                                         |
| `string_`       | `S`       | Fixed-length string type (1 byte per character)           |
| `unicode_`      | `U`       | Fixed-length Unicode type                                 |

## Unary Universal Functions (ufuncs)

### Common Unary Functions:
| Function      | Description                                                     |
|---------------|-----------------------------------------------------------------|
| `abs`, `fabs`  | Compute the absolute value element-wise for integer, floating-point, or complex values. |
| `sqrt`         | Compute the square root of each element. Equivalent to `arr ** 0.5` |
| `square`       | Compute the square of each element. Equivalent to `arr ** 2`     |
| `exp`          | Compute the exponent `e^x` of each element                        |
| `log`, `log10`, `log2`, `log1p` | Natural logarithm (base e), log base 10, log base 2, and `log(1 + x)` respectively |
| `sign`         | Compute the sign of each element: 1 (positive), 0 (zero), or -1 (negative) |
| `ceil`         | Compute the ceiling of each element, i.e., the smallest integer greater than or equal to each element |
| `floor`        | Compute the floor of each element, i.e., the largest integer less than or equal to each element |
| `rint`         | Round elements to the nearest integer, preserving the dtype     |
| `modf`         | Return fractional and integral parts of an array as separate arrays |
| `isnan`        | Return a boolean array indicating whether each value is NaN (Not a Number) |
| `isfinite`, `isinf` | Return a boolean array indicating whether each element is finite (non-inf, non-NaN) or infinite, respectively |
| `cos`, `cosh`, `sin`, `sinh`, `tan`, `tanh` | Regular and hyperbolic trigonometric functions |
| `arccos`, `arccosh`, `arcsin`, `arcsinh`, `arctan`, `arctanh` | Inverse trigonometric functions |
| `logical_not`  | Compute truth value of not `x` element-wise. Equivalent to `-arr`. |

## Binary Universal Functions

### Common Binary Functions:
| Function      | Description                                                     |
|---------------|-----------------------------------------------------------------|
| `add`          | Add corresponding elements in arrays                            |
| `subtract`     | Subtract elements in the second array from the first array     |
| `multiply`     | Multiply array elements                                         |
| `divide`, `floor_divide` | Divide or floor divide (truncating the remainder)       |
| `power`        | Raise elements in the first array to powers indicated in the second array |
| `maximum`, `fmax` | Element-wise maximum (fmax ignores NaN)                      |
| `minimum`, `fmin` | Element-wise minimum (fmin ignores NaN)                      |
| `mod`          | Element-wise modulus (remainder of division)                   |
| `copysign`     | Copy the sign of values in the second argument to values in the first argument |
| `greater`, `greater_equal`, `less`, `less_equal`, `equal`, `not_equal` | Perform element-wise comparison, yielding boolean array |
| `logical_and`, `logical_or`, `logical_xor` | Compute element-wise truth value of logical operations |

## Basic Array Statistical Methods

| Method        | Description                                                      |
|---------------|------------------------------------------------------------------|
| `sum`         | Sum of all the elements in the array or along an axis. Zero-length arrays have sum 0. |
| `mean`        | Arithmetic mean. Zero-length arrays have NaN mean.              |
| `std`, `var`  | Standard deviation and variance, respectively, with optional degrees of freedom adjustment. |
| `min`, `max`  | Minimum and maximum values in the array                          |
| `argmin`, `argmax` | Indices of minimum and maximum elements, respectively        |
| `cumsum`      | Cumulative sum of elements starting from 0                       |
| `cumprod`     | Cumulative product of elements starting from 1                  |

## Array Set Operations

| Method        | Description                                                      |
|---------------|------------------------------------------------------------------|
| `unique(x)`   | Compute the sorted, unique elements in `x`                       |
| `intersect1d(x, y)` | Compute the sorted, common elements in `x` and `y`         |
| `union1d(x, y)` | Compute the sorted union of elements in `x` and `y`            |
| `in1d(x, y)`  | Compute a boolean array indicating whether each element of `x` is contained in `y` |
| `setdiff1d(x, y)` | Set difference, elements in `x` that are not in `y`          |
| `setxor1d(x, y)` | Set symmetric differences; elements that are in either of the arrays, but not both |

## Commonly-Used `numpy.linalg` Functions

| Function      | Description                                                      |
|---------------|------------------------------------------------------------------|
| `diag`        | Return the diagonal (or off-diagonal) elements of a square matrix as a 1D array, or convert a 1D array into a square matrix with zeros on the off-diagonal |
| `dot`         | Matrix multiplication                                             |
| `trace`       | Compute the sum of the diagonal elements                         |
| `det`         | Compute the matrix determinant                                     |
| `eig`         | Compute the eigenvalues and eigenvectors of a square matrix      |
| `inv`         | Compute the inverse of a square matrix                           |
| `pinv`        | Compute the Moore-Penrose pseudo-inverse of a square matrix      |
| `qr`          | Compute the QR decomposition                                      |
| `svd`         | Compute the singular value decomposition (SVD)                    |
| `solve`       | Solve the linear system `Ax = b` for `x`, where `A` is a square matrix |
| `lstsq`       | Compute the least-squares solution to `y = Xb`                    |

## `numpy.random` Functions

| Function      | Description                                                      |
|---------------|------------------------------------------------------------------|
| `seed`        | Seed the random number generator                                 |
| `permutation` | Return a random permutation of a sequence                         |
| `shuffle`     | Randomly permute a sequence in place                             |
| `rand`        | Draw samples from a uniform distribution                          |
| `randint`     | Draw random integers from a given low-to-high range              |
| `randn`       | Draw samples from a normal distribution (mean 0, standard deviation 1) |
| `binomial`    | Draw samples from a binomial distribution                         |
| `normal`      | Draw samples from a normal (Gaussian) distribution                |
| `beta`        | Draw samples from a beta distribution                             |
| `chisquare`   | Draw samples from a chi-square distribution                      |
| `gamma`       | Draw samples from a gamma distribution                            |
| `uniform`     | Draw samples from a uniform [0, 1) distribution                  |
