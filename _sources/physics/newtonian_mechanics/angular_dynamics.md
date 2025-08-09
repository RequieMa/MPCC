# Angular Dynamics

# Angular Momentum
The angular momentum of an object is defined as 
$$
\vec L ~=~ \vec r \times \vec p\\
$$
where $\vec r$ is the displacement of the object from **pivot**, and $\vec p$ is the linear momentum.

The direction of angular momentum is the axis of rotation which is perpendicular to the rotation plane.

In Physics and Engineering, pivot is convinently to be defined at the axis of rotation. However, in partice, the axis of rotation may not be determined beforehind. 

Mathematically, however, the pivot can be **any point**. It is essentially an **origin** of the coordinate system that we imposed on the physical system. Therefore, with different coordinates (origin and directions), our exact value of angular momentum will be different. Yet, the resulting physical phenomena (the relative behaviour) will **not** be affected. 

# Torque
Taking the time derivative of the angular momentum
```{math}
\begin{eqnarray*}
    \frac{d \vec L}{dt} ~ &=& ~ \frac{d \vec r}{dt} \times \vec p + \vec r \times \frac{d \vec p}{dt}\\
    \, ~ &=& ~ \vec v \times \vec p + \vec r \times \vec F\\
\end{eqnarray*}
```
since $\vec p = m \vec v$ which is parallel with $\vec v$, $\Rightarrow \vec v \times \vec p = \vec 0$

$$
\vec \tau = \frac{d \vec L}{dt} ~=~ \vec r \times \vec F\\
$$
where $\vec \tau$ is the **torque** (the vector form of **moment**).

Again, we can say the definition of torque is **the rate of change of angular momentum, given a pivot**.

## Conservation of Angular Momentum
Similarly to the Linear Momentum, in a **closed system**, the total angular momentum is conserved around a given pivot. 

Consider $N$ particles in a system, the total angular momentum is $\sum_k^N \vec L_k$, where $\vec L_k$ refers as the angular momentum of a single particle. 

Then the conservation of angular momentum can be written as 
$$
\sum_k^N (\vec L_k)_i ~=~ \sum_k^N (\vec L_k)_f
$$
where $(\vec L_k)_i$ and $(\vec L_k)_f$ denote the initial and final angular momentum of the particle repectively.