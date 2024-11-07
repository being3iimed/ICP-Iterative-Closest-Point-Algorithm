ICP (Iterative Closest Point) Algorithm with Visualization

This project implements the Iterative Closest Point (ICP) algorithm for aligning 3D point clouds. The algorithm is demonstrated using a source and a target point cloud, where the goal is to iteratively transform the source point cloud so that it aligns with the target point cloud. The project also provides real-time visualization of the ICP process after each iteration, showing how the source and target points gradually align.
Table of Contents

    Project Overview
    Installation Instructions
    Usage
    Functions
    Contributing
    License

Project Overview

This project provides an implementation of the ICP algorithm for 3D point cloud registration. The main feature of this project is the real-time visualization of the source point cloud being transformed and aligned with the target point cloud, with plots generated after each iteration. This helps users to visualize how the algorithm iteratively refines the alignment.
Key Features:

    Interactive 3D plots: Visualize the source and target point clouds in 3D and track the progress of the transformation across iterations.
    Mean Residual Calculation: Calculate and display the residual error (the mean distance between corresponding points) at each iteration.
    Perturbation: Apply a random perturbation (rotation and translation) to the source point cloud to simulate real-world misalignments.

Installation Instructions

To run this project locally, follow these steps:

    Clone the repository:

git clone [https://github.com/being3iimed/IterativeClosestPoint.git]
cd IterativeClosestPoint

Install dependencies: This project requires numpy, matplotlib, and scipy for numerical and plotting operations. You can install them using pip:

    pip install numpy matplotlib scipy

    Run the code: Open a Jupyter Notebook or a Python script and run the provided code cells. Ensure you have the necessary 3D point cloud data (.obj or .ply files) for the demonstration.

Usage

To run the ICP algorithm, use the provided functions in the notebook or Python script. The primary function to run ICP is icp_with_individual_plots, which computes the transformation from a source point cloud to a target point cloud while visualizing each iteration.

Here is how you can call the function:

# Example usage
points_source = np.random.rand(100, 3)  # Replace with actual source point cloud data
points_target = np.random.rand(100, 3)  # Replace with actual target point cloud data

# Apply ICP with visualization
T_accumulated, residuals = icp_with_individual_plots(points_source, points_target, n_iter=20, threshold=0.01)

Functions
perturb_data(points, R_true, t_true)

    Description: This function applies a random perturbation (rotation and translation) to a given point cloud.
    Parameters:
        points: A N×3N×3 numpy array representing the point cloud.
        R_true: A 3×33×3 rotation matrix.
        t_true: A 3×13×1 translation vector.
    Returns: A new point cloud with the applied perturbation.

mean_dist(points1, points2)

    Description: Calculates the mean Euclidean distance (residual) between corresponding points in two point clouds.
    Parameters:
        points1: A N×3N×3 numpy array representing the first point cloud.
        points2: A N×3N×3 numpy array representing the second point cloud.
    Returns: A float value representing the mean residual distance.

icp_core(points1, points2)

    Description: Computes the transformation (rotation and translation) from points1 to points2 using Singular Value Decomposition (SVD).
    Parameters:
        points1: A N×3N×3 numpy array representing the source point cloud.
        points2: A N×3N×3 numpy array representing the target point cloud.
    Returns: A 4x4 transformation matrix T that aligns points1 to points2.

icp_with_individual_plots(points_source, points_target, n_iter=20, threshold=0.01)

    Description: Performs the ICP algorithm, iteratively transforming the source point cloud to align with the target point cloud. This function generates a plot for each iteration to visualize the progress.
    Parameters:
        points_source: A N×3N×3 numpy array representing the source point cloud.
        points_target: A N×3N×3 numpy array representing the target point cloud.
        n_iter: The number of iterations for the ICP algorithm (default is 20).
        threshold: The residual error threshold for convergence (default is 0.01).
    Returns:
        T_accumulated: The final accumulated transformation matrix.
        residuals: A list of residual errors at each iteration.

Contributing

Feel free to open issues, submit pull requests, or ask questions about the project.
How to Contribute:

    Fork the repository.
    Create a new branch (git checkout -b feature-branch).
    Make your changes.
    Commit your changes (git commit -am 'Add new feature').
    Push to the branch (git push origin feature-branch).
    Open a pull request.

License

This project is licensed under the MIT License - see the LICENSE file for details.
Notes

    Ensure that you have the required dependencies installed before running the code.
    You can use 3D point clouds from .obj, .ply, or any other supported format, provided they are loaded into a numpy array for processing.

This README.md file should give users clear instructions on how to run and understand your project. Feel free to adjust the content to fit your specific repository structure and project needs!
