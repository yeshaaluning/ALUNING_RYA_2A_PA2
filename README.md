# ALUNING_RYA_2A_PA2
This repository includes Python programs that provide solutions to two (2) problems from Program Assignment 2: Numerical Python (NUMPY).

---
## 1. NORMALIZATION PROBLEM
**Problem:** Create a random 5 x 5 ndarray and store it to variable X. Normalize X <br>
**Code Process:**
1. The program begins by importing the NumPy library and referring to it as np.
2. A random 5×5 ndarray is generated using np.random.random() and stored in the variable X.
3. The program calculates the mean of all elements in X using .mean() and stores it in the variable m.
4. It then calculates the standard deviation of X using .std() and stores it in the variable sd.
5. Normalization is applied to X by subtracting the mean (m) and dividing by the standard deviation (sd). The result is stored in the variable z.
6. Finally, the normalized array z is saved into a file named X_normalized.npy using np.save().

```Python
#Declaring nump as 'np'
import numpy as np

#Making a random 5x5 ndrray and storing it to variable X.
X = np.random.random((5,5))
X

#To get the mean
m = X.mean()
m

#To get the sd
sd = X.std()
sd

#Normalization
z = X-m/sd
np.save('X_normalized.npy', z)
z
```
---
## 2. DIVISIBLE BY 3 PROBLEM
**Problem:**  Create the following 10 x 10 ndarray which are the squares of the first 100 positive integers. From this ndarray, determine all the elements that are divisible by 3. Save the result as div_by_3.npy  <br> 
**Code Process:**
1. The program imports the NumPy library and refers to it as np.
2. It creates an array of the first 100 positive integers using np.arange().
3. Each integer is squared to form the first 100 perfect squares.
4. The squared values are reshaped into a 10×10 ndarray and stored in the variable A.
5. The program then checks which elements in A are divisible by 3 and extracts them into a new array called div_by_3.
6. The extracted array is saved in a file named div_by_3.npy using np.save().
7. Finally, the program prints both the 10×10 matrix A and the extracted elements div_by_3.

```Python
#Declaring nump as 'np'
import numpy as np

#Creating an array of the first 100 positive integers
numbers = np.arange(1, 101)

#Square the numbers
squares = numbers ** 2

#Reshape into a 10 x 10 ndarray
A = squares.reshape(10, 10)

#Select all elements that are divisible by 3
div_by_3 = A[A % 3 == 0]

#Save the result into a .npy file
np.save("div_by_3.npy", div_by_3)

#Print
print("Matrix A (10x10 of squares):\n", A)
print("\nElements divisible by 3:\n", div_by_3)

