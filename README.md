# Hill Climbing Algorithm in MATLAB
**Prof. Aboud BARSEKH-ONJI (D.Sc.)**

**Email: aboud.barsekh@anahuac.mx**

**https://orcid.org/0009-0004-5440-8092**

**Universidad Anáhuac México Sur - Facultad de Ingeniería** 

This repository provides a MATLAB implementation of the **Hill Climbing algorithm**, demonstrating its behavior on two different types of objective functions. The goal is to visually showcase both the strengths and weaknesses of this local search algorithm.

The project includes two main scripts:
1.  A demonstration on a **simple, single-optimum function** where Hill Climbing efficiently finds the peak.
2.  A demonstration on a **complex function with multiple local optima** to show how the algorithm can get "trapped" and fail to find the global optimum.

---

## 📜 Scripts Description

### 1. `HillClimbingOneOpt.m`

This script applies the Hill Climbing algorithm to a simple, convex function (an inverted paraboloid) defined as:
$$f(x, y) = - (x^2 + y^2)$$
The global optimum is at $(0, 0)$. This example illustrates an ideal scenario for Hill Climbing, where the algorithm is guaranteed to find the single peak from any random starting point.

**Output:**
* A 3D plot of the function's surface.
* A visual path showing the algorithm's steps from a random start point (green) to the optimal peak (black).


### 2. `HillClimbingMultiOpt.m`

This script demonstrates the primary limitation of the Hill Climbing algorithm. It uses MATLAB's built-in `peaks` function, which has multiple local optima and one global optimum.
$$f(x, y) = 3(1-x)^2e^{-x^2 - (y+1)^2} - 10(\frac{x}{5} - x^3 - y^5)e^{-x^2-y^2} - \frac{1}{3}e^{-(x+1)^2 - y^2}$$
Depending on the randomized starting point, the algorithm will often converge to the nearest local peak, which may not be the highest peak (the global optimum).

**Output:**
* A 3D plot of the complex "peaks" surface.
* A visual path showing the algorithm ascending the nearest hill, often getting trapped in a sub-optimal solution.

---

## How to Run

To run the demonstrations, you need **MATLAB** installed.

1.  **Clone the repository** or download the files.
2.  **Open MATLAB**.
3.  Navigate to the directory where you saved the files.
4.  Run the desired script by typing its name in the MATLAB Command Window and pressing Enter:

    ```matlab
    % To run the simple function example
    HillClimbingOneOpt
    ```
    or
    ```matlab
    % To run the complex function example
    HillClimbingMultiOpt
    ```
5.  A figure will be generated showing the function surface and the algorithm's path. The console will also display the coordinates of the optimum found.

---

## Understanding the Visualizations

In each generated plot, you will see:
* **The Surface Plot:** The 3D landscape of the objective function.
* **Green Marker:** The random starting point of the algorithm.
* **Red Path:** The step-by-step trajectory taken by the algorithm as it moves to "higher ground."
* **Black Marker:** The final point where the algorithm stopped—the peak it found.

By running the `HillClimbingMultiOpt.m` script multiple times, you will observe how different starting points lead to different final peaks, clearly illustrating the concept of getting stuck in local optima.
