# Linear Dynamics

# Newton's Three Laws

1. A particle remains at rest or moves in a straight line with constant speed if there is no resultant force acting on it.
2. Resultant force is the rate of change of momentum 
   
$$
\vec F ~=~ \frac{d \vec p}{dt}\\
$$

3. For any action, there is a reaction (equal in magnitude, opposite in direction, and collinear)

Our current form of Newton second law was written by Euler.

They are **laws** because they have been tested. Also, they cannot be **proved**, yet can be **disproved** using experiment. (The fact that we say "they have been tested" is that "they have not been disproved successfully" under our normal life scales)

Mass, $m$, is described as a **physical property** which reflects the ability to resist changing in velocity, known as **inertial mass**.

There is an implicit condition of Newton's laws: They have to be applied under an **inertial reference of frame** (i.e. not a frame under acceleration or rotation). Otherwise, we will measure acceleration even if there is no external force. (e.g. Coriolis Effect)

Absolute inertial frame where Neton 1st law holds is an idealized situation.

# Linear Momentum

$\vec p$ is the linear momentum, 

$$
    \vec{p} ~=~ m \vec{v}\\
$$

According to Newton 2nd law, momentum can be considered as a physical quantity for dynamic status. 

Since
```{math}
\begin{eqnarray*}
    \vec{F} ~ &=& ~ \frac{d \vec{p}}{dt}\\
    \, ~ &=& ~  \frac{d (m \vec{v})}{dt}\\
    \, ~ &=& ~  m \frac{d \vec{v}}{dt} + \frac{d m}{dt} \vec{v}\\
\end{eqnarray*}
```

if an object does not change its mass while force is applying on it, i.e. $\frac{dm}{dt} = 0$, then we have

$$
\vec F ~=~ m \vec a\\
$$

## Conservation of Linear Momentum
In a **closed system**, the total momentum is conserved. 

By closed system, we refer as the system of objects do not interact with external environment. (No external forces exerts on the system of objects).

Consider $N$ particles in a system, the total momentum is refered as $\sum_k^N \vec p_k$, where $\vec p_k$ refers as the momentum of a single particle. 

Then the conservation of linear momentum can be written as 

$$
\sum_k^N (\vec p_k)_i ~=~ \sum_k^N (\vec p_k)_f
$$

where $(\vec p_k)_i$ and $(\vec p_k)_f$ denote the initial and final linear momentum of the particle repectively.

## Newton 3nd Law from 1st and 2nd
..
