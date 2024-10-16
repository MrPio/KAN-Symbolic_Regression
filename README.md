# Symbolic regression in KANs

This repository contains the results of the tests carried out to prove the ability of the Kolmogorov-Arnold neural
network to solve symbolic regression tasks.

KANs were presented by Liu and colleagues in their work [KAN: Kolmogorov-Arnold Networks](https://arxiv.org/abs/2404.19756).


## 📘 The thesis:

### ▶️ [Approaching symbolic regression with Kolmogorov-Arnold networks [PDF]](https://github.com/user-attachments/files/17318281/Approaching.symbolic.regression.with.Kolmogorov-Arnold.networks.pdf)


## 📙 The slideshow presented on the day of the exam:

### ▶️ [Symbolic Regression with KANs [PDF]](https://github.com/user-attachments/files/17270435/Symbolic.Regression.with.KANs.pdf)

### ▶️ [Symbolic Regression with KANs [PPTX]](https://github.com/user-attachments/files/17270436/Symbolic.Regression.with.KANs.pptx)

## 📦 What does the repository offer?

### [Comparison of different methods for Symbolic Regression in an univariate task](Comparison_of_different_methods_for_SR_univariate.ipynb)

The same univariate symbolic regression task is solved using *KANs*, *Genetic Programming*, *Bayesian Method* and *QLattice*.

<p align="center">
<img src="img/comparison_univariate.png" alt="" width="900rem">
</p>

### [Comparison of different methods for Symbolic Regression in a multivariate task](Comparison_of_different_methods_for_SR_multivariate.ipynb)

The same multivariate symbolic regression task is solved using *KANs*, *Genetic Programming*, *Bayesian Method* and *QLattice*.

<p align="center">
<img src="img/comparison_multivariate.png" alt="" width="1200rem">
</p>

### [Pendulum motion experiment](Pendulum_Motion.ipynb)

I recorded my smartphone's gyroscope and accelerometer sensors while it was swaying with a 50cm twine.

The goal is to make KAN retrieve the symbolic formula of the harmonic motion despite the sensor noise.

<p align="center">
  <img src="img/gyroscope.png" alt="" width="600rem">
</p>
<p align="center">
  <img src="img/accelerometer.png" alt="" width="600rem">
</p>


### [Special function](Special_function.ipynb)

This test considers the sine integral special function:

$$Si(x) = \int_0^x \frac{\sin(t)}{t} dt$$

This function cannot be represented as a composition of common functions and is therefore a special function. Unlike
other symbolic regression algorithms, PyKAN is able to approximate it anyway, although the accuracy depends on the depth
of the architecture.

For reasons of interpretability, we train a rather small network, foregoing high accuracy.

Ground truth:

<p align="center">
<img src="img/sine_integral.png" alt="" width="600rem">
</p>

What the KAN has learned:

$$2.5cos(1.5sin(0.17sin(-1.8x-6.2)+3.9)-0.3)-1.4$$

<p align="center">
  <img src="img/kan_sine_integral.png" alt="" width="300rem">
</p>

### [Unsupervised learning](Unsupervised_Learning.ipynb)

In this test we try to solve an unsupervised learning problem. The data set consists of 7 variables with the following
relationships:

- $x_2=sin(6x_0)+e^{2x_1}$
- $x_6=4x_3+x_4+x_5$

KAN must discover these relationships based only on the value of these variables.

<p align="center">
  <img src="img/kan_unsupervised_1.png" alt="Image 1" width="300rem">
  <img src="img/kan_unsupervised_2.png" alt="Image 2" width="300rem">
</p>

### [Plotting EfficientKAN activations](Plotting_Efficient_KAN.ipynb)

This notebook provides a basic implementation of the `.plot()` function for the EfficientKAN networks. This is useful
for interpretation purposes.

### [Reducing the lookup table size](Reducing_the_lookup_table_size.ipynb)

The goal of this experiment is to use KAN's regression capability to approximate the popular multivariate Newton's Law
of Gravity to a sum of univariate functions in order to reduce the size of the lookup table.

$$F(m_1,m_2,d)=G\cdot \frac{m1\cdot m2}{d^2}$$

<p align="center">
  <img src="img/effkan_newton.png" alt="Image 2" width="500rem">
</p>


After obtaining a reasonable training result, we show how the lookup table grows linearly with the number of samples of
the input variables. Considering that the classic lookup table grows $\mathcal{O}(N^d)$, this is a huge size reduction.

<a name="Authors"></a>

## 👨🏻‍💻 Authors

| Name              | Email                       | GitHub                                          |
|-------------------|-----------------------------|-------------------------------------------------|
| Valerio Morelli   | s1118781@studenti.univpm.it | [MrPio](https://github.com/MrPio)               |
| Federica Paganica | s1116749@studenti.univpm.it | [Federica](https://github.com/federicapaganica) |
