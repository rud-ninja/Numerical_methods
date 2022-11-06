# Title: Numerical Methods

## Objectives:
1. Test 4 different numerical algorithms with varying step sizes to estimate definite integrals, namely; Euler, Midpoint, Runge Kutta 2nd order and 4th order. Compare the solutions of the above to the closed form solution.
2. Find the minima points of a given function (of order greater than 2) using gradient descent (optimisation algorithm)
3. Analyse a given dynamic system.


#### Libraries used:
Pandas, NumPy, SciPy, Matplotlib


## Summary and figures:
### Objective 1:
Numerical integration schemes are applied to ordinary differential equations often when their closed-form solution is difficult to find or when the value of a definite integral needs to be estimated. There are multiple numerical integration techniques and below are described 4 of them:
1. **Euler'smethod:** To apply Euler’s method of numerical integration, the initial conditions of the function must be known. In this case we have u(t=0) = 2. In Euler’s method, we start from the initial point and calculate the next point using the gradient of the function and a step size. Therefore, in the question, considering a step size h, we get;

      ![](https://latex.codecogs.com/gif.latex?t_%7Bi&plus;1%7D%20%3D%20t_%7Bi%7D%20&plus;%20h)

      ![](https://latex.codecogs.com/gif.latex?U_%7Bi&plus;1%7D%20%3D%20U_%7Bi%7D%20&plus;%20h.%5Cleft%20%28%20%5Cfrac%7BdU_%7Bi%7D%7D%7Bdt%7D%20%5Cright%20%29)

2. **Midpoint method:** The midpoint method is used to estimate the area under a curve if it is difficult to solve analytically. In this method, we divide the input range, say (a, b) into n equal segments where size of each segment ![](https://latex.codecogs.com/gif.latex?h%20%3D%20%5Cfrac%7B%28b-a%29%7D%7Bn%7D) is nothing but the step size. The value of the function is calculated at the midpoint of each segment i and eventually the estimation of the definite integral reduces to the sum of the area of the rectangles at each segment i with width equal to the step size h and height equal to ![](https://latex.codecogs.com/gif.latex?u%28t%20%3D%20i_%7Bmidpt%7D%29.)

      ![](https://latex.codecogs.com/gif.latex?%5Cint_%7Ba%7D%5E%7Bb%7Du%28t%29dt%20%3D%20%5Csum_%7Bn%7D%5E%7B%7Du%28t%3Di_%7Bmidpt%7D%29.h)


4. **Runge Kutta 2nd order:** Similar to Euler’s Method, the Runge Kutta second order numerical method requires initial conditions of the ordinary differential equation. Starting from the initial value of u(t), it calculates the subsequent values using the weighted average of two gradients as following;

      ![](https://latex.codecogs.com/gif.latex?t_%7Bi&plus;1%7D%20%3D%20t_i%20&plus;h)
      
      ![](https://latex.codecogs.com/gif.latex?K_1%20%3D%20h%20*%20f%28t_i%2C%20u_i%29)
      
      ![](https://latex.codecogs.com/gif.latex?K_2%20%3D%20h%20*%20f%5Cleft%20%28%20%5Cleft%20%28%20t_i%20&plus;%5Cfrac%7Bh%7D%7B2%7D%20%5Cright%20%29%2C%20%5Cleft%20%28%20u_i%20&plus;%20%5Cfrac%7BK_1*h%7D%7B2%7D%20%5Cright%20%29%20%5Cright%20%29)
      
      ![](https://latex.codecogs.com/gif.latex?u_%7Bi&plus;1%7D%20%3D%20u_i%20&plus;%20K_2)


6. **Runge Kutta 4th order:** Similar to Runge Kutta 2nd order, the 4th order takes weighted mean of 4 gradients to calculate the next value. The formulas are as below;

      ![](https://latex.codecogs.com/gif.latex?t_%7Bi&plus;1%7D%20%3D%20t_i%20&plus;h)
      
      ![](https://latex.codecogs.com/gif.latex?K_1%20%3D%20h%20*%20f%28t_i%2C%20u_i%29)
      
      ![](https://latex.codecogs.com/gif.latex?K_2%20%3D%20h%20*%20f%5Cleft%20%28%20%5Cleft%20%28t_i&plus;%5Cfrac%7Bh%7D%7B2%7D%20%5Cright%20%29%2C%5Cleft%20%28u_i%20&plus;%20%5Cfrac%7BK_1%7D%7B2%7D%20%5Cright%20%29%20%5Cright%20%29)
      
      ![](https://latex.codecogs.com/gif.latex?K_3%20%3D%20h%20*%20f%5Cleft%20%28%20%5Cleft%20%28t_i&plus;%5Cfrac%7Bh%7D%7B2%7D%20%5Cright%20%29%2C%5Cleft%20%28u_i%20&plus;%20%5Cfrac%7BK_2%7D%7B2%7D%20%5Cright%20%29%20%5Cright%20%29)
      
      ![](https://latex.codecogs.com/gif.latex?K_4%20%3D%20h%20*%20f%28%28t_i&plus;h%29%2C%28u_i&plus;K_3%29%29)
      
      ![](https://latex.codecogs.com/gif.latex?u_%7Bi&plus;1%7D%20%3D%20u_i%20&plus;%20%5Cfrac%7B1%7D%7B6%7D%28K_1%20&plus;2K_2&plus;2K_3&plus;K_4%29)


Fig 1: A grid display of all 4 methods mentioned above; compared with the closed form solution of the given differential equation.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/cf_vs_nm.jpg" alt="drawing" width="800"/>



### Objective 2:
Gradient descent is an optimization algorithm that is used to find the minima of a function when they are difficult to solve analytically. In the question, the given function to minimize is:

![](https://latex.codecogs.com/gif.latex?f%28x%2Cy%29%20%3D%20%28x%5E4&plus;y%5E4%29-%2821x%5E2&plus;13y%5E2%29&plus;2xy%28x&plus;y%29-%2814x&plus;22y%29&plus;170)
      
The way gradient descent works is as follows:
- Start at a random point ‘w’ on the plane.
- Calculate the gradient of the function at point
‘w’.
- Calculate the next point by moving a step from ‘w’ in a direction in which the value of the function drops the fastest. This implies going in the opposite direction of the gradient if gradient is positive and in the direction of the gradient if it is negative. The step size (h) is set at the beginning for whom a smaller value is beneficial for better results.

     ![](https://latex.codecogs.com/gif.latex?w_%7Bi&plus;1%7D%20%3D%20w_i%20-%20h.%5Cbigtriangledown%20f%28w_i%29)
      
- Repeat previous step until a point is reached from where value of f(x, y) starts to rise again and stop. The coordinates where the algorithm stops are potential minima points (might be local or global).
- Start from another random point and follow all steps again until true minima are obtained.



Fig 2: A plot of the given function along with the trajectories of the paths taken to find the minima points.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/gradient_descent.jpg" alt="drawing" width="600"/>


### Objective 3:

Fig 3: Field direction and phase plot of the given dynamic systems.

<img src="https://github.com/rud-ninja/Numerical_methods/blob/main/phase_plot.jpg" alt="drawing" width="1000"/>

The above plot shows the field vector magnitude and direction in the given range along with eigenvectors plotted for each equilibria point.

The thick dark arrows in the field direction plot represent the eigenvectors of the system at the equilibrium points (0,0) and (2,1). The eigenvectors and their associated eigenvalues scale and give shape to the field direction vectors. We can see the eigenvectors at (0,0) are orthogonal. The eigenvector at y=0 has eigenvalue 0 and hence everything on the line is 0. The eigenvector given by x=0 has eigenvalue - 1 therefore it mirrors the arrows on the line about the origin and shrinks them. Similarly, the point (2,1) has 2 eigenvectors. The one pointing to the right has a eigenvalue 1 + √2 and it expands the arrows in that direction by the same factor and the other one pointing left has eigenvalue 1 − √2 and so it shrinks the arrows. The eigenvectors at both the points affect the shape of the direction field and the eigenvalues affect the size of the direction vector.



This work was originally part of the coursework for the my Master's degree in Data Science. For more detailed information regarding the objectives and/or terminologies, please click here.
