# cvx_irl

Code accompanies the paper "[Inverse Reinforcement Learning via Convex Optimization](https://haozhu10015.github.io/papers/cvx_irl.html)".

## Abstract

We consider the inverse reinforcement learning (IRL) problem, where an unknown reward function of some Markov decision process is estimated based on observed expert demonstrations.
In most existing approaches, IRL is formulated and solved as a nonconvex optimization problem, posing challenges in scenarios where robustness and reproducibility are critical.
We discuss a convex formulation of the IRL problem (CIRL) initially proposed by Ng and Russel, and reformulate the problem such that the domain-specific language CVXPY can be applied directly to specify and solve the convex problem.
We also extend the CIRL problem to scenarios where the expert policy is not given analytically but by trajectory as state-action pairs, which can be strongly inconsistent with optimality, by augmenting some of the constraints.
Theoretical analysis and practical implementation for hyperparameter auto-selection are introduced.
This note helps the users to easily apply CIRL for their problems, without background knowledge on convex optimization.

## Run the examples

We require the following Python libraries for running our examples.

```
numpy==1.26.4
cvxpy==1.6.0
matplotlib==3.10.0
seaborn==0.13.2
```

If you want to generate the video in example 2, `ffmpeg` is also required.

### Example 1: Gridworld

0. Go to the `example_1/src` directory.
1. Collect data: `python collect_demo.py`.
2. Follow the jupyter notebook `example_1/notebook/cirl.ipynb` to solve the problem and visualize the results.

### Example 2: The greedy snake

0. Go to the `example_2/src` directory.
1. Collect data: `python collect_demo.py`.
2. Solve the problem: `python cirl.py`.
3. Follow the jupyter notebook `example_2/notebook/plot.ipynb` to visualize the results.

### Appendix: Auto-tuning the scalarization weight

0. Go to the `lambda_autotune/src` directory.
1. Collect data: `python collect_demo.py`.
2. Follow the jupyter notebook `lambda_autotune/notebook/lambda_autotune.ipynb` to solve the problem with maximum scalarization weight (with nontrivial solution).
