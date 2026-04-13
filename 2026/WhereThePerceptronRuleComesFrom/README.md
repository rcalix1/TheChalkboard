# From Error to Update: Where the Perceptron Rule Comes From

## The Chalkboard

**Derivations and challenges behind modern AI.**

![Perceptron Chalkboard](perceptronGrad.png)

Contact: rcalix@rcalix.com

---

# Problem

Early neural networks did not start with backpropagation.

They started with a simple question:

👉 **How should weights change when a prediction is wrong?**

The Perceptron update rule answers this:

$$
w_i \leftarrow w_i + \eta (y - \hat{y}) x_i
$$

But where does this rule come from?

Is it just heuristic… or is it grounded in calculus?

---

# Starting Point

Assume a simple linear model:

$$
\hat{y} = w_1 x_1 + w_2 x_2 + b
$$

Define the prediction error:

$$
e = y - \hat{y}
$$

---

# Key Idea

We want to **adjust the weights to reduce error**.

This leads to the central question:

$$
\text{How does the error change as we change each weight?}
$$

In other words:

$$
\frac{\partial e}{\partial w_i}
$$

---

# The Challenge

Derive the Perceptron update rule using calculus.

1. Start with the error:

$$
e = y - (w_1 x_1 + w_2 x_2 + b)
$$

2. Compute the partial derivatives:

$$
\frac{\partial e}{\partial w_1} = -x_1
\qquad
\frac{\partial e}{\partial w_2} = -x_2
$$

3. Apply a gradient-based update:

$$
w_i \leftarrow w_i - \eta \frac{\partial e}{\partial w_i}
$$

4. Substitute the derivatives

---

# The Result

You should obtain:

$$
w_1 \leftarrow w_1 + \eta (y - \hat{y}) x_1
$$

$$
w_2 \leftarrow w_2 + \eta (y - \hat{y}) x_2
$$

$$
b \leftarrow b + \eta (y - \hat{y})
$$

---

# Interpretation

The update has a simple but powerful meaning:

* If the prediction is **too low** → increase weights in direction of input
* If the prediction is **too high** → decrease weights
* Inputs act as **directional signals** for correction

---

# Visual Intuition

Instead of projection (like least squares), learning here is **iterative movement**:

```
Initial w  --->  better w  --->  better w  --->  ...
        (reduce error step by step)
```

Each update is a **small step in parameter space guided by the gradient**.

---

# Why This Matters in AI

This simple rule is the ancestor of:

* Gradient Descent
* Backpropagation
* Deep Neural Networks

The same idea scales to:

$$
w \leftarrow w - \eta \nabla_w L
$$

What changes is not the principle—but the **complexity of the model**.

---

# The Big Insight

Unlike the least-squares solution:

$$
(X^T X)^{-1} X^T Y
$$

which gives a **direct answer**,

the Perceptron introduces:

👉 **learning as a process**

---

# Philosophy

**Learning = moving weights in the direction that reduces error.**

---

# Tags

* Neural Networks
* Gradient Descent
* Perceptron
* Optimization
* Machine Learning Foundations

---

*Part of* **The Chalkboard** — a collection of derivations and reasoning challenges behind modern AI.
