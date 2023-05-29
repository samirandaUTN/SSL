1 - Preprocesador

b) Ahorra el trabajo de declarar funciones al programador, La parte 1 del codigo es la libreria expandida

d) Es una declaracion que acepta un argumento como minimo del tipo puntero (*) a un char, el cual no va a poder modificar lo que apunta, el primer parametro es entrada.

c) No expandio ninguna libreria, pero sigue funcionando y estando igual.

2 - Compilacion

a) resultado: hello3.c: In function 'main': hello3.c:5:5: warning: implicit declaration of function 'prontf'; did you mean 'printf'? [-Wimplicit-function-declaration] 5 | prontf("La respuesta es %d\n"); | ^~~~~~ | printf hello3.c:6:5: error: expected declaration or statement at end of input

falta cerrar llaves del main.

c) Lenguaje ensamblador, el codigo se realizo a bajo nivel, con objetivo de ser la entrada para la etapa de ensamblado.En el legnuaje ensamblador que hay una llamada a prontf

d) Al momento de ensamblar generamos un archivo .o el cual permite realizar un analisis byte a byte ya que no es mas que un archivo de bytes.

3 - Vinculacion

a)codigo ejecutado : gcc hello4.o C:/msys64/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/12.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: hello4.o:hello4.c:(.text+0x1f): undefined reference to 'prontf'collect2.exe: error: ld returned 1 exit status

Aca se ve que intento vinvular con la biblioteca estandar y que se intento referenciar a algo que no esta definido que es prontf.

b) codigo ejecutado : gcc hello5.c -o hello5 $ ./hello5.exe La respuesta es 291185584 

c) NO concluye el valor esperado.

4 - Correccion

Si se corre el programa, La respuesta es 42

a) se verifica que funciona bien

Remocion de Prototipo gcc hello7.c -o hello7 hello7.c: In function 'main': hello7.c:4:5: warning: implicit declaration of function 'printf' [-Wimplicit-function-declaration] 4 | printf("La respuesta es %d\n", i); | ^~~~~~ hello7.c:1:1: note: include '<stdio.h>' or provide a declaration of 'printf' +++ |+#include <stdio.h> 1 | hello7.c:4:5: warning: incompatible implicit declaration of built-in function 'printf' [-Wbuiltin-declaration-mismatch] 4 | printf("La respuesta es %d\n", i); | ^~~~~~ hello7.c:4:5: note: include '<stdio.h>' or provide a declaration of 'printf'
Vemos que genera el ejecutable, por lo que se observa que los prototipos no son necesarios, siempre y cuando se utilicen bien las fucniones

Si se corre el programa, La respuesta es 42

b) Funciona por que gcc ya vincula el printf por defecto al utilizarla en nuestro programa.

-i Arrojo warnings de que deberiamos incluir la libreria <stdio.h> -ii un prototipo es una declaracion de un funcion, dando detalle de que parametros va a recibir y de que tipo. Estos parametros los puede generar el programador o directamente llamar a la librerias que ya poseen muchas declaraciones -iii La declaracion implicita sucede cuando no declaramos una funcion, osea no definimos su prototipo -iv la especificacion indica la sintaxis y semantica del lenguaje -v las implementaciones se comportan como un compilador que hace real el lenguaje -vi una funcion built-in es aquella que ya esta incorporado en el compilador -vii Segun el estandar se dice que no existen las declaracion implicitas osea que para que el codigo este bien formado debe haber declaraciones explicitas de funciones aca vemos que no dicen que pasa si NO estan las declaraciones explicitas, ahi es donde se agarra gcc y te permite generar el ejecutable

6)Compilacion Separada: Contratos y Modulos
