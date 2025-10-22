## 1. Derivation of Euler's equation
We will derive Euler's equations for an adiabatic and non-viscous fluid with a density $\rho(\mathbf{r},t)$ and velocity vector field $\mathbf{v}(\textbf{r},t)$ in a uniform gravitational field $\mathbf{g}$. We consider a fluid parcel of dimensions $dx$, $dy$ and $dz$ located at $\mathbf{r}=(x,y,z)$ in a Cartesian coordinate system. 
![fig1](./img/diagram-1.png)
Due to density fluctuations inside the fluid a pressure field $p(\mathbf{r},t)$ is present. The force on the fluid parcel depends on the variation of that pressure and the gravitational field present. In the $x$ direction the force from the pressure is 
$$
dF_x = (-p(x+dx,y,z)+p(x,y,z))dydz=\frac{(-p(x+dx,y,z)+p(x,y,z))}{dx}dxdydz=-\frac{\partial}{\partial x} pdV
$$
Similarly
$$
\begin{align}
dF_y = -\frac{\partial}{\partial y} pdV\\
dF_z = -\frac{\partial}{\partial z} pdV
\end{align}
$$
Including the gravitational force, the total on the parcel is
$$d\mathbf{F}=(-\nabla p+\rho\mathbf{g})dV \tag{1.1}$$
![fig2](./img/diagram-2.png)
Using Newton's second law we get
$$
\begin{align}
dm\frac{d\mathbf{v}}{dt}=d\mathbf{F}  \\ \\ \implies
\frac{d\mathbf{v}}{dt}=-\frac{1}{\rho}\nabla p+\mathbf{g} \tag{1.2},
\end{align}
$$
This is the first of Euler's equations. We can find the second (Landau vol 6) by considering a mass $M$ in the fluid in some volume $V$. The connection between them and the density is 
$$
M=\int_V \rho(\mathbf{r},t)dV \tag{1.3}
$$
Differentiating $(1.3)$ with respect to time and using the fact that the differential mass flux is equal to $\rho \mathbf{v} \cdot d\mathbf{A}$ , we have
$$
\frac{\partial M}{\partial t}=\frac{\partial}{\partial t}\int_V \rho dV=-\oint_S\rho \mathbf{v}\cdot d\mathbf{A} \tag{1.4}
$$
with $S$ being the surface of the considered volume and $d\mathbf{A}$ the normal vector to that surface. Using Gauss's theorem we have
$$
-\oint_S\rho \mathbf{v}\cdot d\mathbf{A} = \int_V\nabla (\rho \mathbf{v}) dV\tag{1.5}
$$
Finally from $(1.4)$ and $(1.5)$ we have
$$
\begin{align}
\int_V \frac{\partial \rho}{\partial t}+\nabla (\rho \mathbf{v}) dV = 0 \\
\implies \frac{\partial \rho}{\partial t}+\nabla (\rho \mathbf{v}) = 0 \tag{1.6}
\end{align}
$$
Thus $(1.2)$ and $(1.6)$ give us Euler's equations:
$$\begin{align} 
\frac{d\mathbf{v}}{dt}=-\frac{1}{\rho}\nabla p+\mathbf{g} \\ 
\tag{1.7} \\
\frac{\partial \rho}{\partial t}+\nabla (\rho \mathbf{v}) = 0
\end{align}
$$
We can simplify them even more for an incompressible fluid - $\rho(\mathbf{r},t)=const$ :
$$\begin{align} 
\frac{d\mathbf{v}}{dt} =-\frac{1}{\rho}\nabla p+\mathbf{g} \\ 
\tag{1.8} \\
\nabla (\mathbf{v}) = 0
\end{align}
$$
We will be using an adiabatic, non-viscous and incompressible fluid for our model of ship waves, which is described by $(1.8)$. One important clarification is to note that $\frac{d\mathbf{v}}{dt}$ is not equal to $\frac{\partial \mathbf{v}}{\partial t}$, as equation $(1.2)$ was derived by following the velocity of a single fluid parcel, and not the velocity field at that point. (<span style="color:red"> по-добро обяснение? </span>)
![fig3](./img/diagram-3.png)
Let us now create a formal connection between the two derivatives. We have
$$
\begin{align}
\frac{d\mathbf{v}}{dt} = \frac{\mathbf{v}(\mathbf{r}+\mathbf{v}\delta t, t+\delta t)-\mathbf{v}(\mathbf{r}, t)}{\delta t} \\
\implies \frac{d\mathbf{v}}{dt} = \frac{\mathbf{v}(x+v_x \delta t, y+v_y \delta t, z+v_z \delta t, t+\delta t)-\mathbf{v}(x, y, z, t)}{\delta t} \tag{1.9}
\end{align} 
$$
Using
$$
f(x_1+\Delta x_1,x_2+\Delta x_2, \cdots , x_n+\Delta x_n )=\frac{\partial f}{\partial x_1}\Delta x_1+\frac{\partial f}{\partial x_2}\Delta x_2+\cdots+\frac{\partial f}{\partial x_n}\Delta x_n
$$
with equation $(1.9)$ we get
$$
\begin{align}
\frac{d\mathbf{v}}{dt} = \frac{\partial \mathbf{v}}{\partial t} + v_x \frac{\partial v_x}{\partial x}+ v_y \frac{\partial v_y}{\partial y}+ v_z \frac{\partial v_z}{\partial z} \\
\frac{d\mathbf{v}}{dt}=\frac{\partial \mathbf{v}}{\partial t} + (\mathbf{v}\cdot\nabla)\mathbf{v} \tag{1.10}
\end{align}
$$
Equation $(1.10)$ can also be shown to be 
$$\frac{d\mathbf{v}}{dt}=\frac{\partial \mathbf{v}}{\partial t} + \frac{1}{2}\nabla v^2-\mathbf{v}\times(\nabla\times\mathbf{v}) \tag{1.11} $$
Finally, $(1.11)$ and $(1.8)$ give us
$$\begin{align} 
\frac{\partial \mathbf{v}}{\partial t} + \frac{1}{2}\nabla v^2-\mathbf{v}\times(\nabla\times\mathbf{v}) =-\frac{1}{\rho}\nabla p+\mathbf{g} \\ 
\tag{1.12} \\
\nabla \cdot(\mathbf{v}) = 0
\end{align}
$$
For potential flow, which is to say in this case irrotational ($\nabla\times\mathbf{v}=0$) flow, and for slow speeds of the fluid, we have
$$\begin{align} 
\frac{\partial \mathbf{v}}{\partial t} =-\frac{1}{\rho}\nabla p+\mathbf{g} \\ 
\tag{1.13} \\
\nabla \cdot(\mathbf{v}) = 0
\end{align}$$
which is the version of the equations we are using for our model.
We define $\nabla \Phi=-\mathbf{v}$ as the velocity potential. With it we rewrite the first equation from (1.13) as
$$ -\nabla \frac{\partial \Phi}{\partial t} =-\frac{1}{\rho}\nabla p+\mathbf{g} \tag{1.14}$$
Take $\mathbf{g}$ to be in the $z$ direction - $\mathbf{g}=(0,0,-gz)$. From (14) we get
$$
\begin{align} 
\nabla(\frac{1}{\rho} p+(gz)-\frac{\partial \Phi}{\partial t}) =0 \\
\implies \frac{1}{\rho} p+(gz)-\frac{\partial \Phi}{\partial t}=f(t) \tag{1.15}
\end{align} 
$$
where $f(t)$ is an arbitrary function that depends only on time. We can see that this function is unnecessary by defining 
$$
\frac{\partial \tilde\Phi}{\partial t} = \frac{\partial \Phi}{\partial t} +f
$$
which, when we plug in to $(1.15)$, gives us
$$
\frac{1}{\rho} p+(gz)-\frac{\partial \tilde\Phi}{\partial t}=0 \tag{1.16}
$$
But since $-\nabla\Phi=-\nabla\tilde\Phi=\mathbf{v}$ it doesn't matter which potential we use, so we can utilize $\tilde\Phi \equiv \Phi$ and formulate the potential formulation of Euler's equations by using $(1.16)$ and $(1.13)$:
$$\begin{align} 
\frac{1}{\rho} p+gz-\frac{\partial \Phi}{\partial t}=0 \\ 
\tag{1.17} \\
\nabla^2 \Phi = 0
\end{align}$$
## 2. Fundamental equations of ship waves
We can use equations $(1.17)$ to derive the evolution of the surface of the water, which we take as an adiabatic, non-viscous, incompressible and irrotational fluid. We assume air pressure $p_0$ is constant. At the boundary between air and water defined as $z=\zeta(x,y,t)$ we have 
$$
\left(\frac{p}{\rho}+gz-\frac{\partial \Phi}{\partial t}\right)_{z=\zeta(x,y,t)}=0 \tag{2.1}
$$
We will now find how the boundary evolves with time:
$$
\begin{align} 
\frac{p_0}{\rho}+g\zeta-\frac{\partial \Phi}{\partial t}=0 \\
\zeta=\frac{1}{g}\frac{\partial \Phi(x,y,z=\zeta(x,y,t),t)}{\partial t}-\frac{p_0}{g\rho} \\
v_z \approx \frac{\partial \zeta}{\partial t} = \frac{1}{g}\frac{\partial^2 \Phi}{\partial t^2}+\frac{1}{g}\frac{\partial^2 \Phi}{\partial t \partial z}\frac{\partial \zeta}{\partial t} \tag{2.2}

