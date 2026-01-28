# ⚛ Molecular-Dynamics

The main objective of this project is to simulate a Lennard-Jones gas of N particles, studying the temporal evolution, energies, and trajectories of the particles in the system.

---
**Modeling**

To model our Lennard-Jones gas, we will use the Lennard-Jones potential equation, which describes the cohesion between particles and accounts for the repulsive and attractive forces between them. The Verlet algorithm will be used to calculate and model the trajectory of the particles.

---
**Lennard-Jones potential** 

Here is the equation for the force derived from the Lennard-Jones potential energy

$$F(r) = \frac{48}{r^2} \cdot \varepsilon \left( \left( \frac{1}{r^{12}} \right) - \frac{1}{2} \cdot \left( \frac{1}{r^6} \right) \right) \vec{r}$$

ε: the depth of the potential well
r: the distance between the two particles 

We first initialized the initial conditions for the positions in x and y, to enable us to calculate the positions of the different particles, and therefore the distance between them, allowing us to calculate the forces of interaction between them.

---

**Verlet algorithm**

The integration of the equations of motion is performed using this algorithm:

$$r(t + \Delta t) = 2 \cdot r(t) - r(t - \Delta t) + F(r) \cdot \Delta t^2$$                                                                                    
 $$(\Delta t)$$ = time step

We integrated the equations of motion in x and y using the interaction forces calculated using the Lennard-Jones force, then stored the new positions in a table.

---
**Energies**

---

**Kinetic energy of the system**

To calculate the kinetic energy, we need the velocities, which can be determined using the new positions stored in the r table with the expression: 

$$v(t) = \frac{(r(t + \Delta t) - r(t - \Delta t))}{2 \cdot \Delta t}$$

Since the position array is a vector array, we also have a vector array for velocity, so we calculated the velocity norm first and then calculated the kinetic energy.

---
**Potential Energy**

For the calculation, we used the integral form of the Lennard-Jones derivative force: 

$$U(r) = 4 \cdot \varepsilon \cdot \left( \left( \frac{1}{r^{12}} \right) - \left( \frac{1}{r^6} \right) \right)$$

---
**Results**

---

**Trajectories**

Here is the modeling of some trajectories with:
<img width="2735" height="2685" alt="Capture d’écran 2026-01-28 211330_upscayl_5x_upscayl-standard-4x" src="https://github.com/user-attachments/assets/c863abb8-ee40-4f16-a6a2-575347fba86e" />

M=30, e=1, N=1000, L=50, B=3, and epsilon=0.1

---
**Energie Potentiel en fonction du temps**
<img width="3550" height="2460" alt="Capture d’écran 2026-01-28 211518_upscayl_5x_upscayl-standard-4x" src="https://github.com/user-attachments/assets/94679332-5a64-464c-a57a-7955e5eac80f" />

---
**Énergie cinétique en fonction du temps**
<img width="3435" height="2180" alt="Capture d’écran 2026-01-28 211614_upscayl_5x_upscayl-standard-4x" src="https://github.com/user-attachments/assets/311978df-23bb-41d1-a1ed-bd7ed56e1576" />

---
**Energie total en fonctio**
<img width="3225" height="2150" alt="Capture d’écran 2026-01-28 211743_upscayl_5x_upscayl-standard-4x" src="https://github.com/user-attachments/assets/c7b170a8-8b82-4a38-8c95-757730b9100e" />



