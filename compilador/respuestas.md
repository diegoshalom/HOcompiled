#1. Escriban qu� esperan de cada uno de los pasos
##Pre-procesador
Reemplaza `#include` y `#define` por los headers y valores definidos.

##Compilaci�n I
Traduce el c�digo C en c�digo Assembler (aun legible por humanos)

##Compilaci�n II
Traduce el c�digo Assembler en lenguaje de m�quina (ilegible por humanos). Lo miramos con `nm`, y podemos ver los s�mbolos, nos muestra descriptores.

##Linkeo
Linkea con librer�as u otros objetos con definiciones de las funciones indefinidas (U).

#2. �Qu� agreg� el preprocesador?
En este caso, peg� el `calculator.h` y `stdio.h`, agregando n�meros de l�nea para tener registro.

#3. Identificar en la rutina de assembler las funciones
Pone cosas en lugares de memoria con `movl`, y luego llama a las funciones con `call`

#4. Explicar qu� quieren decir los s�mbolos que se crean en el objeto
Son lo objetos visibles desde afuera:
00000000003c T add_numbers
000000000000 T main
             U printf

El descriptor T signfica "texto", e incluye las funciones. U es indefinido, ser� necesario linkeo para tener su definici�n.

#5. �En qu� se diferencian los s�mbolos del objeto y del ejecutable?
Al principio, creeimos que no deber�a haber U(ndefined), pero printf est� indefinida, porque usa una ibrer�a din�mica.
El ejecutable tiene muchos m�s s�mbolos, seguaramente definidos adentro de `stdio.h`, o parte general de C.

