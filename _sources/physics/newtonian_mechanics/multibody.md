# Multibody Dynamics

[reference MAE/BIM 223: Multibody Dynamics](https://moorepants.github.io/mae223/schedule.html)

1. Direct dynamics: Given $\vec F$ and find $m \vec a$
2. Inverse dynamics: Given $m \vec a$ and find $\vec F$

Our systems is made of particles and rigid bodies:
1. Particle: object with mass but no dimensions or extent
2. Rigid body: object has mass but also extent (distributed mass in space)

## Equations of Motion (EoM)
Linear motion - Newton's 2nd Law
$$
\vec F ~ = ~ \frac{d \vec p}{dt}
$$

Rotational motion - Euler's 2nd Law
$$
\vec \tau ~ = ~ \frac{d \vec L}{dt}
$$

## Methods to derive the EoM
Focus on Kane's Method (?) (Uses generalized speeds and avoids constraint forces)

Other methods: Newton-Euler (Applies Newton’s second law to each body in a system), Lagrange (Uses energy (kinetic - potential) and generalized coordinates), Hamilton (Reformulates Lagrangian mechanics using generalized momenta), Jain (Generalized recursive dynamics using projection operators), Featherstone (Recursive Newton-Euler for articulated rigid bodies), Denavit-Hartenberg (Not a dynamics method per se, but a kinematic modeling tool for robots), Gibbs-Apell (Uses acceleration energy (Appell’s function) to derive EoM), etc.

| Method               | Best For                        | Pros                                | Cons                                 |
|----------------------|----------------------------------|-------------------------------------|--------------------------------------|
| **Newton-Euler**     | Simple systems                  | Intuitive, force-based              | Tedious for complex systems          |
| **Lagrangian**       | General systems with constraints| Elegant, energy-based               | Algebra-heavy                        |
| **Hamiltonian**      | Theoretical physics             | Symplectic, control-friendly        | Less intuitive                       |
| **Kane’s**           | Multibody dynamics              | Compact, efficient                  | Requires new concepts                |
| **Featherstone**     | Real-time robotics              | Fast, recursive                     | Tree-structured only                 |
| **Jain’s**           | Closed-loop systems             | Modular, efficient                  | Less common                          |
| **Denavit-Hartenberg** | Robot kinematics              | Standardized, simple transforms     | Not for dynamics                     |
| **Gibbs-Appell**     | Constrained systems             | Compact equations                   | Rare, less intuitive                 |


DH, Featherstone, Jain methods are essentially Newton-Euler mechanics transformed into structured computational frameworks.

Kane’s method typically uses a body-fixed frame or a frame attached to a joint/link. Velocities and accelerations are expressed relative to this frame, not necessarily an inertial frame. Each body’s motion is described locally.

both Kane’s and Gibbs-Appell methods assume:
- Rigid bodies or point masses.
- Constant mass and inertia (no mass flow or variable mass systems).
- No internal deformation or elasticity unless explicitly modeled.

not suitable for: Fluid dynamics

## Reference Frames
- reference frames and rigid bodies are interchangable
- every rigid body can serve as a RF and every RF can be a rigid body
- reference frame $\ne$ coordinate system (many cooridnate systems in single RF)
- reference frames can be oriented to other RFs, but there is no property of translation
