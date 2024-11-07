# ICP (Iterative Closest Point) Algorithm with SVD-based Transformation

This repository contains a Jupyter Notebook implementation of the **Iterative Closest Point (ICP)** algorithm, used for 3D point cloud registration. The ICP algorithm is widely used in computer vision, robotics, and 3D modeling to align two point clouds by iteratively minimizing the distance between corresponding points.

---

## Key Features
- **SVD-based ICP**: The alignment is performed using Singular Value Decomposition (SVD) to find the optimal transformation (rotation and translation) between the source and target point clouds.
- **Visualizations**: The notebook provides interactive visualizations showing the transformation of the source point cloud across iterations.

---

## How to Use
1. **Clone this repository** to your local machine.
2. Install the necessary dependencies (such as `numpy`, `scipy`, `matplotlib`, and `ipympl`).
3. Open the notebook (`ICP_Algorithm.ipynb`) and run the cells to load point clouds and apply the ICP algorithm.

---

## ICP Algorithm Overview

The **Iterative Closest Point (ICP)** algorithm iteratively refines the alignment of two point clouds. At each iteration, the algorithm:

For more information on ICP, check out the [ICP Wikipedia page](https://en.wikipedia.org/wiki/Iterative_closest_point).

### SVD-based ICP
The SVD-based ICP algorithm computes the optimal transformation (rotation and translation) using Singular Value Decomposition (SVD) to minimize the least-squares error between corresponding points in the source and target point clouds.

Learn more about SVD-based ICP in the following resources:
- [ICP on Wiki](https://en.wikipedia.org/wiki/Iterative_closest_point)

---

## Installation Instructions

To run the notebook, you need to install the required dependencies. You can install them using `pip`:

```bash
pip install numpy scipy matplotlib ipympl
