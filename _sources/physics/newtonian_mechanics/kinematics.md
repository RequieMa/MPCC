# Kinematics

There are two physical quantities that cannot actually be defined in physics: Position and Time. 

**Time**, $t$, is the most ill-defined physical quantity. We all assumed that we know what it is when we talked about time. However, we can only imagine the 'tick-tock' of a mechanical clock, not a conceptual definition of it. Some philosophers argues that our imagination of time comes from how understanding of 3D world where the perception of "distance" is vivid. Some go the other way around, like Kant. They think that our interest of "quantify distance" into some kinds of scale is from time as time is ticking all the time. The sensation of time is from the awareness of death which is the ultimate end. Nevertheless, in Physic, we only talk about the measurement of time, the different rate of time in different perspective or reference (in Relativity), sometimes the origin of time. Not time itself. We end our discussion of time with a quotation from Saint Augustine:
```
I know what it is, but when you ask me I don’t.
```

The other one is position. Unlike time, in Physics, we use the idea of position all the time, and we do define it. However, the discussion of position implicitly depends on the "origin" we set. Therefore, you can point out a location in space. However, to write down the actual mathematical descirption of this point, i.e. a specific coordinate, you need to define a **coordinate system**, like a Cartesian coordinate, beforehind. Therefore, in Physics, we are more keen to use **displacement** instead, which is the relative position. It can relative to an origin or another object. Physical phenomena will not be affected by it, only the equations will.

Given an origin, $O$, and some basis vectors (for Physics, normally in 3D) such that any position of objects, $A$ and $B$ can be written as 
$$
\vec O ~=~ \begin{pmatrix}0 \\ 0 \\ 0\end{pmatrix}\\
\vec {OA} ~=~ \begin{pmatrix}a_i \\ a_j \\ a_k\end{pmatrix}\\
\vec {OB} ~=~ \begin{pmatrix}b_i \\ b_j \\ b_k\end{pmatrix}
$$ 

The relative position or **displacement** in Physics is hence defined as
$$
\vec {AB} ~=~ \vec {OB} - \vec {OA} ~=~ \begin{pmatrix}b_i - a_i \\ b_j - a_j \\ b_k - a_k\end{pmatrix}\\
$$
normally written as $\vec r$ and is a function of time $\vec r = \vec r(t)$

For convinence, the two form of vector notation is interchangeable in Physics
$$
\vec r ~=~ \begin{pmatrix}x \\ y \\ z\end{pmatrix} = x \hat i + y \hat j + z \hat k
$$
The only difference is that the second one explicitly writes down the basis vector so that you know what kind of coordinate system we are using, the first one does not so it can be on other types of coordinate systems like a spherical polar coorinates. Without explicitly specifying, we assume the first one is using a Cartesian coordinate.

# Definitions of Velocity and Acceleration
**Velocity** of a particle is **the rate of change of displacement**
$$
\vec v ~=~ \frac{d \vec r}{dt}\\
$$

**Acceleration** of a particle is **the rate of change of velocity**
$$
\vec a ~=~ \frac{d \vec v}{dt} = \frac{d^2 \vec r}{dt^2}
$$

# Velocity and Acceleration on 2D Coordinate Systems
If we are in 2D, there are two natural option of coordinate systems: 
1. a Cartesian coordinate, $(x, y)$
2. a Polar coordinate, $(r, \theta)$, where $\theta$ is positive in anticlockwise direction $\theta \in (0, 2\pi)$

## In Caresian Coordinate
$$
\vec r ~=~ x \hat i + y \hat j\\
\Rightarrow \vec v ~=~ \frac{d \vec r}{dt} ~=~ \frac{d}{dt}\left(x \hat i \right) + \frac{d}{dt}\left(y \hat j \right)\\
$$

Using product rule, we have
$$
\Rightarrow \vec v ~=~ \frac{d x}{dt}\hat i + x \frac{d \hat i}{dt} + \frac{d y}{dt}\hat j + y \frac{d \hat j}{dt}\\
$$

Based on the geometry, we know that the direction of $\hat i$ and $\hat j$ does not change over time, hence the rate of change is zero.
$$
\Rightarrow \vec v ~=~ \frac{d x}{dt}\hat i + \frac{d y}{dt}\hat j\\
$$

Similarly, 
$$
\vec v ~=~ \frac{d x}{dt}\hat i + \frac{d y}{dt}\hat j\\
\Rightarrow \vec a ~=~ \frac{d \vec v}{dt} ~=~ \frac{d^2 x}{dt^2}\hat i + \frac{d^2 y}{dt^2}\hat j\\
$$