\end{align}
$$
at $z=\zeta$. By using the definition of the velocity potential we have
$$\frac{\partial}{\partial t} (\frac{\partial \Phi}{\partial z}) = -\frac{\partial v_z}{\partial t}$$ which then gives us in $(2.2)$
$$
\begin{align}
\frac{\partial \zeta}{\partial t} = \frac{1}{g}\frac{\partial^2 \Phi}{\partial t^2}-\frac{1}{g} v_z\frac{\partial v_z}{\partial t}\\
\implies \frac{\partial \zeta}{\partial t} = \frac{1}{g}\frac{\partial^2 \Phi}{\partial t^2}-\frac{1}{2g} \frac{\partial v_z^2}{\partial t}
\end{align}
$$
But since we assume small velocities of the fluid flow we can write
$$
\frac{\partial \zeta}{\partial t} = \frac{1}{g}\frac{\partial^2 \Phi}{\partial t^2} \tag{2.3}
$$
as our final equation for the boundary. By again employing the fact that $v_z=-\frac{\partial \Phi}{\partial z}$ we get
$$
\left.-\frac{\partial \Phi}{\partial z}\right|_{z=\zeta} = \left. \frac{1}{g}\frac{\partial^2 \Phi}{\partial t^2}\right|_{z=\zeta}
$$
From here we write out the complete set of evolutionary equations for surface waves by employing the above and Euler's equations:
$$
\begin{align}
\left(\frac{\partial \Phi}{\partial z} +\frac{1}{g}\frac{\partial^2 \Phi}{\partial t^2}\right)_{z=\zeta}=0 \\ \tag{2.4}
\\
\nabla^2 \Phi = 0
\end{align}
$$
## 3. Old Ship Model

## 4. Improved Ship Model
While a ship moves it displaces water in the back and in the front of itself, meaning just modeling it as a single Dirac-delta function is not enough. We will model this by employing two Dirac delta functions that represent the volume of water that has been pushed aside by the ship and the volume of water that has taken the new volume behind the ship. We shall first prove a few fundamental ideas about the shape of the ship.


