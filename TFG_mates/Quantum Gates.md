Son las transformaciones cuánticas "legales" (legitimate) y no hay más.
Dado n [[Qubit]]s, una puerta cuantica es una isometría vectorial unitaria (norma del operador es 1).
Como ejemplo, un qubit tenemos:
Identidad:
$I: \ket0 \longrightarrow \ket0, \ket1 \longrightarrow \ket1$
Negación:
$X: \ket0 \longrightarrow \ket1, \ket1 \longrightarrow \ket0$
"Phase Shift", cambio de fase:
$Z: \ket0 \longrightarrow \ket0, \ket1 \longrightarrow -\ket1$
También combinando estás puertas podemos tener otras, por ejemplo: $Y=ZX$. 
Se llaman transformaciones de Pauli a las anteriores 4, $\{I,X,Y,Z\}$, también se pueden notar como $\{\sigma_0,\sigma_1,\sigma_2,\sigma_3\}$ o $\{\sigma_0,\sigma_X,\sigma_Y,\sigma_Z\}$ respectivamente.

Como todas las puertas cuánticas son operaciones lineales, podemos representar el cambio usando una matriz.
Para mas de un bit sigue siendo analogo. Hay que tener en cuenta que los elementos del espacio pueden ser extraños, pero siempre se puede hacer una isometría vectorial entre dicho espacio y un espacio vectorial complejo pertinente en el que operamos con la base usual. (Hay recordar que para cada qubit estamos en una base ortonormal).
El producto tensor de isometría es una isometría, es decir puedo aplicar a dos qubits lo siguiente, al primero Z y al segundo X.
Dos transfomaciones importantes son las siguientes: 
- The Walsh-Hadamard Transformation, $H:\ket 0 \longrightarrow \frac{1}{\sqrt2}(\ket 0 + \ket 1)$, $\ket 1 \longrightarrow \frac{1}{\sqrt2}(\ket 0 - \ket 1)$, aplicando a mas qubits se puede definir recursivamente como, $W_1=H$, $W_n=H\otimes W_{n-1}$.
- The Controlled NOT Gate, $C_{not}$, aplicado a dos qubits es si el primer qubit es un $\ket 1$ niega al segundo. Aplicado a la base: $C_{not}: \ket{00}  \longrightarrow \ket{00}$, $\ket{01}  \longrightarrow \ket{01}$, $\ket{10}  \longrightarrow \ket{11}$, $\ket{11}  \longrightarrow \ket{10}$.

Hay formas gráficas de ver las puertas lógicas y también matriciales. Pondre todas las que vaya conociendo en esta lista: [[quantum_gates_list]]


Usando las isometrías podemos probrar que no podemos clonar qubits. Para empezar clonar un qubit, es dado un $\ket a$ lo queremos copiar en otro qubit, llamemoslo $\ket 0$. Es decir tengo los dos qubits $\ket {a0}$ y quiero acabar con $\ket {aa}$. Parece ser que es una transformación lineal, veamos que no puede ser una transformación lineal unitaria $U$.

Supongamos que tengo dos estados $\ket {a0}$ y $\ket{b0}$, considero $\ket{c}=\frac{1}{\sqrt2}(\ket{a}+\ket{b})$.
Entonces: $\ket{c0} = \ket{c}\otimes\ket{0} = \frac{1}{\sqrt2}(\ket{a}+\ket{b}) \otimes \ket0 = \frac{1}{\sqrt2}(\ket{a}\otimes\ket0 + \ket{b}\otimes\ket0) =\frac{1}{\sqrt2}(\ket{a0} + \ket{b0})$ 
Por linealidad:
$U(\ket{c0})=\frac{1}{\sqrt2}(U(\ket{a0} + U(\ket{b0}))) = \frac{1}{\sqrt2}(\ket{aa} + \ket{bb})$
Y por definición de la U:
$U(\ket{c0}) = \ket{cc} = \frac{1}{2}(\ket{aa} + \ket{ab} + \ket{ba} + \ket{bb})$
Como ambas cosas son incompatibles entre si entonces no puedo copiar un estado desconocido $\ket{c}$.
Lo que si se sabe que es posible es copiar estados conocidos (porque se cual es y es solo meterlo).

Dos usos de estas transformaciones son el [[Teleportation]] y el [[Dense Coding]].

#### Bibliografía
- [[Resumen.pdf]]
- [[Quantum_Computing_Explained_David_McMahon.pdf]]