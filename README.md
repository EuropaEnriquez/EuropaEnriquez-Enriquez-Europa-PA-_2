**PROBLEM 1: NORMALIZATION**
Normalization is one of the most basic preprocessing techniques in data analytics. This involves centering and scaling process. Centering means subtracting the data from the mean and scaling means dividing with its standard deviation. Here is the code for this problem.
```
import numpy as np

X = np.random.random((5, 5))  
X

mean = X.mean()
mean
print("Mean of X:", mean)

std = X.std()
std
print("Standard Deviation of X:", std)

X_normalized = (X - mean) / std
X_normalized
print("\nNormalized Array:\n", X_normalized)

np.save('X_normalized.npy', X_normalized)

loaded = np.load("X_normalized.npy")
```

The code begins by importing the NumPy library and generating a random 5×5 array of floating-point numbers between 0 and 1 using ```np.random.random((5, 5))```. This array is stored in the variable X and represents the dataset to be normalized. 
```
import numpy as np
X = np.random.random((5, 5))  
X
```

The mean of the array is calculated with the X.mean() and stored in the variable mean. The standard deviation is computed with ```X.std()``` and stored in std. These two values will now be used for normalization.
```
mean = X.mean()
mean
print("Mean of X:", mean)

std = X.std()
std
print("Standard Deviation of X:", std)
```

Next, we will obtain the Normalized Data using the formula ```(X - mean) / std```, which subtracts the mean from each element and divides the result by the standard deviation. This produces a new array named ```X_normalized``` where values are centered around zero and measured in units of standard deviation. 
```
X_normalized = (X - mean) / std
X_normalized
print("\nNormalized Array:\n", X_normalized)
```

For the last step, the code saves this normalized array as a  file ```X_normalized.npy``` using ```np.save()```, and then reloads it with ```np.load()``` to ensure that the file was saved correctly.
```
np.save('X_normalized.npy', X_normalized)
loaded = np.load("X_normalized.npy")
```

**This process demonstrates one of the most common preprocessing techniques in data analytics, ensuring that the dataset has comparable values regardless of the original scale.**

________________________________________________________________________________________________________________________
**PROBLEM 2: DIVBISIBLE BY 3**
This problem asks to create a 10 x 10 ndarray, Which are the squares of the first 100 positive integers. Here is the code used for this problem:
```
numbers = np.arange(1, 101)
numbers
Arranged_Set = numbers.reshape(10,10)
print("10x10 Array of first 100 Integers:\n", Arranged_Set)

squares = numbers ** 2
squares
A = squares.reshape(10, 10)
print("10x10 Array of firstSquares:\n", A)

div_by_3 = A[A % 3 == 0]
print("\nNumbers divisible by 3:\n", div_by_3)

np.save('div_by_3.npy', div_by_3)
loaded = np.load("div_by_3.npy")
```
The code starts by generating a sequence of numbers from 1 to 100 using ```np.arange(1, 101)```. This sequence is then turned into a 10×10 array for clear display, stored in the variable ```Arranged_Set```.

```
numbers = np.arange(1, 101)
numbers
Arranged_Set = numbers.reshape(10,10)
print("10x10 Array of first 100 Integers:\n", Arranged_Set)
```

Next, each number in the sequence is squared using the expression ```numbers ** 2```, producing the first 100 perfect squares. These squared values are then turned or reshaped into another 10×10 array called ```A```.

```
squares = numbers ** 2
squares
A = squares.reshape(10, 10)
print("10x10 Array of Squares:\n", A)
```

To determine which squared values are divisible by 3, the code used the condition ```A % 3 == 0```, where this condition is also applied from C++. This condition checks every element of the array and keeps only those that are divisible by 3. 

```
div_by_3 = A[A % 3 == 0]
print("\nNumbers divisible by 3:\n", div_by_3)
```
For the last step, the resulting array of numbers divisible by 3 can be saved as a file ```div_by_3.npy``` using ```np.save()``` and ```np.load()```. to ensure that the file was saved correctly, like Problem 1.

```
np.save('div_by_3.npy', div_by_3)
loaded = np.load("div_by_3.npy")
```

**This problem demonstrates how NumPy can efficiently generate sequences, reshape arrays, perform element-wise operations like squaring, and filter results using conditions, making it a powerful tool for numerical analysis.**
