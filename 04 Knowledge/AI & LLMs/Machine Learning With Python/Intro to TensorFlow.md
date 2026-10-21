---
tags: [ai, machine-learning, python, tensorflow]
---

2025-09-14 03:08

Status: #Teen 

Tags: [[Python]] [[Machine Learning]][[Tensorflow]]

# Intro to TensorFlow

What is a Tensor? 
It is a vector generalized to higher dimensions. 
what is a vector?
A data-point. It doesn't necessarily have a coordinate, it can have any amount of dimension in it. 1d- 1 coordinate
2d - 2 coordinate 2d plane
3d - 3 coordinate
4d -...
and so on 

Tensor are the main object that is passed around a program in TensorFlow. 
When we create a tensor, it represents a partially defined computation that will eventually produce a value. Tensorflow works by building a graph of Tensor objects that detail how tensors are related. Running different parts of the graph allow results to be generated.
When we create the program we create a bunch of tensors which store partial computation. When we run a program we run these graphs and different tensors will be executed and they will give different results. 

Each Tensor has a data type and a shape. 
Data Types include: Float32, int32, string and others
Shape is the dimension of the data.

### Creating a Tensor

`string = tf.Variable("this is a string", tf.string)`
`number = tf.Variable(324, tf.int16)`
`floating = tf.Variable(3.567, tf.float64)`

The first command creates a string type tensor which stores the value "This is a String". The name of this Tensor variable is string.
The second command creates a number type tensor which stores the value 324. The name of this string is number
The third command creates a number type tensor which stores the value  3.567. The name of this string is floating.

All of these tensor variables are 1 dimensional.

### Rank/Degrees of Tensor

when we create a tensor of rank 0 like the above tensors it is called scaler
when we create tensor of an 1d array we call it rank 1 tensor the code below shows a string array so its a rank 1 tensor.

`rank1_tensor = tf.Variable(["Test"], tf.string)`

when we create a tensor of 2d array we call it rank 2 tensor the code below shows a string 2d array so its a rank 2 tensor.

`rank2_tensor = tf.Variable([["test", "ok"], ["test", "yes"]], tf.string)`

We can determine the rank of a tensor by the following method:
`tf.rank(name of the tensor variable)`

Shape of a tensor tells us the number of items a tensor has in each dimension. To get the shape you can use the following method:
`tensor_variable_name.shape`

### Reshaping a Tensor

Reshaping a tensor means changing its structure (shape) while keeping all its elements. The total number of elements in the tensor must remain the same after reshaping. For example, a tensor with 8 elements and a shape of (2, 4) (a 2x4 matrix) can be reshaped into a (4, 2) matrix, a (1, 8) vector, or an (8, 1) vector.
the `tf.reshape()` method, is used to perform this operation. A particularly useful feature highlighted is the ability to use `-1` for one of the dimensions. When you specify `-1`, you are telling TensorFlow to automatically infer the size of that dimension based on the total number of elements in the tensor and the other specified dimensions. For instance, if you have a tensor with 12 elements and you reshape it to `(3, -1)`, TensorFlow will automatically calculate the second dimension to be 4, resulting in a shape of (3, 4).

### Types of Tensor
There are different types of tensors in TensorFlow, each with a specific purpose:

- **`Variable`**: These are mutable tensors, meaning their values can be changed during the execution of a TensorFlow program. Variables are typically used to hold the parameters of a model, such as the weights and biases in a neural network, which need to be updated during training.
    
- **`Constant`**: As the name suggests, these are immutable tensors. Once a constant tensor is created, its value cannot be changed. Constants are used for values that you know will not change during the execution of your program, such as hyperparameters or fixed input values.
    

There also exists **Placeholder** and **SparseTensor**. A placeholder is a tensor that is used to feed data into a TensorFlow graph. You can think of it as a variable that you promise to provide a value for later. A SparseTensor is a special type of tensor used to represent data that is mostly zero in an efficient way.

### Evaluating Tensor

In TensorFlow 1.x, the code you write defines a computational graph. This graph consists of tensors and the operations that connect them. However, simply defining the graph doesn't actually perform any computations or assign any values.

To evaluate a tensor, which means to compute its value, you need to run the computational graph within a **`tf.Session`**. The following pattern is for this:

`with tf.Session() as sess:`
    `result = tensor.eval()`

Here's what this code does:

1. `tf.Session()` creates a session object, which provides an environment for executing the operations in the graph.
    
2. The `with` statement ensures that the session is automatically closed after the block of code is executed.
    
3. `tensor.eval()` is a shortcut for `sess.run(tensor)`. This command tells TensorFlow to execute the part of the graph that is necessary to compute the value of the `tensor` and then returns that value.


# References
https://colab.research.google.com/drive/1F_EWVKa8rbMXi3_fG0w7AtcscFq7Hi7B#forceEdit=true&sandboxMode=true
https://youtu.be/r9hRyGGjOgQ?si=y6edtZDHPxHaBm36
