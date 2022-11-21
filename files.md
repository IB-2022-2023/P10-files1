# Práctica 09. Ficheros. Visual Studio Code.

# Factor de ponderación: 9

### Objetivos
Los objetivos de esta práctica son que el alumnado:
* Sea capaz de resolver problemas sencillos en C++ usando todos los conocimientos adquiridos hasta ahora, 
  y en particular utilizando funciones y objetos de las clases `std::string`, `std::array`, `std::vector`
* Diseñe, desarrolle y utilice funciones en sus programas haciendo que sus programas sean modulares
* Configure y practique el uso de Visual Studio Code (VSC) para editar ficheros de forma remota en su VM

### Rúbrica de evaluacion de esta práctica
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva) que se tendrán en cuenta a la hora de evaluar esta práctica.
Se comprobará que el alumnado:
* Conoce los conceptos expuestos en el material de referencia de esta práctica.
* Ha realizado todos los ejercicios propuestos en este enunciado
* Es capaz de escribir programas simples en C++ que resuelvan problemas de complejidad similar a los que se proponen en este documento
* Sea capaz de utilizar VSC para editar y compilar programas de forma remota en su Máquina Virtual
* Conoce la plataforma Exercism y es capaz de descargar y realizar problemas sencillos interaccionando con ella.
* Es capaz de escribir un fichero `CMakeLists.txt` para automatizar el proceso de compilación de sus programas con `cmake` y `make`
* Ha automatizado la compilación de sus programas usando un fichero `Makefile` para cada uno de los programas que desarrolle 
* Hace que sus programas se estructuren en torno a diferentes funciones (sean modulares)
* Todos sus programas se estructuran en directorios diferentes para cada "proyecto" haciendo que cada uno de
  ellos contenga un fichero `CMakeLists.txt` con la configuración de despliegue del proyecto.
