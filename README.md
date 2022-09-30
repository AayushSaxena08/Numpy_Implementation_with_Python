# **Numpy Implementation with Python**

*Reference: https://numpy.org/*

NumPy is the fundamental package for scientific computing in Python. It is a Python library that provides a multidimensional array object, various derived objects (such as masked arrays and matrices)

<a class="anchor" id="0.1"></a>
## TOC

1. **[Introduction to NumPy](#1)**
2. **[Indexing, Slicing and Iterating](#2)**
3. **[](#3)**
4. **[](#4)**
5. **[](#5)**
6. **[](#6)**
7. **[](#7)**

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

