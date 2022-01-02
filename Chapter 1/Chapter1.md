# Chapter 1: The Machine Learning Landscape

## What is Machine Learning?

- Machine Learning is the field of study that gives computers the ability to learn without being explicitly programmed. (Arthur Samuel, 1959)
- A computer program is said to learn from experience E with respect to some task T and some performance measure P, if its performance on T, as measured by P, improves with experience E. (Tom Mitchell, 1997)

## Types of Machine Learning Systems

- Supervised (trained with human supervision)
- Unsupervised
- Semisupervised
- Reinforcement Learning

1. In *supervised learning*, the training data you feed to the algorithm includes the desired solutions, called *labels*.
   - **Supervised Machine Learning Algorithms:**
     - k-Nearest Neighbors
     - Linear Regression
     - Logistic Regression
     - Support Vector Machines (SVMs)
     - Decision Trees and Random Forests
     - Neural Networks (some can be unsupervised, such as autoencoders and restricted Boltzmann machines; some can be semisupervised, such as in deep belief networks and insupervised pretraining)

2. In *unsupervised learning*, the training data is unlabeled. The system tries to learn without a teacher.
   - **Unsupervised Machine Learning Algorithms:**
     - Clustering
       - k-Means
       - Hierarchical Cluster Analysis (HCA)
       - Expectation Maximization
     - Visualization and dimensionality reduction
       - Principal Component Analysis (PCA)
       - Kernel PCA
       - Locally-Linear Embedding (LLE)
       - t-distributed Stochastic Neighbor Embedding (t-SNE)
     - Association rule learning
       - Apriori
       - Eclat

3. In **semisupervised learning**, the training data can be partially labeled, usually a lot of unlabeled and a little labeled.
   - Most semisupervised learning algorithms are combinations of unsupervised and supervised algorithms. 
     - Deep belief networks (DBNs): based on unsupervised components called restricted Boltzmann machines (RBMs) stacked on top of one another. RBMs are trained sequentially in an unsupervised manner, and then the whole system is fine-tuned using supervised learning techniques.

4. **Reinforcemnet Learning** is very different from the others. The learning system, called an agent in this context, can observe the environment, select and perform actions, and get **rewards** in return (or **penalties** in the form of negative rewards). It must then learn by itself what is the best strategy, called a **policy**, to get the most reward over time. A policy defines what action the agent should choose when it is in a given situation.

## Batch and Online Learning

1. Batch learning:
   - the system is incapable of learning incrementally: it must be trained usingall the available data. This will generally take a lot of time and computing resources, so it is typically done offline. First the system is trained, and then it is launched into production and runs without learning anymore; it just applies what it has learned. This is called offline learning.

2. Online learning:
   - the system is trained incrementally by feeding it data instances sequentially, either individually or by small groups called -mini-batches. Each learning step is fast and cheap, so the system can learn about new data on the fly, as it arrives. Online learning is great for systems that recieve data as a continous flow and need to adapt to change rapidly or autonomously. Also a good choice if you have limited computing resources, once an online learning system has learned about new data instances, it does not need them anymore.
     - *Important parameter: Learning Rate*
       - A high learning rate will let the system rapidly adapt to new data, but it also forgets about old data quickly.
       - A low learning rate will let the systme learn more slowly and be less sensitive to noise from new data or to sequences of nonrepresentative data points. 

## Instance-Based Versus Model-Based Learning

1. **Instance-Based:** the system learns the examples by heart, then generalizes to new cases using a similarity measure.
2. **Model-Based:** generalize a model from a set of examples, then use that model to make *predictions*. 

### [Example 1.1](./example1_1.py)