# PINN
flow around circular cylinder
## Introduction 
This project provides a numerical solution for the steady-state Navier-Stokes equations for fluid flow over a cylinder at a Reynolds number (Re) of 200 using Physics-Informed Neural Networks (PINN). This innovative approach leverages neural networks to solve partial differential equations (PDEs) and offers a powerful alternative to traditional computational fluid dynamics (CFD) methods.

### Navier-Stokes Equation

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


 