* Utiliza en todos sus programas comentarios adecuados en el formato requerido por
[Doxygen](https://www.doxygen.nl/index.html)
* Acredita que todas las prácticas realizadas hasta la fecha se encuentran alojadas en repositorios privados de 
[GitHub](https://github.com/).
* Acredita que es capaz de subir programas a la plataforma 
[Jutge](https://jutge.org/)
para su evaluación
* Ha incluido un comentario prólogo en todos los ficheros (`*.cc`, `*.h`) de sus ejercicios
* Que todos los programas que desarrolla, antes de su ejecución imprimen en pantalla un mensaje indicando la 
  finalidad del programa así como la información que precisará del usuario para su correcta ejecución.
* Hace que todos los programas que se presentan para su evaluación cumplan con los estándares definidos en la
[Guía de estilo de Google para C++](https://google.github.io/styleguide/cppguide.html) 
* Utiliza siempre identificadores significativos en su programa (para constantes, variables, etc.) y
  no utiliza nunca identificadores de una única letra, tal vez con la excepción de las variables que utilice para iterar en un bucle.
* Acredita que es capaz de editar ficheros remotos en su VM usando vi
* Ha realizado todos sus ejercicios en la máquina virtual Ubuntu de la asignatura.
* Demuestra que es capaz de ejecutar comandos Linux en su VM

#### Visual Studio Code
Un 
[IDE](https://en.wikipedia.org/wiki/Integrated_development_environment)
(*Integrated development environment*, entorno integrado de desarrollo) es un programa que proporciona
diversos servicios a una programadora para facilitarle la tarea del desarrollo de programas.
Los servicios más comunes que proporciona un IDE son un editor de código fuente (hasta ahora se ha usado vi),
un compilador (se seguirá usando g++), herramientas de construcción automáticas (hasta ahora se ha utilizado 
`make`) y un depurador. 
La mayoría de los IDE tienen auto-completado inteligente de código (IntelliSense). 
Los IDE presentan un único programa en el que se lleva a cabo todo el desarrollo. 
Generalmente, este programa (IDE) suele ofrecer muchas funcionalidades para la creación, modificación, compilación, implementación y depuración de programas.
Algunos IDE están orientados específicamente a un determinado lenguaje de programación, mientras que otros  se
pueden utilizar con diferentes lenguajes.

[Visual Studio Code](https://en.wikipedia.org/wiki/Visual_Studio_Code) 
(VSC) es un IDE desarrollado por Microsoft 
para Windows, Linux, macOS y Web. 
Incluye soporte para la depuración, control integrado de Git, resaltado de sintaxis, finalización inteligente de código, 
fragmentos y 
[refactorización](https://es.wikipedia.org/wiki/Refactorizaci%C3%B3n)
(modificación del código fuente sin cambiar su comportamiento).
El IDE es personalizable, por lo que sus usuarios pueden cambiar el tema del editor, los atajos de teclado y las preferencias. 
Es gratuito y de código abierto y es 
[uno de los IDEs más utilizados](https://www.geeksforgeeks.org/10-best-ide-for-web-developers-in-2022/)
en la actualidad.
En *Informática Básica* se adoptará VSC como IDE, y se utilizará en la evaluación de las prácticas
restantes de la asignatura.

Para instalar VSC en su instalación Linux particular (no en su máquina virtual, sino en la instalación Linux
desde la que suele trabajar) siga
[estas instrucciones](https://code.visualstudio.com/docs/setup/linux)
descargando el paquete `.deb`. 
Una vez haya descargado el paquete, instálelo en su máquina ejecutando:
```
sudo apt install code_1.73.1-1667967334_amd64.deb
```
Una vez haya instalado el paquete, compruebe que puede iniciar VSC en su máquina ejecutando en una terminal:
```
code .
```
En el comando anterior el punto indica que desea Ud. editar ficheros en el directorio actual (`.`).
Una vez arranque el programa, salga del mismo utilizando el menú (*File* -> *Exit*).

Siga a continuación las instrucciones de la página
[Remote Development using SSH](https://code.visualstudio.com/docs/remote/ssh)
para configurar la edición remota usando VSC.

De los tres pasos que se indican en la página anterior:
1. Instalar un cliente OpenSSH
2. Instalar Visual Studio Code
3. Instalar el paquete correspondiente a la extensión *Remote Development extension pack* 

Solo tiene que realizar el tercero, puesto que ya se tiene `ssh` tanto en la máquina virtual como en su máquina de
trabajo y la instalación de VSC ya se ha realizado usando `apt install`.

Si sigue el enlace
[Remote Development extension pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
le llevará a una página en la que le indica el comando que ha de teclear en VSC (`Ctrl+P`) para instalar la
extensión.

Vuelva de nuevo a la página 
[Remote Development using SSH](https://code.visualstudio.com/docs/remote/ssh)
y en el apartado *SSH host setup* realice las instrucciones del paso 3 (opcional). 
Para ello ha de acceder a la página 
[Remote Development Tips and Tricks](https://code.visualstudio.com/docs/remote/troubleshooting#_improving-security-on-multi-user-servers)
y seguir las instrucciones correspondientes a *Quick start: Using SSH keys*.

Ejecute para ello (sustituyendo la dirección IP por la de su VM):
```
$ ssh-keygen -t rsa -b 4096
$ export USER_AT_HOST=usuario@10.6.131.106
$ export PUBKEYPATH="$HOME/.ssh/id_rsa.pub"
$ ssh-copy-id -i "$PUBKEYPATH" "$USER_AT_HOST"
```
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/master/img/VSC-connect-to-host.png)
muestra el paso 2 del apartado "Connect to a remote host" de esas instrucciones mientras que
[esta otra](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/master/img/VSC-password.png)
muestra la ventana de autentificación de VSC para darle acceso a la máquina virtual.  
[Este vídeo](https://youtu.be/pAUfwae-eWg) ilustra cómo configurar la edición remota de ficheros alojados en máquinas IaaS-ULL usando VSC.

Una vez instalado en su máquina local, ejecute el Microsoft Visual Studio Code (VSC) y siga 
[estas instrucciones](https://code.visualstudio.com/docs/remote/ssh)
para configurar la edición remota de ficheros alojados en su máquina virtual.  

### Material de estudio complementario
Estudie todo lo que se indica en el epígrafe 
[Functions](https://google.github.io/styleguide/cppguide.html#Functions)
de la Guía de Estilo de Google y ponga en práctica todo lo que en ella se propone.
Es normal si encuentra en ese epígrafe algún contenido que aún no ha estudiado: no se preocupe. 
Centre su atención en aquellos aspectos que ya conozca, para consolidarlos.

Estudie del
[tutorial de referencia](https://www.learncpp.com/)
en la asignatura los siguientes apartados:
* [7.18 — Introduction to random number generation](https://www.learncpp.com/cpp-tutorial/introduction-to-random-number-generation/)
* [4.17 — Introduction to std::string](https://www.learncpp.com/cpp-tutorial/introduction-to-stdstring/)
* [4.18 — Introduction to std::string_view](https://www.learncpp.com/cpp-tutorial/introduction-to-stdstring_view/)
* [11.16 — An introduction to std::array](https://www.learncpp.com/cpp-tutorial/an-introduction-to-stdarray/)
* [11.17 — An introduction to std::vector](https://www.learncpp.com/cpp-tutorial/an-introduction-to-stdvector/)
* [11.13 — For-each loops](https://www.learncpp.com/cpp-tutorial/for-each-loops/)
* Estudie en 
[cppreference](https://en.cppreference.com/w/cpp/numeric/random/uniform_real_distribution)
cómo utilizar una distribución uniforme con números reales (en punto flotante).

### Ejercicios
* Al realizar los ejercicios cree dentro de su repositorio de esta práctica un directorio diferente
para cada uno de los ejercicios.
Asigne a cada uno de esos directorios nombres significativos. 
* Automatice la compilación del programa correspondiente a cada ejercicio con un fichero `Makefile`
independiente para cada programa e inclúyalo en el correspondiente directorio.
* Haga que todos los programas tomen su entrada por la línea de comandos y en caso de que se ejecuten sin
  pasarles el número adecuado de parámetros impriman en pantalla un mensaje indicando el modo correcto de
  ejecutar el programa.
* El código de cada uno de los programas deberá organizarse de forma modular, es decir haciendo uso de funciones 
* Cada función deberá realizar una única tarea y hacerlo correctamente 
* El identificador de una función debe reflejar claramente lo que la función hace 

* Exercism ??? XXXX

3. Desarrolle un programa que incluya una función cuyo nombre sea *ReduceSum* que tome como parámetro un
vector de números en punto flotante y devuelva como resultado la suma de todos los valores almacenados en el
vector.

Utilice la función *GenerateVector()* para generar vectores y probar el funcionamiento de *ReduceSum*.

```
Public test cases
Input           Output
1.0 1.0 1.0      3.0
1 2 3 4 5 6     21.0
0 0 0 0 1 0 1    2.0
```
