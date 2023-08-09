# Instalación de python y anaconda en caso de ser requeridos

__Nota: Todo lo que realizará a continuación sera con conexión remota a un servidor desde terminal WSL o desde terminal GNU/Linux (logeado por ssh en el servidor):__

Los servidores GNU/Linux ya viene con [python](https://www.python.org/doc/), [Jupyter](https://jupyter.org/)-[lab](https://jupyterlab.readthedocs.io/en/stable/) y [Jupyter](https://jupyter.org/)-[notebook](https://ebac.mx/blog/jupyter-notebook) nativo instalado, y muy probablemente también anaconda, pero si desea y puede hacer la instalación de anaconda, primero debe tener encuenta que se instala en su __$HOME__ y no en el sistema, entonces las instalacione remotas de anaconda en servidores se almacenan en el $HOME de los usuarios, se proporciona esta información en caso de que se anime arealizar la instalación de la distribución de anaconda.

__Nota: En caso contrario, ya debe estar instalado en su sistema o debe cargarse con un gestor de carga de paquetes com Environment-modules.__


Se dejan los pasos a seguir para la instalación de anaconda.

Se describen los pasos a continuación:


1. Primero en el explorador de internet de la __maquina local__ se abre la pagina de [anaconda](https://www.anaconda.com/products/distribution#Downloads) y se busca la última versión:  
https://www.anaconda.com/products/distribution#Downloads

2. Enla sección de descargas, se seleccina el paquete a instalar, si el servidor es GNU/Linux, entonces la versión a instalar es de linux, se copia la dirección de enlace y se pega en la __terminal remota__ del servidor con click derecho sobre el ícono __64-Bit (x86) Installer (737 MB)__ y precedido por el comando __*wget*__, por ejemplo:


```python
wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh
```

3. Se introduzce el comando __"ls"__ para listar archivos y ver si se descargo el archivo instalador con extensión **_*.sh_**:


```python
ls
```

4. Es probable que encuentre un archivo como __Anaconda3-2022.10-Linux-x86_64.sh__ entre los archivos, entonces se ejecutael instalador mediante:


```python
sh Anaconda3-2022.10-Linux-x86_64.sh
```

5. Las instrucciones del instalador, guían al usuario:

- Se debe aceptar la licencia escribiendo "*yes*" cuando se solicite.

- Se debe aceptar con enter o intro cuando el instaladorpide confirmar el directorio de instalación /home/user

- Se debe escribir "*yes*" al final de la instalación cuando el instalador pregunta si quiere ejecutar conda init para inicioa automático de anaconda



6. Salga del servidor con la finalidad de reiniciarlo escribiendo:


```python
exit
```

En la terminal antes de la insalación se ve así: 
__user@servidor__

7. Posterior a la instalación de anaconda al conectarse al servidor, en la ventana aparecerá __(base)__ junto al nombre del ususario:

__(base)user@servidor__

8. Se confirma que la instalación de anaconda revisando los ambientes;


```python
conda info --envs
```

En los servidores con GNU/Linux ya traen preinsalado python y pueden traer Jupyter, la distribución de anaconda también traje jupyter, siempre y cuando se haya instalado anaconda y no una versión minimalista de la como conda, pero se puede confirmar si en la instalación hay Jupyter mediante la revisión de cual jupyter hay en el sistema.


- Primero, se desactiva anaconda mediante:


```python
conda deactivate
```

- Segundo, se confirma que existe un python nativo mediante:


```python
which python # Esto muestra la ruta de instalación nativa de Python
python --version# Esto muestra la versión nativa de Python
```


```python
which Jupyter #Esto muestra la ruta de instalación nativa de Jupyter
jupyter --version # Esto muestra la versión nativa de Jupyter
```

- Tercero, se activa anaconda de nuevamente mediante:


```python
conda activate
```

- Con anaconda activo, se vuelve a correr:


```python
which python # Esto muestra la ruta de instalación nativa de Python
python --version# Esto muestra la versión nativa de Python
```


```python
which Jupyter #Esto muestra la ruta de instalación nativa de Jupyter
jupyter --version # Esto muestra la versión nativa de Jupyter
```

9. Se deben crear ambientes en donde realicen las intalaciones de anaconda de acuerdo a las necesidades de los usuarios
