# Title: Numerical Methods

## Objectives:
1. Test 4 different numerical algorithms with varying step sizes to estimate definite integrals, namely; Euler, Midpoint, Runge Kutta 2nd order and 4th order. Compare the solutions of the above to the closed form solution.
2. Find the minima points of a given function (of order greater than 2) using gradient descent (optimisation algorithm)
3. Analyse a given dynamic system.


#### Libraries used:
Pandas, NumPy, SciPy, Matplotlib


## Figures:
Numerical integration schemes are applied to ordinary differential equations often when their closed-form solution is difficult to find or when the value of a definite integral needs to be estimated. There are multiple numerical integration techniques and below are described 4 of them:
1. **Euler'smethod:** To apply Euler’s method of numerical integration, the initial conditions of the function must be known. In our question we have u(t=0) = 2. In Euler’s method, we start from the initial point and calculate the next point using the gradient of the function and a step size. Therefore, in the question, considering a step size h, we get;

  * ![](https://latex.codecogs.com/gif.latex?t_%7Bi&plus;1%7D%20%3D%20t_%7Bi%7D%20&plus;%20h)

  * ![](https://latex.codecogs.com/gif.latex?U_%7Bi&plus;1%7D%20%3D%20U_%7Bi%7D%20&plus;%20h.%5Cleft%20%28%20%5Cfrac%7BdU_%7Bi%7D%7D%7Bdt%7D%20%5Cright%20%29)

2. **Midpoint method:** The midpoint method is used to estimate the area under a curve if it is difficult to solve analytically. In this method, we divide the input range, say (a, b) into n equal segments where size of each segment ![](https://latex.codecogs.com/gif.latex?h%20%3D%20%5Cfrac%7B%28b-a%29%7D%7Bn%7D) is nothing but the step size. The value of the function is calculated at the midpoint of each segment i and eventually the estimation of the definite integral reduces to the sum of the area of the rectangles at each segment i with width equal to the step size h and height equal to ![](https://latex.codecogs.com/gif.latex?u%28t%20%3D%20i_%7Bmidpt%7D%29.)

![](https://latex.codecogs.com/gif.latex?%5Cint_%7Ba%7D%5E%7Bb%7Du%28t%29dt%20%3D%20%5Csum_%7Bn%7D%5E%7B%7Du%28t%3Di_%7Bmidpt%7D%29.h)


4. **Runge Kutta 2nd order:**


6. **Runge Kutta 4th order:**


Fig 1: A grid display of all 4 methods mentioned in objective 1 in comparison with the closed form solution of a given differential equation.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/cf_vs_nm.jpg" alt="drawing" width="800"/>


Fig 2: A plot of the given function along with the trajectories of the paths taken to find the minima points.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/gradient_descent.jpg" alt="drawing" width="600"/>



Fig 3: Field direction and phase plot of the given dynamic systems.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/phase_plot.jpg" alt="drawing" width="1000"/>