## In Polar Coordinate
Taking velocity and acceleration in Cartesian coordinate is trivial. However, in Polar coordinate, we have to be careful of the changing direction.
$$
\vec r ~=~ r \hat{e_r}\\
$$
Here, $\hat{e_r}$ is the radial direction and it is a function of angle, i.e. $\hat{e_r} = \hat{e_r}(\theta)$.
Then, 
```{math}
\begin{eqnarray*}
    \Rightarrow \vec v ~ &=& ~ \frac{d \vec r}{dt}\\
    \, ~ &=& ~ \frac{d}{dt}\left(r \hat{e_r} \right)\\
    \, ~ &=& ~  \frac{dr}{dt} \hat{e_r} + r \frac{d \hat{e_r}(\theta)}{dt}\\
\end{eqnarray*}
```
For the second term, we need to apply chain rule
$$
\Rightarrow \vec v ~=~ \frac{dr}{dt} \hat{e_r} + r \frac{d \hat{e_r}(\theta)}{d \theta} \frac{d \theta}{dt}\\
$$
To get an idea of what $\frac{d \hat{e_r}(\theta)}{d \theta}$ is, we can first consider the relation between Polar and Caresian Coordinate. 
$$
\hat{e_r}(\theta) = \cos(\theta) \hat i + \sin(\theta) \hat j\\
$$
Obviously, $\hat i$ and $\hat j$ are not dependent on $\theta$, thus,
```{math}
\begin{eqnarray*}
    \Rightarrow \frac{d \hat{e_r}(\theta)}{d \theta} ~ &=& ~ \frac{d}{d \theta}\left(\cos(\theta) \right)\hat i + \frac{d}{d \theta}\left(\sin(\theta) \right)\hat j\\
    \, ~ &=& ~ -\sin(\theta)\hat i + \cos(\theta)\hat j\\
    \, ~ &=& ~ \hat{e_\theta}\\
\end{eqnarray*}
```
It is clear that it satisfies the orthogonality of basis vector such that $\hat{e_r} \cdot \hat{e_\theta} = 0$

Therefore,
$$
\vec v ~=~ \frac{dr}{dt} \hat{e_r} + r \omega \hat{e_\theta}
$$
where $\omega = \frac{d \theta}{dt}$ is the **angular velocity**, which is **the rate of change of angular displacement** (the angle). (More in this, especially the vector form of it, will be shown later)

Similarly, 
```{math}
\begin{eqnarray*}
    \vec a ~ &=& ~ \frac{d \vec v}{dt}\\
    \Rightarrow ~ &=& ~ \frac{d}{dt}\left(\frac{dr}{dt} \hat{e_r}\right) + \frac{d}{dt}\left(r \omega \hat{e_\theta}\right)\\
    \, ~ &=& ~ \frac{d^2 r}{dt^2} \hat{e_r} + \frac{dr}{dt} \frac{d \hat{e_r}(\theta)}{dt}  + \frac{dr}{dt} \omega \hat{e_\theta} + r \frac{d\omega}{dt} \hat{e_\theta} + r \omega \frac{d \hat{e_\theta}}{dt}\\
    \, ~ &=& ~ \frac{d^2 r}{dt^2} \hat{e_r} + 2 \frac{dr}{dt} \omega \hat{e_\theta} + r \frac{d\omega}{dt} \hat{e_\theta} + r \omega^2 \frac{d \hat{e_\theta}}{d\theta}\\
\end{eqnarray*}
```
To solve the last term, we can use the aid of Caresian Coordinate again
```{math}
\begin{eqnarray*}
    \Rightarrow \frac{d \hat{e_\theta}}{d\theta} ~ &=& ~ -\frac{d}{d \theta}\left(\sin(\theta) \right)\hat i + \frac{d}{d \theta}\left(\cos(\theta) \right)\hat j\\
    \, ~ &=& ~ -\cos(\theta)\hat i - \sin(\theta)\hat j\\
    \, ~ &=& ~ -\hat{e_r}\\
\end{eqnarray*}
```

Therefore,
$$
\Rightarrow \vec a ~=~ \left(\frac{d^2 r}{dt^2} - r \omega^2 \right) \hat{e_r} + \left(r \alpha + 2 \frac{dr}{dt} \omega \right) \hat{e_\theta} \\
$$
where $\alpha = \frac{d\omega}{dt}$ is the **angular acceleration**, which is **the rate of change of angular velocity**.