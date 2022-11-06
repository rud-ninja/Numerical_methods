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
$$ 𝑡~~𝑖+1~~ = 𝑡~𝑖~ + ℎ $$
$$𝑈~𝑖+1~ = 𝑈~𝑖~ + ℎ.(𝑑𝑈 \over 𝑑𝑡)~𝑖~$$

2. **Midpoint method:** The midpoint method is used to estimate the area under a curve if it is difficult to solve analytically. In this method, we divide the input range, say (a, b) into n equal segments where size of each segment $h = (b-a) \over n$ is nothing but the step size. The value of the function is calculated at the midpoint of each segment i and eventually the estimation of the definite integral reduces to the sum of the area of the rectangles at each segment i with width equal to the step size h and height equal to u(t = imidpt).
∫ 𝑢(𝑡)𝑑𝑡𝑏𝑎 = Σ𝑢(𝑡 = 𝑖𝑚𝑖𝑑𝑝𝑡)𝑛. ℎ


4. **Runge Kutta 2nd order:**


6. **Runge Kutta 4th order:**


Fig 1: A grid display of all 4 methods mentioned in objective 1 in comparison with the closed form solution of a given differential equation.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/cf_vs_nm.jpg" alt="drawing" width="800"/>


Fig 2: A plot of the given function along with the trajectories of the paths taken to find the minima points.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/gradient_descent.jpg" alt="drawing" width="600"/>



Fig 3: Field direction and phase plot of the given dynamic systems.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/phase_plot.jpg" alt="drawing" width="1000"/>
