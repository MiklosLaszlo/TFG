[[Quantum Gates]],[[ERP particula]]
Se sabe que no podemos clonar qubits en qubits. Pero la teleportación dice que usando 2 bits puedo transimitir el estado cuántico y reconstruirlo en otro lugar. Esto no es la clonación clásica, se verá que destruimos el estado y una vez destruido somos capaces de reconstruirlo.
(Se ha podido hacer experimentalmente).
Dos personas Alice y Bob, poseen cado uno un qubit de un par ERP $\phi = \frac{1}{\sqrt2}(\ket {00} + \ket {11})$
Forma:
- Alice tiene un qubit. $\psi_0$, en un estado desconocido $\psi_0 = a\ket 0 + b \ket1$ (con $|a|^2 + |b|^2=1$). 
- Teniendo en cuenta el par ERP, tenemos $\psi_0 \otimes \phi = \frac{1}{\sqrt2}(a\ket{000} + a\ket{011} + b\ket{100} + b\ket{111})$.
- Alice controla los dos primeros qubits de este estado y Bob el último (de momento). Alice ahora aplica $C_{not}\otimes I$, y luego $H \otimes I \otimes I$ {$(H \otimes I \otimes I) \circ (C_{not}\otimes I)$} a este estado.
$(H \otimes I \otimes I) \circ (C_{not}\otimes I) (\psi_0 \otimes \phi) = \frac{1}{2}(\ket{00}(a\ket0 + b\ket1)+\ket{01}(a\ket1 + b\ket0)+\ket{10}(a\ket0 - b\ket1)+\ket{11}(a\ket1 - b\ket0))$
- Alice mide los dos primeros qubits del estado transformado, que puede ser $\{\ket{00},\ket{01},\ket{10},\ket{11}\}$ con igual probabilidad. Dependiendo de la medición el qubit de Bob se ha projectado a $\{a\ket0 + b\ket1,a\ket1 + b\ket0,a\ket0 - b\ket1,a\ket1 - b\ket0\}$ respectivamente. Alice envía su medición a Bob con dos bits clásicos (notemos que hemos acabamos de destruir el estado cuántico)
- Bob recibe los bits de Alice, y ya sabe en que estado se encuentra su qubit. Por tanto dependiendo de si recibe $\{00,01,10,11\}$ aplica a su qubit $\{I,X,Z,Y\}$ y con ello Bob obtiene otra vez el estado $\psi_0$

Notemos que hemos usado otra vez que dos qubits esten entrelazadas. Por otro lado para enviar el estado de su qubit Alice a tenido que destruirlo.

#### Bibliografía
- [[Resumen.pdf]]