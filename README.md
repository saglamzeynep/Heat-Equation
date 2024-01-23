# Heat Equation Application on Physics-Informed Neural Networks
The heat equation is a partial differential equation that describes the temperature of a substance as a function that varies with time. This equation, solved under certain initial and boundary conditions, describes how the temperature distribution of a substance changes over time. This is a classic example of the diffusion equation and plays a crucial role in understanding the principles governing heat transfer and thermal diffusion. 

<p align="center">
  <img width="460" height="300" src="https://github.com/saglamzeynep/Heat-Equation/assets/152716329/7bb7fc3a-428e-488f-87c0-9814a5bf6cce">
</p>

The heat equation mathematically represents how the temperature at each point in an environment evolves as a function of both time and spatial coordinates. This equation finds wide applications in various disciplines, including physics, mathematics and engineering. Study of the heat equation contributes significantly to our understanding of heat conduction, diffusion and thermal properties of materials. The heat equation is represented as ;  
  
$$\frac{\partial T}{\partial t}-\alpha \frac{\partial ^2 T}{\partial x^2}=0$$
  
Here T represents the heat equation, t represents time, and x represents location. The $\alpha$ coefficient is called part conductivity and is obtained by multiplying specific heat capacity and part density. It is a different coefficient for each item.  

While making this application, steady state was taken into consideration for the heat function. The steady state can be thought of as a snapshot of the temperature equation. Therefore, it does not depend on time and the heat equation takes the form;
$$\frac{\partial u_{ss}}{\partial t}=0 ,\quad\quad \frac{\partial^2 u_{ss}=0}{\partial x^2}$$

Here $u_{ss}$ represents steady state of the heat function. Then the boundry conditions;  
  
$$ u_{ss}(x=0)=u_{0} \quad \quad u_{ss}(x=L)=u_{L}$$

Considering all these conditions, the physics equation we will apply is:  

$$ u_{ss}=(u_L-u_0)\frac{x}{L}+u_0$$


After determining the equation required for the program, the data set must be determined. Instead of using a ready-made dataset, the dataset was created with the desired boundary conditions (T(-1,y)=100 $^{\circ}$C, T(1,y)=0 $^{\circ}$C ,T(x,-1)=300$^{\circ}$C , T(x,1)=0$^{\circ}$C) using the Latin Hypercube Sampling method. These conditions can be set as desired within the code.  

With the dataset ready, the model that would form the neural network was created, and a function called DNN-builder was created for this. The model has been trained and tested. As a result, the graphic outputs:

<p align="center">
<img width="700" height="300" src="https://github.com/saglamzeynep/Heat-Equation/assets/152716329/b4b3c145-1c9c-41b4-9a2a-19e5ed5f59dc">
</p>

While performing this application, mean squared error(MSE) was used as the loss function. MSE is a performance measure used in regression problems and measures how close a model makes predictions to true values. The advantages of MSE include maintaining the balance between negative and positive errors by squaring and summing each difference. However, due to squaring, large errors may have a greater impact. This means sensitivity to outliers. The learning process can be examined through the loss function as:


<p align="center">
<img width="375" height="300" src="https://github.com/saglamzeynep/Heat-Equation/assets/152716329/149092be-a93d-4244-a0fe-9ef73c2bdb06">

</p>
