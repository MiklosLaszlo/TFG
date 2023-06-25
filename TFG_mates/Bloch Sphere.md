Se basa en la siguiente idea, un qubit es un vector de norma 1 en un espacio complejo 2 dimensional. Entonces tambíen lo puedo ver como un vector de norma 1 en una espacio real 4 dimensional, es decir el qubit es un elemento $S^3$ y podemos identificar $S^3$ con la bola unidad de $\mathbb{R}^3$. Pero si restringimos que unos de los vectores de la base solo tenga coeficientes reales entonces obtenemos $S^2$.Veamos la definición.

Sea $\ket{\psi}$ un qubit con coeficiente real en $\ket{0}$ en la base usual $\{\ket{0},\ket{1}\}$. Como $<\psi|\psi>=1$ puedo escribir:
$$\ket{\psi}=cos(\dfrac{\theta}{2})\ket{0}+e^{i\phi}sen{\dfrac{\theta}{2}}\ket{1}$$
Para algún $\theta$ en $[0,\pi]$ y algún $\phi$ en $[0,2\pi[$. Además está representación es única.
Ahora interpretando $\theta$, $\psi$ como coordenadas de colatitud y longitud tenemos el vector
$$a=(sin(\theta)cos(\phi),sin(\theta)sin(\phi),cos(\theta))$$
a es un vector en la esfera de $\mathbb{R}^{3}$.

Ahora usando el [[Operador de Densidad]] puedo obtener un vector que ya este en la propia bola de $\mathbb{R}^3$. 

Cuando estamos en un espacio 2-dimensional podemos usar $\rho$ para calcular el vector de Bloch (en la esfera de Bloch, [[Bloch Sphere]]).
Usando los [[Operadores de Pauli]], puedo descomponer $\rho$ (mirandolo como matriz) definiendo: $\overrightarrow\sigma = \sigma_x \hat{x} + \sigma_y \hat{y} +\sigma_z \hat{z}$
$$\rho=\dfrac{1}{2}(I-\overrightarrow{S}\overrightarrow{\sigma})$$
Donde $\overrightarrow{S}$ se le llama vector de Bloch. $\overrightarrow{S}$ verifica que su norma es menor igual a 1, siendo 1 solamente si $\psi$ es un qubit en estado puro. Los componentes del vector de Bloch son:
$$\overrightarrow{S}=S_x\hat{x}+S_y\hat{y}+S_z\hat{z}=<X>\hat{x}+<Y>\hat{y}+<Z>\hat{z}=Tr(\rho X)\hat{x}+Tr(\rho Y)\hat{y}+Tr(\rho Z)\hat{z}$$
Usando $\rho$ para calcular el valor medio de los operadores.