---
tags: [machine-learning, programming, tensorflow]
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



# References
https://colab.research.google.com/drive/1F_EWVKa8rbMXi3_fG0w7AtcscFq7Hi7B#forceEdit=true&sandboxMode=true
https://youtu.be/r9hRyGGjOgQ?si=y6edtZDHPxHaBm36
