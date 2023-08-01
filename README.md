# Neural Network Activation Function Analysis

This repository presents an analysis of various activation functions in the context of Multi Layer Perceptrons (MLPs), trained on the MNIST dataset of handwritten digits. It provides a study of the behavior of these functions regarding their gradients, and their impact on the learning process and model performance.

# Notation

In a neural network with $(R)$ layers and a set of $\mu$ patterns, the output of node $i$ in the $(r)$-th hidden layer is denoted as $y^{(r)}\_{i\mu}$. This output is calculated by taking the sum of the products of the weights connecting the previous layer nodes to the current node, with the output of the previous layer nodes denoted as $v^{(r)}_{i\mu}=\sum w^{(r)}_{ij}y^{(r-1)}_{j\mu}$ The result of this sum is passed as an argument into an activation function $f$. Thus the output of node $i$ in layer $r$ for pattern $\mu$ is: $y^{(r)}_{i\mu}=f(v^{(r)}_{i\mu})$ $w^{(r)}_{ij}$ denotes the weight connecting node $j$ in layer $(r-1)$ to node $(i)$ in layer $(r)$, the bias has been incorporated into the weights vector.

# Overview

The following tasks have been performed in the included notebook:

- **Task A:** The backpropagation equations have been rewritten for specific activation functions: ReLU, hyperbolic tangent, and sigmoid. The range of gradients for each activation function has also been provided. Below we present the visualization of the activation functions and their gradients.

<p align="center">
  <b>ReLU:</b>
</p>

$f(v^{(r)}_{i\mu}) = \begin{cases} 0 & \text{if } v^{(r)}_{i\mu} < 0 \\ v^{(r)}_{i\mu} & \text{if } v^{(r)}_{i\mu} > 0 \end{cases}$

<p align="center">
  <img src="./outputs/relu.png" alt="Alternate text for image"/>
</p>

<p align="center">
  <b>Tanh:</b>
</p>

$
f(v^{(r)}_{i\mu})=\frac{e^{v^{(r)}_{i\mu}} -e^{-v^{(r)}_{i\mu}}}{e^{v^{(r)}_{i\mu}}+e^{-v^{(r)}_{i\mu}}}
$

<p align="center">
  <img src="./outputs/tanh.png" alt="Alternate text for image"/>
</p>

<p align="center">
  <b>Sigmoid:</b>
</p>

$
f(v^{(r)}_{i\mu}) = \frac{1}{1 + e^{-v^{(r)}_{i\mu}}},
$

<p align="center">
  <img src="./outputs/sigmoid.png" alt="Alternate text for image"/>
</p>

---

- **Task B:** The MNIST dataset was used to train a fully-connected neural network to recognize handwritten digits. A comparison study was carried out by varying the number of layers (5, 20, and 40) and activation functions (ReLU, hyperbolic tangent, sigmoid) used in the model.The corresponding test scores for each model were reported, along with insightful observations. Again below we showcase the visualization of the test accuracy scores per epoch for all activation functions and layer depths, to illustrate the vanishing gradient problem.

<p align="center">
<b>Shallow network:</b>
</p>

<p align="center">
  <img src="./outputs/shallowNN.png" alt=""/>
</p>

<p align="center">
  <b>Medium depth Network:</b>
</p>

<p align="center">
  <img src="./outputs/mediumNN.png" alt=""/>
</p>

<p align="center">
  <b>Deep Network:</b>
</p>

<p align="center">
  <img src="./outputs/deepNN.png" alt=""/>
</p>

- **Task C:** For each model trained in Task B, the maximum gradient value for each layer was calculated for a given mini-batch. A plot showcasing the correlation between layer depth and maximum gradient was created, offering visualization and analysis of the results.

<p align="center">
  <b>layer depth vs maximum gradient:</b>
</p>

<p align="center">
  <img src="./outputs/MNISTgradient.png" alt=""/>
</p>

- **Task D:** A model was trained using the given the architecture from Task B, but with the LeCun activation function. An analysis was performed between the learning curves of models using the LeCun and hyperbolic tangent activation functions. Further, the backpropagation equations and the gradient range for the LeCun activation function were derived. Finally, the gradients for different depth choices were plotted for an untrained model using LeCun and hyperbolic tangent activations.

<p align="center">
  <b>LeCun activation vs tanh:</b>
</p>

<p align="center">
  <img src="./outputs/LeCunvsTanh.png" alt=""/>
</p>
