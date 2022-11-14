[[ERP particula]], [[Quantum Gates]]
Usando un par ERP (particula ERP) (usaremos el clásico), transmitimos el valor de información de dos bits clásicos. Supongamos dos personas Alice y Bob.
Forma:
- Le damos un par del ERP a Alice y otro a Bob, cada uno tiene un qubit pero ambos qubits están entrelazados entre si.
- Alice recibe dos bits, dependiendo de su codificación aplica a su qubit la transformación $\{I,X,Y,Z\}$ dependiendo de si recibe $\{00,01,10,11\}$. Y envía su qubit a Bob. Como par de qubits se ha aplicado la correspondiente transformación $T$ al qubit de Alice y la identidad a la particula de Bob. Es decir a la particula ERP se ha aplicado la transformacion $T \otimes I$.
	![[Alice_apply_transofrmation_DenseCoding.png]]
- Bob aplica $C_{not}$ al par ERP, con esto el par deja de estar entrelazada, así que Bob mide el segundo qubit dejandole dos opciones (ver tabla del resumen). Despues a la medición le aplica $H$ al primer qubit (recordemos que la medición destruye), mide y puede saber que dos bits tenía Alice.
![[Bob_apply_Cnot_DenseCoding.png]]
![[Bob_apply_H_DenseCoding.png]]
En resumen, intervienen dos qubits entrelazados. Pero solo se envía uno de ellos.
EL entrelazamiento es lo que permite hacer esto.

#### Bibliografía
- [[Resumen.pdf]]