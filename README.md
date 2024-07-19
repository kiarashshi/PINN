# PINN
flow around circular cylinder
## Introduction 
This project provides a numerical solution for the steady-state Navier-Stokes equations for fluid flow over a cylinder at a Reynolds number (Re) of 200 using Physics-Informed Neural Networks (PINN). This innovative approach leverages neural networks to solve partial differential equations (PDEs) and offers a powerful alternative to traditional computational fluid dynamics (CFD) methods.

## Navier-Stokes Equation

The governing equations for steady-state incompressible flow over a cylinder using the Navier-Stokes equations are given by:

 <p>$$u^* \frac{\partial u^*}{\partial x^*} + v^* \frac{\partial u^*}{\partial y^*} = \frac{\partial \sigma^*_{11}}{\partial x^*} + \frac{\partial \sigma^*_{12}}{\partial y^*}$$</p>
<p>$$u^* \frac{\partial v^*}{\partial x^*} + v^* \frac{\partial v^*}{\partial y^*} = \frac{\partial \sigma^*_{12}}{\partial x^*} + \frac{\partial \sigma^*_{22}}{\partial y^*}$$</p>



  <p>$$\sigma^*_{11} = \frac{\sigma_{11}}{\rho u_\infty^2} = -p^* + \frac{2}{Re} \frac{\partial u^*}{\partial x^*}$$</p>
<p>$$\sigma^*_{22} = \frac{\sigma_{22}}{\rho u_\infty^2} = -p^* + \frac{2}{Re} \frac{\partial v^*}{\partial y^*}$$</p>
<p>$$\sigma^*_{12} = \frac{\sigma_{12}}{\rho u_\infty^2} = \frac{1}{Re} \left( \frac{\partial u^*}{\partial y^*} + \frac{\partial v^*}{\partial x^*} \right)$$</p>


<p>The continuity equation:</p>

<p>$$\frac{\partial u^*}{\partial x^*} + \frac{\partial v^*}{\partial y^*} = 0$$</p>
    
Where:
1. **$\sigma_{11}$ is normal Stress in x-Direction**
2. **$\sigma_{22}$ is normal Stress in y-Direction**
3. **$\sigma_{12}$ and $\sigma_{21}$ are shear Stress**



## Boundary conditions

1. **Top and Bottom Walls:**
    
   <p>$$u = 0 \quad \text{and} \quad v = 0 \quad \text{at the top and bottom walls}$$</p>

2. **Entrance (Inflow):**
    
   <p>$$u = 1 \quad \text{and} \quad v = 0 \quad \text{at the entrance}$$</p>

3. **Exit (Outflow):**
    
   <p>$$p = 0 \quad \text{at the exit}$$</p>

## Loss function

The neural network predicts the x-velocity (\( u \)), the y-velocity (\( v \)), and the pressure (\( p \)) fields. To train the model, we minimize the loss function (\( L \)), which comprises components from both the data and the governing equations.

<p>$$L = L_{\text{DATA}} + L_{\text{PDE}}$$</p>



<p>$$L_{\text{DATA}} = \frac{1}{n} \sum_{i=1}^{n} \left( \left( \hat{u}_i - u_i \right)^2 + \left( \hat{v}_i - v_i \right)^2 + \left( \hat{p}_i - p_i \right)^2 \right)$$</p>

To find  $L_{PDE}$, we differentiate the neural network outputs with respect to position as needed and evaluate the left-hand side (LHS) of the partial differential equations. The PDEs are enforced by minimizing  $L_{PDE}$ to be as close to zero as possible. In this sense,  $L_{PDE}$ acts as an unsupervised loss function since it does not require knowledge of the true velocities or pressure.


<p>$$L_{\text{PDE}} = \frac{1}{n} \left( \left\| f1 \right\|^2 + \left\| f2 \right\|^2 +\left\| f3 \right\|^2+\left\| f4 \right\|^2+ \left\| f5 \right\|^2 + \left\| f6 \right\|^2 \right)$$</p>


 ## Results
 ![loss](https://github.com/user-attachments/assets/cc3d1ad1-5e50-49cc-bba1-69d592196fa8)

 ![Screenshot (639)](https://github.com/user-attachments/assets/a41e1d4f-c704-4340-a48f-36f92db97449)

 ![v](https://github.com/user-attachments/assets/12eb5bd0-df22-499b-a599-170b94f512d8)


 
