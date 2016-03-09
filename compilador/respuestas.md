#1. Escriban qué esperan de cada uno de los pasos
##Pre-procesador
Reemplaza `#include` y `#define` por los headers y valores definidos.

##Compilación I
Traduce el código C en código Assembler (aun legible por humanos)

##Compilación II
Traduce el código Assembler en lenguaje de máquina (ilegible por humanos). Lo miramos con `nm`, y podemos ver los símbolos, nos muestra descriptores.

##Linkeo
Linkea con librerías u otros objetos con definiciones de las funciones indefinidas (U).

#2. ¿Qué agregó el preprocesador?
En este caso, pegó el `calculator.h` y `stdio.h`, agregando números de línea para tener registro.

#3. Identificar en la rutina de assembler las funciones
Pone cosas en lugares de memoria con `movl`, y luego llama a las funciones con `call`

#4. Explicar qué quieren decir los símbolos que se crean en el objeto
Son lo objetos visibles desde afuera:
00000000003c T add_numbers
000000000000 T main
             U printf

El descriptor T signfica "texto", e incluye las funciones. U es indefinido, será necesario linkeo para tener su definición.

#5. ¿En qué se diferencian los símbolos del objeto y del ejecutable?
Al principio, creeimos que no debería haber U(ndefined), pero printf está indefinida, porque usa una ibrería dinámica.
El ejecutable tiene muchos más símbolos, seguaramente definidos adentro de `stdio.h`, o parte general de C.

