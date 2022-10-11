# **Numpy Implementation with Python**

*Reference: https://numpy.org/*

NumPy is the fundamental package for scientific computing in Python. It is a Python library that provides a multidimensional array object, various derived objects (such as masked arrays and matrices)

<a class="anchor" id="0.1"></a>
## TOC

1. **[Introduction to NumPy](#1)**
2. **[Indexing, Slicing and Iterating](#2)**
3. **[Joining NumPy Arrays](#3)**
4. **[Statistical Functions](#4)**
5. **[Matrix Functions](#5)**
6. **[Linear Algebra Functions](#6)**
7. **[Data Distribution](#7)**
8. **[](#8)**
9. **[](#9)**
10. **[](#10)**
11. **[](#11)**

## **1. Introduction to NumPy** <a class="anchor" id="1"></a>
[Table of Contents](#0.1)

NumPy is the fundamental package for scientific computing in Python. It is a Python library that provides a multidimensional array object, various derived objects (such as masked arrays and matrices), and an assortment of routines for fast operations on arrays, including mathematical, logical, shape manipulation, sorting, selecting, I/O, discrete Fourier transforms, basic linear algebra, basic statistical operations, random simulation and much more.
- At the core of the NumPy package, is the `ndarray` object

This repository explains the basics of NumPy such as its architecture and environment. It also discusses the various array functions, types of indexing, etc. 

### **Why is NumPy Fast?**

- NumPy arrays are stored at one continuous place in memory unlike lists, so processes can access and manipulate them very efficiently.
- In Python we have lists that serve the purpose of arrays, but they are slow to process.
- NumPy aims to provide an array object that is up to 50x faster than traditional Python lists.
- The array object in NumPy is called ndarray, it provides a lot of supporting functions that make working with ndarray very easy. Arrays are very frequently used in data science, where speed and resources are very important.

      >>> import numpy as np
      >>> a = np.arange(15).reshape(3, 5)
      >>> a
      array([[ 0, 1, 2, 3, 4],
           [ 5, 6, 7, 8, 9],
           [10, 11, 12, 13, 14]])
      >>> a.shape
      (3, 5)
      >>> a.ndim
      2
      >>> a.dtype.name
      'int64'
      >>> a.itemsize
      8
      >>> a.size
      15

## **2. Indexing, Slicing and Iterating**<a class="anchor" id="2"></a>
[Table of Contents](#0.1)

One-dimensional arrays can be indexed, sliced and iterated over, much like lists and other Python sequences.
- Array indexing is the same as accessing an array element.
- The indexes in NumPy arrays start with 0, meaning that the first element has index 0, and the second has index 1 etc.
- Slicing in python means taking elements from one given index to another given index. We pass slice instead of index like this: `[ start : end ]`
- Iterating means going through elements one by one. As we deal with multi-dimensional arrays in numpy, we can do this using basic `for` loop of python.

      >>> a = np.arange(10)**3
      >>> a
      array([ 0, 1, 8, 27, 64, 125, 216, 343, 512, 729])
      >>> a[2]
      8
      >>> a[2:5]
      array([ 8, 27, 64])

## **2. Joining NumPy Arrays**<a class="anchor" id="3"></a>
[Table of Contents](#0.1)

Joining means putting contents of two or more arrays in a single array. 
- In SQL we join tables based on a key, whereas in NumPy we join arrays by axes.
- We pass a sequence of arrays that we want to join to the `concatenate()` function, along with the axis. If axis is not explicitly passed, it is taken as 0.

      >>> arr1 = np.array([[1, 2], [3, 4]])
      >>> arr2 = np.array([[5, 6], [7, 8]])
      >>> arr = np.concatenate((arr1, arr2), axis=1)
      >>> print(arr)
      
      [[1 2 5 6]
       [3 4 7 8]]
       
## **4. Statistical Functions**<a class="anchor" id="4"></a>
[Table of Contents](#0.1)

NumPy has quite a few useful statistical functions for finding minimum, maximum, percentile standard deviation and variance, etc. from the given elements in the array.

- `numpy.amin()` and `numpy.amax()` - These functions return the minimum and the maximum from the elements in the given array along the specified axis.
- `numpy.ptp()` - The numpy.ptp() function returns the range (maximum-minimum) of values along an axis.
- `numpy.percentile()` - Percentile (or a centile) is a measure used in statistics indicating the value below which a given percentage of observations in a group of observations fall.
- `numpy.mean()` - The numpy.mean() function returns the arithmetic mean of elements in the array.
- `numpy.average()` - The numpy.average() function computes the weighted average of elements in an array according to their respective weight given in another array. The function can have an axis parameter.
- Standard Deviation - Standard deviation is the square root of the average of squared deviations from mean. The formula for standard deviation is as follows −

      std = sqrt(mean(abs(x - x.mean())**2))

- Variance - Variance is the average of squared deviations, i.e., mean(abs(x - x.mean())**{2}). In other words, the standard deviation is the square root of variance.

## **5. Matrix Functions** <a class="anchor" id="5"></a>
[Table of Contents](#0.1)

NumPy package contains a Matrix library numpy.matlib.

- `numpy.matlib.zeros()`: This function returns the matrix filled with zeros.

      >>> import numpy as np 
      >>> print np.matlib.ones((2,2))
      [[ 0.  0.] 
       [ 0.  0.]] 
   
- `numpy.matlib.ones()`: This function returns the matrix filled with 1s.
- `numpy.matlib.eye()`: This function returns a matrix with 1 along the diagonal elements and the zeros elsewhere.

      numpy.matlib.eye(n, M,k, dtype)
      
## **6. Linear Algebra Functions**<a class="anchor" id="6"></a>
[Table of Contents](#0.1)

NumPy package contains numpy.linalg module that provides all the functionality required for linear algebra.

- `numpy.dot()` : This function returns the dot product of two arrays. For N-dimensional arrays, it is a sum product over the **last axis of a** and the **second-last axis of b.**

      >>> import numpy as np 
      >>> a = np.array([[1,2],[3,4]]) 
      >>> b = np.array([[11,12],[13,14]]) 
      >>> np.dot(a,b)
      [[37  40] 
       [85  92]]
       
- `numpy.matmul()` : The **numpy.matmul()** function returns the matrix product of two arrays.
- `numpy.linalg.det()` : The **numpy.linalg.det()** function calculates the determinant of the input matrix.

## **6. Data Distribution**<a class="anchor" id="7"></a>
[Table of Contents](#0.1)

- **Normal Distribution:** Generate a random normal distribution of size 2x3 with mean at 1 and standard deviation of 2

      x = random.normal(loc=1, scale=2, size=(2, 3))
      print(x)
      
      # loc - (Mean) where the peak of the bell exists.
      # scale - (Standard Deviation) how flat the graph distribution should be.
      # size - The shape of the returned array.

![image](https://user-images.githubusercontent.com/35486320/195160090-203e84d4-7024-4a2b-9f57-f91332676f5a.png)

- **Binomial Distribution:** It describes the outcome of binary scenarios, e.g. toss of a coin, it will either be head or tails.

      x = random.binomial(n=10, p=0.5, size=10)
      print(x)

      # n - number of trials.
      # p - probability of occurence of each trial (e.g. for toss of a coin 0.5 each).
      # size - The shape of the returned array.

![image](https://user-images.githubusercontent.com/35486320/195160677-b9e2f5ff-13f2-421c-a4c3-9f098de422c7.png)

- **Poisson Distribution:** Poisson Distribution is a Discrete Distribution. It estimates how many times an event can happen in a specified time. e.g. If someone eats twice a day what is probability he will eat thrice?

      x = random.poisson(lam=2, size=10)
      print(x)

      # lam - rate or known number of occurences e.g. 2 for above problem.
      # size - The shape of the returned array.

- **Uniform Distribution:** Used to describe probability where every event has equal chances of occuring.

      x = random.uniform(size=(2, 3))
      print(x)

      # a - lower bound - default 0 .0.
      # b - upper bound - default 1.0.
      # size - The shape of the returned array.

![image](https://user-images.githubusercontent.com/35486320/195161345-43aa0097-1d68-498a-b418-4f3c5decee36.png)

- **Rayleigh Distribution:** 

      x = random.rayleigh(scale=2, size=(2, 3))
      print(x)

      # scale - (standard deviation) decides how flat the distribution will be default 1.0).
      # size - The shape of the returned array.

![image](https://user-images.githubusercontent.com/35486320/195161623-59f33102-1b09-400d-88e3-5fb14ab9a595.png)

This repository is still in progress. 

# Thank you for reading this repo. Connect with me on <a href="https://www.linkedin.com/in/aayushsaxena08/">LinkedIn</a>⭐
