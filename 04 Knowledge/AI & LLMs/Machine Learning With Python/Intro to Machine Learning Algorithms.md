---
tags: [ai, dsa, machine-learning, python]
---

2025-11-20 00:53

Status: #Teen 

Tags: [[Machine Learning]] [[6 - Main Notes/Machine Learning With Python/Intro to TensorFlow|Intro to TensorFlow]] [[Tensorflow]]

# Intro to Machine Learning Algorithms

There exists different types of core algorithms, here we will talk about five of them. 
So, What is an Algorithm? 
An Algorithm is a set of instructions a loop(recipe) that every ingredient (milk, flour, eggs) go through before becoming a meaningful output (cake).
We make algorithms to make our problems automated so if a similar problem arises we just enter input and get the output take an example of a for loop for printing table of a number 

`for (int i = 1; i<11; i++)`
`{`
`System.out.println(i*num);`
`}`

This is a simple algorithm that prints the table of a number.
There exists many algorithms used in Machine Learning:

#### 1. Linear Regression

**"The Line of Best Fit"**

~What is it?: It is used to find a relationship between two numbers and draws an imaginary straight line between them. It is used when you need to find a numerical value.

~The Math: The Algorithm makes a line $y = mx + b$ where:
 1. $y$ is the number you are trying to find.
 2. $x$ is the data you have.
 3. $m$ is the slope how much the value changes per change.
 4. The algorithms job is to find the best $m$ and $b$ so that the line made touches as many points as possible

**Real-World Use:**

- Predicting life expectancy based on BMI.
    
- Predicting stock prices based on yesterday's trends.

#### 2. Classification

**"The Labeler"**

~What is it?: It is used when the thing you are trying to find isn't a value but a category. It decides whether something belongs in category A or B.
- **How it works:** Imagine a graph with red dots (Spam emails) and blue dots (Real emails). Classification draws a curvy line to separate the red zone from the blue zone. If a new email lands in the red zone, it gets labeled "Spam."
    
- **The Math:** It often uses a function (like the "Sigmoid" function) that squishes any number into a probability between 0 and 1. If the probability is > 0.5, it's a "Yes"; otherwise, it's a "No."

**Real-World Use:**

- Detecting if a tumor is benign or malignant.
    
- Classifying a flower species based on petal size (The Iris dataset used in the video).

#### 3. Clustering

**"The Grouper"**

- **What it is:** This is **Unsupervised Learning**, meaning we don't give the computer the answers. We just give it a pile of messy data and say, "Find the patterns."
    
- **How it works (K-Means):**
    
    1. The algorithm randomly picks "Centroids" (center points).
        
    2. It grabs all the data points nearest to that center and forms a group.
        
    3. It moves the center to the middle of that new group.
        
    4. It repeats this until the groups are perfectly separated.
        
- **Real-World Use:**
    
    - **Netflix:** "Users who liked _Inception_ also liked _Interstellar_." It clusters viewers into groups with similar tastes.
        
    - **T-Shirt Sizing:** A clothing company measures 1,000 people and finds 3 natural "clusters" of body shapes to define Small, Medium, and Large sizes.

#### 4. Hidden Markov Models (HMM)

**"The Sequence Predictor"**

- **What it is:** This is different from the others. It doesn't look at a static picture; it looks at **sequences over time**. It assumes that the future depends on the present.
    
- **Key Concept:** It uses **States** (hidden situations) and **Observations** (what we see).
    
    - _Example:_ You can't see if your friend is happy or sad (Hidden State), but you can see if they are whistling or crying (Observation). HMM uses the observation to guess the state.
        
- **Real-World Use:**
    
    - **Speech Recognition:** Predicting that the sound "Hel-" will likely be followed by "-lo".
        
    - **Weather:** Predicting tomorrow's weather based on today's weather, not just average historical data.




# References

https://colab.research.google.com/drive/15Cyy2H7nT40sGR7TBN5wBvgTd57mVKay#forceEdit=true&sandboxMode=true