# Guía rápida para el uso del servidor LaBTAA

En su primer contacto con el servidor este le permitirá crear un nuevo password, este se debe cambiar mediante:


## El primer contacto

Se le proveera de un nombre de usuario que de manera convencional llamaremos *user*

Los comandos son para ser utilizados desde la terminal, no desde Jupyter, cuando se va a configurar la coniección a Jupyter se le indicará en el texto.

El servidor tiene como dirección ip: *__10.5.7.10__*, de tal manera que su usuario debera introducirlo en una terminal con ssh (asumiendo que tiene instalado ssh en su __Computadora Local__), si no lo tiene instalado, lo puede hacer mediante


_**nota: Elimine el símbolo "#" que se encuentra al inicio del comando para que la terminal lo reconozca, recuerde que todo lo que vaya posterior al un símbolo de "#" será ignorado**_


```bash
#apt-get install openssh-server openssh-client openssh #ejecute si requiere instalar
```

Una vez instalado ssh, ud puede conectarse al servidor mediante el usuario y pass asignado mediante:


```bash
ssh user@10.5.7.10 #No corra este comando en Jupyter
```

El comando anterio es para conectarse al sevidor desde la terminal

_**nota: Elimine el símbolo "#" que se encuentra al inicio del comando para que la terminal lo reconozca, recuerde que todo lo que vaya posterior al un símbolo de "#" será ignorado**_ 


```bash
#passwd #sólo ejecute si es su primera vez con el servidor
```

Al entrar al servidor ud podrá ver algo parecido:

![](001_000.jpg)

__Nota: Todo lo que realizará a continuación sera con su WSL conectado por ssh al servidor:__

El servidor trae instalado Jupyter notebook y lab nativo, pero la instalación de anaconda se instala en el home de cada ususario, entonces tendrá que hacer su propia instalación en su /home del servidor.


1. Primero en su explorador de internet de su maquina local, vaya a la pagina de [anaconda](https://www.anaconda.com/products/distribution#Downloads) y busque la ultima versión:

2. El servidor es linux, entonces la versión a instalar es linux, a continuación haga click derecho sobre el ícono __64-Bit (x86) Installer (737 MB)__ y de copiar dirección de enlace y en su terminal del servidor ponga:


```bash
wget https://www.anaconda.com/products/distribution#Downloads
```

3. Introduzca el comando para ver si se descargo su archivo:


```bash
ls
```

4. Es probable que encuentre una archivo como __Anaconda3-2022.10-Linux-x86_64.sh__ entre sus archivos, entonces ejecute:


```bash
sh Anaconda3-2022.10-Linux-x86_64.sh
```

5. Siga las instrucciones del instalador, este lo guiará:

- Acepte la licencia escribiendo "*yes*" cuando se lo solicite.

- Precione enter o intro cuando le pregunte si quiere cguardar en su /home/user

- Escriba "*yes*" al final de la instalación cuando le pregunte si quiere ejecutar conda init



6. Salga del servidor escribiendo:


```bash
exit
```

En su terminal ud antes veía 
__user@labtaa__

7. Vuelva conectarse al servidor, en la ventana aparecerá __(base)__ junto al nombre del ususario:

__(base)user@labtaa__

8. Confirme que se instaló anaconda revisando los ambientes;


```bash
conda info --envs
```

En el servidor está instalado Jupyter y en anaconda también, siempre y cuando ud haya instalado anaconda y no una versión minimalista de la distribución, pero confirme sus 
versiones como se describe a continuación.

- Desactive anaconda mediante:


```bash
conda deactivate
```

- confirme que existe un python nativo mediante:


```bash
which python
```

- Active anaconda de nuevo mediante:


```bash
conda activate
```

- Con anaconda activo vuelva a correr:


```bash
which python
```

9. Cree un ambiente en donde hara sus intalaciones de anaconda

10. Use el servidor 

## Segundo contacto: Conectandose mediante Jupyter

Una vez insalados todos los paquetes a utilizar, el trabajo se realizará mediante Jupyter



__Nota: Todo lo que realice en este punto es en teminal, nada debe realizar con Jupyter que es lo último de este tutorial__

1. Desde su tertminal de su distribución GNU/Linux o WSL teclee para loguearse:


```bash
ssh user@10.5.7.10 #EL USER DEBE SER EL PROPIO
```

2. Ponga su password

3. En el servidor remoto ejecutar segun desee "jupyter lab" o "jupyter notebook":


```bash
jupyter lab --no-browser --port=8888
#jupyter notebook --no-browser --port=8888
```

La orden anterior permitirá que Jupyter se conecte a un puerto pero sin abrir en explorador

4. __Sin cerrar la terminal anterior__, la cuál continuara ejecutando,abra una segunda terminal de su maquina local y conectese al servidor también


```bash
ssh user@10.5.7.10 #EL USER DEBE SER EL PROPIO
```

5. En esta segunda terminal y despues de haberse loguead een el servidor introduzca:


```bash
ssh -NL localhost:1234:localhost:8888 user@10.5.7.10
```

En este punto su maquina local ya está conectada al servidor por Jupyter __Nota: No cierre ninguna de las dos ventanas en ejecución__

6. Vaya al explorador de su preferencia de su maquina local y pegue lo siguiente en la dirección:



http://localhost:1234

7. Congratulaciones, está conectado, realice su procedimiento en Jupyter
