---
layout: post
title: "A Primer on Optimal Control Theory"
date: 2024-09-28
tags: [optimal-control, optimization, control-theory]
---

Optimal control is about finding control inputs that minimize (or maximize) some performance criterion. This post summarizes key concepts I've learned while studying Kirk's "Optimal Control Theory."

## The Problem Formulation

Given a dynamical system:

$$ \dot{x} = f(x, u, t) $$

We want to find $u(t)$ that minimizes:

$$ J = \Phi(x(t_f), t_f) + \int_{t_0}^{t_f} L(x, u, t) dt $$

Where:
- $\Phi$ is the terminal cost
- $L$ is the running cost (Lagrangian)

## Three Main Approaches

### 1. Calculus of Variations
The classical approach, dating back to Euler and Lagrange. We derive the Euler-Lagrange equations and solve the resulting boundary value problem.

**Insight**: This extends to infinite-dimensional function spaces the idea of finding extrema by setting derivatives to zero.

### 2. Pontryagin's Maximum Principle
Introduces the Hamiltonian:

$$ H = L(x, u, t) + \lambda^T f(x, u, t) $$

The optimal control satisfies:

$$ u^* = \arg \min H(x, u, \lambda, t) $$

**Key advantage**: Can handle control constraints naturally.

### 3. Dynamic Programming
Bellman's approach based on the principle of optimality. Leads to the Hamilton-Jacobi-Bellman equation:

$$ -\frac{\partial V}{\partial t} = \min_u \left[ L(x,u,t) + \left(\frac{\partial V}{\partial x}\right)^T f(x,u,t) \right] $$

**Power**: Provides the optimal control as a function of state (feedback control).

## The LQR Problem

The Linear Quadratic Regulator is the most tractable optimal control problem:

**System**: $\dot{x} = Ax + Bu$  
**Cost**: $J = \int_{0}^{\infty} (x^T Qx + u^T Ru) dt$

The solution is the linear feedback:

$$ u^* = -Kx \quad \text{where} \quad K = R^{-1}B^T P $$

And $P$ satisfies the algebraic Riccati equation:

$$ A^T P + PA - PBR^{-1}B^T P + Q = 0 $$

**Why it matters**: LQR provides guaranteed stability margins and is the foundation for many modern control techniques.

## Applications to Power Systems

Optimal control appears in power systems in several contexts:
- Automatic Generation Control (AGC): Minimize frequency deviation
- Economic Dispatch: Minimize generation cost
- Optimal Power Flow: Minimize losses subject to constraints

I'm particularly interested in how Model Predictive Control (MPC) uses optimal control in a receding horizon fashion.

## Next Steps

Planning to dive deeper into:
- Stochastic optimal control (for uncertainty)
- Differential games (for multi-agent systems)
- Connection to reinforcement learning
