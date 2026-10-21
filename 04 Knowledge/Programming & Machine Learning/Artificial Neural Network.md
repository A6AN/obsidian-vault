---
tags: [deep-learning, machine-learning, programming]
---

2024-12-06 17:14

Status: #baby 

Tags: [[AI]] [[Research]] [[Machine Learning]] [[ANN]]

# ANN

Why Neural Network?

`• OFFER AN ALTERNATIVE APPROACH TO COMPUTING AND TO UNDERSTANDING OF THE HUMAN BRAIN
`- ﻿﻿NEURAL NETWORKS TAKE A DIFFERENT APPROACH TO PROBLEM SOLVING THAN THAT OF CONVENTIONAL COMPUTERS
`- ﻿﻿NEURAL NETWORKS PROCESS INFORMATION IN A SIMILAR WAY THE HUMAN BRAIN DOES.
`• THE BUILDING BLOCK OF A NEURAL NET IS THE NEURON.
`AN ARTIFICIAL NEURON WORKS MUCH THE SAME WAY THE BIOLOGICAL ONE DOES.

Never use ANN or CNN on small datasets. 
ANN mimics a human brain it creates small neurons which are used to solve problems.

if you dont make a proper connection with all the hidden connections the output may vary a lot

##### Activation Function :- 
- The activation function f(∑wixi + b) is a mathematical operation applied to the weighted sum of inputs plus a bias term.
- It determines whether the neuron will "fire" (produce an output) based on the strength of the input signals.
- Common activation functions include sigmoid, tanh, ReLU (Rectified Linear Unit), which can introduce non-linearity and allow the neuron to learn complex patterns.
- The choice of activation function is important as it impacts the behavior and capabilities of the artificial neuron.

Layers:
- Input Layer: This is the layer that receives the initial inputs (xi) to the artificial neural network.
- Hidden Layer(s): These are the intermediate layers between the input and output layers, where the inputs are transformed through the weighted connections and activation functions.
- Output Layer: This is the final layer that produces the output of the artificial neural network, which in this case is the "output axon".![[Screenshot 2024-12-06 at 5.27.09 PM.png]]

This image presents a neural network model for a "Single OBS" (Observation) scenario. 

1. Standardized Input:
    - The input variables (X1, X2, ..., Xm) are all standardized, meaning they are transformed to have a common scale and distribution. This is an important preprocessing step to ensure the neural network can learn effectively.
2. Single Neuron:
    - The core of the model is a single neuron, which is the fundamental processing unit in a neural network.
    - The neuron receives the standardized input values (X1, X2, ..., Xm) and processes them to produce a single output value (y).
3. Hidden Layer:
    - The "Hidden Layer" can be multiple layers, and these layers are where the input data is transformed and processed to extract meaningful features.
    - The number of hidden layers and the specific architecture (e.g., the number of neurons in each layer) are important design choices that can impact the model's performance.
4. Output Value:
    - The output value (y) can be one of three types:
        1. Continuous: A numerical value.
        2. Binary (Y/N): A binary classification (yes/no).
        3. Categorical: A classification into one of multiple categories.
    - The type of output value depends on the specific problem being solved.
5. Single Observation:
    - This model is designed for a "Single OBS" scenario, where the neural network processes a single observation or data point at a time, as opposed to processing a batch or sequence of data.

In summary, this neural network model takes standardized input variables, processes them through a single neuron with a potentially complex hidden layer architecture. And produces a single output value of a specific type (continuous, binary, or categorical) based on the problem being solved.

#### Threshold Function:
The threshold function introduces non-linearity into the neural network, allowing it to learn and represent complex patterns in the data. Some common examples of threshold functions used in neural networks include:

1. Sigmoid function:
    - The sigmoid function maps the input to a value between 0 and 1, allowing the output to be interpreted as a probability.
    - The sigmoid function is given by the formula: 1 / (1 + e^(-x))
2. Tanh (Hyperbolic Tangent) function:
    - The tanh function maps the input to a value between -1 and 1.
    - The tanh function is given by the formula: (e^x - e^(-x)) / (e^x + e^(-x))
3. ReLU (Rectified Linear Unit) function:
    - The ReLU function outputs the input value if it is positive, and 0 if the input is negative.
    - The ReLU function is given by the formula: max(0, x)
4. Softmax function:
    - The softmax function is used for multi-class classification problems, as it converts the output values into a probability distribution over the classes.
    - The softmax function is given by the formula: e^(x_i) / Σ e^(x_j), where i is the current class and j is over all classes.

Gradient Descent is an optimization algorithm. Its goal is to find the best set of parameter (weights and biases) which can minimize the loss and cost function. 

The gradient descent algorithm can be summarized as follows:

1. Initialize the parameters (e.g., weights and biases) to some random values.
2. Compute the gradient of the loss function with respect to each parameter.
3. Update the parameters by subtracting a small fraction (learning rate) of the gradient from the current parameter values.
4. Repeat steps 2 and 3 until the loss function is minimized or a stopping criterion is met.

The formula for updating the parameters in gradient descent is:

θ_new = θ_old - α * ∂L/∂θ

Where:

- θ_new is the updated parameter value
- θ_old is the current parameter value
- α is the learning rate, which determines the step size of the update
- ∂L/∂θ is the gradient of the loss function with respect to the parameter θ

Gradient descent can be implemented in different variations, such as:

1. Batch gradient descent: The gradients are computed using the entire training dataset.
2. Stochastic gradient descent (SGD): The gradients are computed using a single training example at a time.
3. Mini-batch gradient descent: The gradients are computed using a small subset of the training dataset, called a mini-batch.
# References
