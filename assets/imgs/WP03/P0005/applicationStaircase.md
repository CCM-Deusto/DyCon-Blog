---
title: Control of reaction-diffusion under state constraints - Application of the staircase method
author: [DomenecR]
date: 2020-03-30
description: This tutorial is part of the control under state constraints. We will present how to generate admissible paths of steady states for the homogeneous reaction-diffusion equation.
layout: tutorial
categories: [tutorial,WP03]
url_zip:
avatar: https://deustotech.github.io/DyCon-Blog//assets/imgs/WP03/P0005/figures/completepath02L12-1.png
code: MATLAB
equation: HEAT
---

In this tutorial, we will present how to generate admissible paths of steady states for the homogeneous reaction-diffusion equation:

$$ \begin{cases}
u_t-\Delta u=u(1-u)(u-\theta)\quad (x,t)\in \Omega\times(0,T),\\
u=a(x,t)\qquad \qquad\qquad\qquad(x,t)\in \partial\Omega\times(0,T),\\
 0\leq u(x,0)\leq 1.
\end{cases}$$

This a key argument for ensuring controllability that has been studied in [2,3,4,5].

## Stair-case method
The stair-case method ( see [1]) guarantees the following:

If we have an admissible continuous path of steady states, for any initial datum in the path, any target function in the path and for $T>0$ sufficiently large, there exists a function $a$ such that drives the system from the initial datum to the target fulfilling the state-constraints along the trajectory.


<center>
<img  src="figures/Plot_Staircase.png"  width="350"  height="300"  />
</center>
<center><b>Figure 1.</b> Qualitative understanding of the Stair-case method. When we have a continuous admissible path of steady-states, one can find a control that is connecting the initial steady state with the target by "jumping" along the continuous path.</center>
</div>

## Extension to ball, and the phase-plane analysis

We will restrict ourselves to the construction of paths that connect the steady state $w\equiv 0$ with the steady state $w\equiv \theta$. For doing such example with our model bistable equation. 

In order to construct the paths we will use phase-plane techniques for which we use radial coordinates. Our original domain might not be a ball, for this reason we extend it to a ball and firstly construct the path there.



<center>
<img width="25%" src="{{site.url}}{{site.baseurl}}/assets/imgs/WP03/P0005/figures/ballE-1.png"  />
</center>
<center><b>Figure 2.</b> Extension of our domain to a ball.</center>

Remind that the important issue is to be able to guarantee that for every domain $w\equiv0$ and $w\equiv\theta$ are connected in an admissable way and this is seen in the phase plane representation of the elliptic equation.

$$ -u_{rr}-\frac{N-1}{r}u_r=u(1-u)(u-\theta),$$
$$u(0)=a,$$
$$ u_r(0)=0.$$


Now, considering the energy
$$ E(u,v)=\frac{1}{2}v^2+F(u)$$

where $F(u)=\int_0^u f(s)ds$, one can see that the radial ODE dissipates.

Define the following region:
$$ D:=\left\{(u,v)\in\mathbb{R}^2 \quad \text{such that}\quad E(u,v)\leq 0\right\} $$
Let $\theta_1$ be defined as:
$$\theta_1=\min_{s>0}\{F(s)=0\}$$

Note that the region defined by 
$$
 \Gamma:=\left\{(u,v)\in[0,\theta_1]\times\mathbb{R}\quad\text{such that}\quad |v|\leq \sqrt{-2F(u)}\right\}
$$
Note that $\Gamma\subset D$. 

Take $(u_0,0)\in \Gamma$, then the solution of the radial equation with initial
datum $(u_0,0)$ satisfies:

$$\frac{d}{dr}E(u,v)=vv_r+f(u)v=-\frac{N-1}{r}v^2<0$$

So $(u,v)\in\Gamma$ for all $r>0$.


We have that the blue line (the border of $\Gamma$) in the following figure determines a positively invariant region.

Then, making $a$ change continuously from $0$ to $\theta$ we generate a continuous path (by the Gromwall inequality) that is admissible since the invariant region $\Gamma$ is inside the admissible set.


<center>
<img  width="60%" src="{{site.url}}{{site.baseurl}}/assets/imgs/WP03/P0005/figures/ContinuousPathinthePhaseSpace-1.png"  />
</center>
<center><b>Figure 3.</b> Invariant region and construction of the path.</center>



## Animation of the path

 
<center>
<video width="80%" controls>
  <source src="{{site.url}}{{site.baseurl}}/assets/imgs/WP03/P0005/figures/video.mp4" type="video/mp4">
</video>
</center>
<center><b>Figure 4.</b> Path of steady states.</center>




If our domain is not a ball we restrict our path to the original domin to obtain the desired path.



## Other features

General existence of admisible paths is not true due to the comparison principle. Non-trivial steady states can exist that block any possibity to control (See blog entry [Nontrivial]).

Here we restrict ourselves in the one dimensional case. In the following figure one can see how can we connect the steady state $w\equiv 0$ with the first nontrivial solution with boundary value $0$.

<center>

<table>
    <tr>
        <th>
            <img  src="{{site.url}}{{site.baseurl}}/assets/imgs/WP03/P0005/figures/Lcomp-1.png"  />
        </th>
         <th>
            <img  src="{{site.url}}{{site.baseurl}}/assets/imgs/WP03/P0005/figures/Lcomp2-1.png"  />
                    </th>       
    </tr>
</table>
</center>

<center><b>Figure 5.</b> Path of steady states.</center>


However, since this path touches the boundary of the admissible set controllability cannot be guaranteed due to the comparison principle. 


Another important remark to be mentioned is that if we forget about the state constraints, more paths can be generated, provided that the ODE representation of the elliptic equation does not blow up. The following figure is an example of a path connecting $w\equiv 0$ with $w\equiv 1$ that violates the constraints:

<center>
<table>
    <tr>
        <th>
            <img  src="{{site.url}}{{site.baseurl}}/assets/imgs/WP03/P0005/figures/completepath02L12-1.png"  />
        </th>
         <th>
            <img  src="{{site.url}}{{site.baseurl}}/assets/imgs/WP03/P0005/figures/Completepath01L12-1.png"  />
                    </th>       
    </tr>
</table>
</center>
<center><b>Figure 6.</b> Path of steady states violating constraints.</center>


## References:

[1] D. Pighin, E. Zuazua, Controllability under positivity constraints of multi-d wave equations, in:
Trends in Control Theory and Partial Differential Equations, Springer, 2019, pp. 195–232.

[2] J.-M. Coron, E. Trélat, Global steady-state controllability of one-dimensional semilinear heat equa-
tions, SIAM J. Control. Optim. 43 (2) (2004) 549–569.

[3] C. Pouchol, E. Trélat, E. Zuazua, Phase portrait control for 1d monostable and bistable reac-
635
tion–diffusion equations, Nonlinearity 32 (3) (2019) 884–909.

[4]   D.  Ruiz-Balet  and  E.  Zuazua. Controllability  under  constraints  for  reaction-diffusionequations:   The  multi-dimensional  case.   Preprint  available  athttps://cmc.deusto.eus/domenec-ruiz-balet/.

[5] D.  Ruiz-Balet  and  E.  Zuazua. Control of certain parabolic models from biology and social sciences.   Preprint  available  at https://cmc.deusto.eus/domenec-ruiz-balet/.



  
