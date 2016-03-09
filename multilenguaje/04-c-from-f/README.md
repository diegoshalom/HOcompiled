Primero debemos: 
-acomodar los decoradores (definir la funcion con _ en C).
-acomodar memory management (fortran pasa todos punteros, hay que acomodar la funcion en c para que tenga tres argumentos punteros en lugar de dos y un output.

#Para compilar: 
Primero genera los dos objetos, y después los linkea en un ejecutable.
`gcc -c c-sum.c -o c-sum.o`
`gfortran -c f-main.f90 -o f-main_f90.o`
`gfortran c-sum.o f-main_f90. -o ./f-main_f90.e`

#Para ejecutar:
`./f-main_f90.e`

