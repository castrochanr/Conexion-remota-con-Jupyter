# Correr MrBayes desde [Jupyter](https://jupyter.org/)

Primero debe tener instalado [Jupyter](https://jupyter.org/) notebook y jupyterlab (o solo lab)

Hay 2 maneras de tener instalado [Jupyter](https://jupyter.org/)

1. La primera puede ser de manera nativa en su distribución o desde su distro en WSL mediante python y pip

2. La segunda es desde su instalación de conda o anaconda,mediante las *condenes conda install PAQUETE*.


## Instalación nativa de [python](https://www.python.org/)

### Instalación existente [python](https://www.python.org/)

Si ud desea realizar una instalación nativa, la primera opción, entonces debe saber que las distros de GNU/Linux traen instalado por default una versión de python, ud puede saber que versión tiene, mediante:


```bash
which python # me permite conocer donde está instalada la versión que correré
```

    /usr/bin/python


En mi caso, como mi instalación es nativa, la ruta es */usr/bin/python*, si mi instalación fuera en anaconda o conda, mi ruta sería similar a */home/user/anaconda3/bin/python*


```bash
python --version #con este comando verémos la versión instalada
```

    Python 2.7.18


la versión anterior es la versión que mi distro trae por default. Por motivos que no describiremos en este tutorial hay otra versión de python en GNU/Linux y podremos ver la sersión con el comando a continuación


```bash
python3 --version # la versión del cmd anterior fue de python2, aca veremos la versión de python3 instalada
```

    Python 3.9.2


Como acabamos de ver, la versión instalada es python-3.9.2

### Instalación nueva de [python](https://www.python.org/)

Si ud no tiene una version de python3 instalada, entonces instale como se le indica a continuación, __**No realice esta instalación si ud ya tiene python__

*sudo apt install python3 pip3*

Con lo anterior nos instalará python3 y pip, pip es el instalador de python, con ello instalaremos Jupyter notebook y jupyterlab adeás de los kernels de jupyter

Si ud desea saber sobre [python](https://www.python.org/) en https://www.python.org/ puede leer toda la información necesaria:

Casi todas las extensiones de python pueden encontrarse en https://pypi.org/, Jupyter es una extensión, los kernels de jupyter también lo son. Con pip se pueden instalar las extensiones mediante:


```bash
pip install jupyter notebook jupyterlab
```

    Requirement already satisfied: jupyter in /home/rcastro/.local/lib/python3.9/site-packages (1.0.0)
    Requirement already satisfied: notebook in /home/rcastro/.local/lib/python3.9/site-packages (6.5.2)
    Requirement already satisfied: jupyterlab in /home/rcastro/.local/lib/python3.9/site-packages (3.6.1)
    Requirement already satisfied: nbconvert in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter) (7.2.9)
    Requirement already satisfied: qtconsole in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter) (5.4.0)
    Requirement already satisfied: ipywidgets in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter) (8.0.4)
    Requirement already satisfied: ipykernel in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter) (6.21.1)
    Requirement already satisfied: jupyter-console in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter) (6.4.4)
    Requirement already satisfied: jupyter-server-ydoc<0.7.0,>=0.6.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (0.6.1)
    Requirement already satisfied: jupyter-ydoc~=0.2.2 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (0.2.2)
    Requirement already satisfied: nbclassic in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (0.5.1)
    Requirement already satisfied: jinja2>=2.1 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (3.1.2)
    Requirement already satisfied: tomli in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (2.0.1)
    Requirement already satisfied: jupyter-core in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (5.2.0)
    Requirement already satisfied: ipython in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (8.9.0)
    Requirement already satisfied: jupyterlab-server~=2.19 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (2.19.0)
    Requirement already satisfied: tornado>=6.1.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (6.2)
    Requirement already satisfied: packaging in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (23.0)
    Requirement already satisfied: jupyter-server<3,>=1.16.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab) (1.23.5)
    Requirement already satisfied: traitlets>=4.2.1 in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (5.9.0)
    Requirement already satisfied: nbformat in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (5.7.3)
    Requirement already satisfied: nest-asyncio>=1.5 in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (1.5.6)
    Requirement already satisfied: argon2-cffi in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (21.3.0)
    Requirement already satisfied: pyzmq>=17 in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (25.0.0)
    Requirement already satisfied: Send2Trash>=1.8.0 in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (1.8.0)
    Requirement already satisfied: terminado>=0.8.3 in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (0.17.1)
    Requirement already satisfied: jupyter-client>=5.3.4 in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (7.4.1)
    Requirement already satisfied: ipython-genutils in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (0.2.0)
    Requirement already satisfied: prometheus-client in /home/rcastro/.local/lib/python3.9/site-packages (from notebook) (0.16.0)
    Requirement already satisfied: MarkupSafe>=2.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jinja2>=2.1->jupyterlab) (2.1.2)
    Requirement already satisfied: python-dateutil>=2.8.2 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-client>=5.3.4->notebook) (2.8.2)
    Requirement already satisfied: entrypoints in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-client>=5.3.4->notebook) (0.4)
    Requirement already satisfied: platformdirs>=2.5 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-core->jupyterlab) (3.0.0)
    Requirement already satisfied: anyio<4,>=3.1.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-server<3,>=1.16.0->jupyterlab) (3.6.2)
    Requirement already satisfied: websocket-client in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-server<3,>=1.16.0->jupyterlab) (1.5.1)
    Requirement already satisfied: sniffio>=1.1 in /home/rcastro/.local/lib/python3.9/site-packages (from anyio<4,>=3.1.0->jupyter-server<3,>=1.16.0->jupyterlab) (1.3.0)
    Requirement already satisfied: idna>=2.8 in /usr/lib/python3/dist-packages (from anyio<4,>=3.1.0->jupyter-server<3,>=1.16.0->jupyterlab) (2.10)
    Requirement already satisfied: ypy-websocket<0.9.0,>=0.8.2 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (0.8.2)
    Requirement already satisfied: jupyter-server-fileid<1,>=0.6.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (0.6.0)
    Requirement already satisfied: jupyter-events~=0.5.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (0.5.0)
    Requirement already satisfied: python-json-logger in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (2.0.4)
    Requirement already satisfied: jsonschema[format-nongpl]>=4.3.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (4.17.3)
    Requirement already satisfied: pyyaml in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (6.0)
    Requirement already satisfied: attrs>=17.4.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (22.2.0)
    Requirement already satisfied: pyrsistent!=0.17.0,!=0.17.1,!=0.17.2,>=0.14.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (0.19.3)
    Requirement already satisfied: jsonpointer>1.13 in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (2.3)
    Requirement already satisfied: rfc3986-validator>0.1.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (0.1.1)
    Requirement already satisfied: webcolors>=1.11 in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (1.12)
    Requirement already satisfied: rfc3339-validator in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (0.1.4)
    Requirement already satisfied: fqdn in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (1.5.1)
    Requirement already satisfied: isoduration in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (20.11.0)
    Requirement already satisfied: uri-template in /home/rcastro/.local/lib/python3.9/site-packages (from jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (1.2.0)
    Requirement already satisfied: importlib-metadata>=3.6 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-ydoc~=0.2.2->jupyterlab) (6.0.0)
    Requirement already satisfied: y-py<0.6.0,>=0.5.3 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyter-ydoc~=0.2.2->jupyterlab) (0.5.5)
    Requirement already satisfied: zipp>=0.5 in /home/rcastro/.local/lib/python3.9/site-packages (from importlib-metadata>=3.6->jupyter-ydoc~=0.2.2->jupyterlab) (3.13.0)
    Requirement already satisfied: requests>=2.28 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab-server~=2.19->jupyterlab) (2.28.2)
    Requirement already satisfied: json5>=0.9.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab-server~=2.19->jupyterlab) (0.9.11)
    Requirement already satisfied: babel>=2.10 in /home/rcastro/.local/lib/python3.9/site-packages (from jupyterlab-server~=2.19->jupyterlab) (2.11.0)
    Requirement already satisfied: pytz>=2015.7 in /home/rcastro/.local/lib/python3.9/site-packages (from babel>=2.10->jupyterlab-server~=2.19->jupyterlab) (2022.7.1)
    Requirement already satisfied: notebook-shim>=0.1.0 in /home/rcastro/.local/lib/python3.9/site-packages (from nbclassic->jupyterlab) (0.2.2)
    Requirement already satisfied: tinycss2 in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (1.2.1)
    Requirement already satisfied: pandocfilters>=1.4.1 in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (1.5.0)
    Requirement already satisfied: nbclient>=0.5.0 in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (0.7.2)
    Requirement already satisfied: pygments>=2.4.1 in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (2.14.0)
    Requirement already satisfied: beautifulsoup4 in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (4.11.2)
    Requirement already satisfied: bleach in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (6.0.0)
    Requirement already satisfied: defusedxml in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (0.7.1)
    Requirement already satisfied: mistune<3,>=2.0.3 in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (2.0.5)
    Requirement already satisfied: jupyterlab-pygments in /home/rcastro/.local/lib/python3.9/site-packages (from nbconvert->jupyter) (0.2.2)
    Requirement already satisfied: fastjsonschema in /home/rcastro/.local/lib/python3.9/site-packages (from nbformat->notebook) (2.16.2)
    Requirement already satisfied: six>=1.5 in /usr/lib/python3/dist-packages (from python-dateutil>=2.8.2->jupyter-client>=5.3.4->notebook) (1.16.0)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in /usr/lib/python3/dist-packages (from requests>=2.28->jupyterlab-server~=2.19->jupyterlab) (1.26.5)
    Requirement already satisfied: certifi>=2017.4.17 in /usr/lib/python3/dist-packages (from requests>=2.28->jupyterlab-server~=2.19->jupyterlab) (2020.6.20)
    Requirement already satisfied: charset-normalizer<4,>=2 in /home/rcastro/.local/lib/python3.9/site-packages (from requests>=2.28->jupyterlab-server~=2.19->jupyterlab) (3.0.1)
    Requirement already satisfied: ptyprocess in /home/rcastro/.local/lib/python3.9/site-packages (from terminado>=0.8.3->notebook) (0.7.0)
    Requirement already satisfied: aiosqlite<1,>=0.17.0 in /home/rcastro/.local/lib/python3.9/site-packages (from ypy-websocket<0.9.0,>=0.8.2->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (0.18.0)
    Requirement already satisfied: aiofiles<23,>=22.1.0 in /home/rcastro/.local/lib/python3.9/site-packages (from ypy-websocket<0.9.0,>=0.8.2->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (22.1.0)
    Requirement already satisfied: argon2-cffi-bindings in /home/rcastro/.local/lib/python3.9/site-packages (from argon2-cffi->notebook) (21.2.0)
    Requirement already satisfied: cffi>=1.0.1 in /home/rcastro/.local/lib/python3.9/site-packages (from argon2-cffi-bindings->argon2-cffi->notebook) (1.15.1)
    Requirement already satisfied: pycparser in /home/rcastro/.local/lib/python3.9/site-packages (from cffi>=1.0.1->argon2-cffi-bindings->argon2-cffi->notebook) (2.21)
    Requirement already satisfied: soupsieve>1.2 in /home/rcastro/.local/lib/python3.9/site-packages (from beautifulsoup4->nbconvert->jupyter) (2.3.2.post1)
    Requirement already satisfied: webencodings in /home/rcastro/.local/lib/python3.9/site-packages (from bleach->nbconvert->jupyter) (0.5.1)
    Requirement already satisfied: comm>=0.1.1 in /home/rcastro/.local/lib/python3.9/site-packages (from ipykernel->jupyter) (0.1.2)
    Requirement already satisfied: debugpy>=1.6.5 in /home/rcastro/.local/lib/python3.9/site-packages (from ipykernel->jupyter) (1.6.6)
    Requirement already satisfied: matplotlib-inline>=0.1 in /home/rcastro/.local/lib/python3.9/site-packages (from ipykernel->jupyter) (0.1.6)
    Requirement already satisfied: psutil in /home/rcastro/.local/lib/python3.9/site-packages (from ipykernel->jupyter) (5.9.4)
    Requirement already satisfied: jedi>=0.16 in /home/rcastro/.local/lib/python3.9/site-packages (from ipython->jupyterlab) (0.18.2)
    Requirement already satisfied: stack-data in /home/rcastro/.local/lib/python3.9/site-packages (from ipython->jupyterlab) (0.6.2)
    Requirement already satisfied: decorator in /home/rcastro/.local/lib/python3.9/site-packages (from ipython->jupyterlab) (5.1.1)
    Requirement already satisfied: backcall in /home/rcastro/.local/lib/python3.9/site-packages (from ipython->jupyterlab) (0.2.0)
    Requirement already satisfied: prompt-toolkit<3.1.0,>=3.0.30 in /home/rcastro/.local/lib/python3.9/site-packages (from ipython->jupyterlab) (3.0.36)
    Requirement already satisfied: pickleshare in /home/rcastro/.local/lib/python3.9/site-packages (from ipython->jupyterlab) (0.7.5)
    Requirement already satisfied: pexpect>4.3 in /home/rcastro/.local/lib/python3.9/site-packages (from ipython->jupyterlab) (4.8.0)
    Requirement already satisfied: parso<0.9.0,>=0.8.0 in /home/rcastro/.local/lib/python3.9/site-packages (from jedi>=0.16->ipython->jupyterlab) (0.8.3)
    Requirement already satisfied: wcwidth in /home/rcastro/.local/lib/python3.9/site-packages (from prompt-toolkit<3.1.0,>=3.0.30->ipython->jupyterlab) (0.2.6)
    Requirement already satisfied: jupyterlab-widgets~=3.0 in /home/rcastro/.local/lib/python3.9/site-packages (from ipywidgets->jupyter) (3.0.5)
    Requirement already satisfied: widgetsnbextension~=4.0 in /home/rcastro/.local/lib/python3.9/site-packages (from ipywidgets->jupyter) (4.0.5)
    Requirement already satisfied: arrow>=0.15.0 in /home/rcastro/.local/lib/python3.9/site-packages (from isoduration->jsonschema[format-nongpl]>=4.3.0->jupyter-events~=0.5.0->jupyter-server-fileid<1,>=0.6.0->jupyter-server-ydoc<0.7.0,>=0.6.0->jupyterlab) (1.2.3)
    Requirement already satisfied: qtpy>=2.0.1 in /home/rcastro/.local/lib/python3.9/site-packages (from qtconsole->jupyter) (2.3.0)
    Requirement already satisfied: executing>=1.2.0 in /home/rcastro/.local/lib/python3.9/site-packages (from stack-data->ipython->jupyterlab) (1.2.0)
    Requirement already satisfied: pure-eval in /home/rcastro/.local/lib/python3.9/site-packages (from stack-data->ipython->jupyterlab) (0.2.2)
    Requirement already satisfied: asttokens>=2.1.0 in /home/rcastro/.local/lib/python3.9/site-packages (from stack-data->ipython->jupyterlab) (2.2.1)


**Mi instalación es nativa, y en mi caso las instalaciones ya estaban realizadas, así que no se realizó nada con la orden anterior.**

### Instalación de [python](https://www.python.org/) en [anaconda](https://www.anaconda.com/products/distribution)

No es requerida, Anaconda y conda son implementaciones de python en ambientes. si desea leer mas sobre anaconda revise el link con la documentación https://www.anaconda.com/products/distribution.

#### Instalación anaconda [anaconda](https://www.anaconda.com/products/distribution) o conda

Googlee [anaconda](https://www.anaconda.com/products/distribution) y seleccione anaconda distribution, el link es pagina oficial https://www.anaconda.com/products/distribution, en la parte inferior de la página están los instaladores.

Seleccione el link de descarga **64-Bit (x86) Installer** si tiene una distro nativa GNU/Linux o si tiene WSL (en Windows), o alguno de los links de descarga de MacOS como **64-Bit Graphical Installer**

En el caso de la distro de linux o WSL puede instalar con wget (si no lo tinee instalado, installe con **sudo apt install wget**), requiere tener el la dirección de descarga que ud obtiene dando click derecho sobre el ícono del paquete y seleccionando "copiar direccion de enlace", en mi caso la dirección es: __https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh__

Primero veremos nuestra ruta y nos moveremos a **~/** para realizar la descarga e instalación


```bash
pwd #nos muestra nuestra ruta
```

    /home/rcastro/Documentos



```bash
cd ~/ #nos cambiamos a home

```


```bash
pwd #nos muestra uestra nueva ruta de trabajo
```

    /home/rcastro


Aca realizamos la descarga del paquete con el link copiado y wget


```bash
wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh
```

    --2023-02-21 12:45:23--  https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh
    Resolviendo repo.anaconda.com (repo.anaconda.com)... 104.16.130.3, 104.16.131.3, 2606:4700::6810:8203, ...
    Conectando con repo.anaconda.com (repo.anaconda.com)[104.16.130.3]:443... conectado.
    Petición HTTP enviada, esperando respuesta... 200 OK
    Longitud: 773428196 (738M) [application/x-sh]
    Grabando a: «Anaconda3-2022.10-Linux-x86_64.sh»
    
    Anaconda3-2022.10-L 100%[===================>] 737.60M  47.9MB/s    en 16s     
    
    2023-02-21 12:45:39 (45.9 MB/s) - «Anaconda3-2022.10-Linux-x86_64.sh» guardado [773428196/773428196]
    



```bash
ls *Anaconda*
```

    Anaconda3-2022.10-Linux-x86_64.sh


correr:

__sh Anaconda3*__

Tras la instalacion reiniciamos la consola y debe aparecer (base) antes del ususario en la terminal

En mi caso para activar anaconda corro conda activate


```bash
conda activate
```

    (base) 




Como se puede observar aparece (base), lo que significa que anaconda está instalado.

### instalación de Python en anaconda no necesaria

Si usted tiene una version de conda, tendrá que ir instalando jupyter, noteboo,lab con la siguiente orden:


[tips](https://www.dataquest.io/blog/jupyter-notebook-tips-tricks-shortcuts/)


```bash
conda install jupyter notebook jupyterlab -y
```

    Collecting package metadata (current_repodata.json): done
    Solving environment: done
    
    ## Package Plan ##
    
      environment location: /home/rcastro/anaconda3
    
      added / updated specs:
        - jupyter
        - jupyterlab
        - notebook
    
    
    The following packages will be downloaded:
    
        package                    |            build
        ---------------------------|-----------------
        conda-23.1.0               |   py39h06a4308_0         942 KB
        ruamel.yaml-0.17.21        |   py39h5eee18b_0         178 KB
        ruamel.yaml.clib-0.2.6     |   py39h5eee18b_1         140 KB
        ------------------------------------------------------------
                                               Total:         1.2 MB
    
    The following NEW packages will be INSTALLED:
    
      ruamel.yaml        pkgs/main/linux-64::ruamel.yaml-0.17.21-py39h5eee18b_0 None
      ruamel.yaml.clib   pkgs/main/linux-64::ruamel.yaml.clib-0.2.6-py39h5eee18b_1 None
    
    The following packages will be UPDATED:
    
      conda                               22.9.0-py39h06a4308_0 --> 23.1.0-py39h06a4308_0 None
    
    
    
    Downloading and Extracting Packages
    conda-23.1.0         | 942 KB    | ##################################### | 100% 
    ruamel.yaml.clib-0.2 | 140 KB    | ##################################### | 100% 
    ruamel.yaml-0.17.21  | 178 KB    | ##################################### | 100% 
    Preparing transaction: done
    Verifying transaction: done
    Executing transaction: done
    Retrieving notices: ...working... done
    (base) 




confirmamos las versiones de python y la instalación


```bash
which python
```

    /home/rcastro/anaconda3/bin/python
    (base) 





```bash
python --version
```

    Python 3.9.13
    (base) 




Como se puede observar esta instalado en la carpeta de anaconda, la versión fue 3.9.13 y la de debian 3.9.12 (nativo).

En mi caso tengo ambas instalaciones y si anaconda esta activo, el sistema dara prioriad a los paquetes de anaconda.

Se puede desactivar anaconda con la orden *conda deactivate* o reactivar *conda activate*.

**_Los paquetes nativos correran, siempre y cuando no exista el paquete en el ambiente activo de anaconda_**


### Instalación nativa de [MrBayes](https://nbisweden.github.io/MrBayes/download.html)




```bash
# sudo apt install mrbayes mrbayes-mpi #no lo realizaré porque ya tengo la instalación nativa
```

    (base) 




Segun anaconda la instalación de [MrBayes](https://nbisweden.github.io/MrBayes/download.html) se debe realizar como sigue
https://anaconda.org/bioconda/mrbayes:


```bash
conda install -c bioconda mrbayes -y
```

    Collecting package metadata (current_repodata.json): done
    Solving environment: failed with initial frozen solve. Retrying with flexible solve.
    Solving environment: failed with repodata from current_repodata.json, will retry with next repodata source.
    Collecting package metadata (repodata.json): done
    Solving environment: failed with initial frozen solve. Retrying with flexible solve.
    Solving environment: | 
    Found conflicts! Looking for incompatible packages.
    This can take several minutes.  Press CTRL-C to abort.
                                                                                    Determining conflicts:   0%|                              | 0/6 [00:00<?, ?it/sfailed
    
    UnsatisfiableError: The following specifications were found to be incompatible with each other:
    
    Output in format: Requested package -> Available versions
    
    Package _libgcc_mutex conflicts for:
    python=3.9 -> libgcc-ng[version='>=11.2.0'] -> _libgcc_mutex[version='*|0.1',build=main]
    mrbayes -> libgcc-ng[version='>=10.3.0'] -> _libgcc_mutex[version='*|0.1',build=main]
    
    Package ncurses conflicts for:
    mrbayes -> ncurses[version='>=6.1,<6.2.0a0|>=6.2,<6.3.0a0|>=6.3,<7.0a0']
    mrbayes -> readline[version='>=8.1,<9.0a0'] -> ncurses[version='>=6.1,<7.0a0|>=6.2,<7.0a0']
    
    Package libgcc-ng conflicts for:
    mrbayes -> beagle-lib[version='<4'] -> libgcc-ng[version='>=11.2.0|>=4.9|>=7.2.0']
    mrbayes -> libgcc-ng[version='>=10.3.0|>=12|>=9.4.0|>=9.3.0|>=7.5.0|>=7.3.0']The following specifications were found to be incompatible with your system:
    
      - feature:/linux-64::__glibc==2.31=0
      - feature:|@/linux-64::__glibc==2.31=0
      - python=3.9 -> libgcc-ng[version='>=11.2.0'] -> __glibc[version='>=2.17']
    
    Your installed version is: 2.31
    
    
    (base) 




[MrBayes](https://nbisweden.github.io/MrBayes/download.html), es un software de tiempo real, no se puede correr en Jupyter, se puede ejecutar mediante un script.

## Corriendo [MrBayes](https://nbisweden.github.io/MrBayes/download.html)

Si ud está corriendo en terminal, puede ir introduciendo los comandos uno por uno y seguir los pasos:

>pwd #para ver su directorio de trabajo, debe conocer la ruta de su archivo *.nex
>mb

>    execute primates.nex;

>    lset nst=6 rates=invgamma;

>    mcmc nchains=4 nruns=2 ngen=20000 samplefreq=100 printfreq=100 diagnfreq=1000;

>  q #para salir de Mr Bayes


En el caso de Jupyter, reciclaremos el código para construir un ejecutable

1. Crearemos un archivo de texto con extensión *.nex


```bash
touch myfile.nex
```

    (base) 





```bash
ls myfile*.nex
```

    myfile02.nex  myfile.nex
    (base) 




El archivo que creemos trendrá cierta estructura para poder correr y el objetivo es documentar, no nos enviará los errores a pantalla, la estructura será similar a este archivo:


```bash
cat myfile02.nex
```

    [ topology constrained to include South and Central Aslian ]
    
    begin mrbayes;
      log start filename=test.log replace;	
      set autoclose=yes nowarn=yes;
        execute primates.nex;
        lset nst=6 rates=invgamma;
        mcmc nchains=4 nruns=2 ngen=20000 samplefreq=100 printfreq=100 diagnfreq=1000;
      sump;					
      sumt;
      log stop;
    end;
    
    (base) 




Revisemos el archivo que crearemos, para ver que no contiene nada despues de haberlo creado con *touch*.

El código que nos permitirá tener este formato requiere que los renglones vayan separados por el símbolo "\", que la terminal interpretará como *enter* o *intro* o como ud prefiera llamarle


```bash
cat myfile.nex
```

    (base) 




Como se puede ver no salió nada como resultado, lo que significa que el archivo no tiene contenido, ahora ejecutemos el comando:

Abra un edtor de texto y ponga la estructura en el archivo .nex


```bash
cat myfile.nex
```

    [ topology constrained to include South and Central Aslian ]
    
    begin mrbayes;
      log start filename=test.log replace;
      set autoclose=yes nowarn=yes;
        execute primates.nex;
        lset nst=6 rates=invgamma;
        mcmc nchains=4 nruns=2 ngen=20000 samplefreq=100 printfreq=100 diagnfreq=1000;
      sump;					
      sumt;
      log stop;
    end;(base) 




Con esta estructura se puede corres un análisis en MrBayes desde jupyter recuerde que puede usar *mb* o *mb-mpi*:


```bash
time mb myfile.nex
```

    
    
                                MrBayes 3.2.7a x86_64
    
                          (Bayesian Analysis of Phylogeny)
    
                  Distributed under the GNU General Public License
    
    
                   Type "help" or "help <command>" for information
                         on the commands that are available.
    
                       Type "about" for authorship and general
                           information about the program.
    
    
    
       Executing file "myfile.nex"
       UNIX line termination
       Longest line length = 97
       Parsing file
       Reading mrbayes block
          Logging screen output to file "test.log"
          Setting autoclose to yes
          Setting nowarnings to yes
          Setting usebeagle to yes
          Setting beagledevice to CPU
          Setting beagleprecision to double
          Setting beaglescaling to Dynamic
          Setting beaglesse to Yes
    
          Executing file "primates.nex"...
    
       DOS line termination
       Longest line length = 920
       Parsing file
       Expecting NEXUS formatted file
       Reading data block
          Allocated taxon set
          Allocated matrix
          Defining new matrix with 12 taxa and 898 characters
          Data is Dna
          Data matrix is not interleaved
          Gaps coded as -
          Taxon  1 -> Tarsius_syrichta
          Taxon  2 -> Lemur_catta
          Taxon  3 -> Homo_sapiens
          Taxon  4 -> Pan
          Taxon  5 -> Gorilla
          Taxon  6 -> Pongo
          Taxon  7 -> Hylobates
          Taxon  8 -> Macaca_fuscata
          Taxon  9 -> M_mulatta
          Taxon 10 -> M_fascicularis
          Taxon 11 -> M_sylvanus
          Taxon 12 -> Saimiri_sciureus
          Successfully read matrix
          Setting default partition (does not divide up characters)
          Setting model defaults
          Seed (for generating default start values) = 1677097749
          Setting output file names to "primates.nex.run<i>.<p|t>"
       Exiting data block
       Reached end of file
    
       Returning execution to calling file ...
    
          Setting Nst to 6
          Setting Rates to Invgamma
          Successfully set likelihood model parameters
          Setting number of chains to 4
          Setting number of runs to 2
          Setting number of generations to 20000
          Setting sample frequency to 100
          Setting print frequency to 100
          Setting diagnosing frequency to 1000
          Setting chain output file names to "primates.nex.run<i>.<p/t>"
          Running Markov chain
          MCMC stamp = 5498659517
          Seed = 852106496
          Swapseed = 1677097749
          Model settings:
    
             Data not partitioned --
                Datatype  = DNA
                Nucmodel  = 4by4
                Nst       = 6
                            Substitution rates, expressed as proportions
                            of the rate sum, have a Dirichlet prior
                            (1.00,1.00,1.00,1.00,1.00,1.00)
                Covarion  = No
                # States  = 4
                            State frequencies have a Dirichlet prior
                            (1.00,1.00,1.00,1.00)
                Rates     = Invgamma
                            The distribution is approximated using 4 categories.
                            Shape parameter is exponentially
                            distributed with parameter (1.00).
                            Proportion of invariable sites is uniformly dist-
                            ributed on the interval (0.00,1.00).
    
          Active parameters: 
    
             Parameters
             ---------------------
             Revmat              1
             Statefreq           2
             Shape               3
             Pinvar              4
             Ratemultiplier      5
             Topology            6
             Brlens              7
             ---------------------
    
             1 --  Parameter  = Revmat
                   Type       = Rates of reversible rate matrix
                   Prior      = Dirichlet(1.00,1.00,1.00,1.00,1.00,1.00)
    
             2 --  Parameter  = Pi
                   Type       = Stationary state frequencies
                   Prior      = Dirichlet
    
             3 --  Parameter  = Alpha
                   Type       = Shape of scaled gamma distribution of site rates
                   Prior      = Exponential(1.00)
    
             4 --  Parameter  = Pinvar
                   Type       = Proportion of invariable sites
                   Prior      = Uniform(0.00,1.00)
    
             5 --  Parameter  = Ratemultiplier
                   Type       = Partition-specific rate multiplier
                   Prior      = Fixed(1.0)
    
             6 --  Parameter  = Tau
                   Type       = Topology
                   Prior      = All topologies equally probable a priori
                   Subparam.  = V
    
             7 --  Parameter  = V
                   Type       = Branch lengths
                   Prior      = Unconstrained:GammaDir(1.0,0.1000,1.0,1.0)
    
    
    
          The MCMC sampler will use the following moves:
             With prob.  Chain will use move
                0.93 %   Dirichlet(Revmat)
                0.93 %   Slider(Revmat)
                0.93 %   Dirichlet(Pi)
                0.93 %   Slider(Pi)
                1.85 %   Multiplier(Alpha)
                1.85 %   Slider(Pinvar)
                9.26 %   ExtSPR(Tau,V)
                9.26 %   ExtTBR(Tau,V)
                9.26 %   NNI(Tau,V)
                9.26 %   ParsSPR(Tau,V)
               37.04 %   Multiplier(V)
               12.96 %   Nodeslider(V)
                5.56 %   TLMultiplier(V)
    
          Division 1 has 413 unique site patterns
          Initializing conditional likelihoods
    
          Running benchmarks to automatically select fastest BEAGLE resource... 
          Using BEAGLE v3.1.2 resource 0 for division 1:
             Rsrc Name : CPU
             Impl Name : CPU-4State-SSE-Double
             Flags: PROCESSOR_CPU PRECISION_DOUBLE COMPUTATION_SYNCH EIGEN_REAL
                    SCALING_MANUAL SCALERS_RAW VECTOR_SSE THREADING_CPP         MODEL STATES: 4
          Initializing invariable-site conditional likelihoods
    
          Initial log likelihoods and log prior probs for run 1:
             Chain 1 -- -8359.576606 -- 42.620562
             Chain 2 -- -8880.111666 -- 42.620562
             Chain 3 -- -8865.367873 -- 42.620562
             Chain 4 -- -8448.855642 -- 42.620562
    
          Initial log likelihoods and log prior probs for run 2:
             Chain 1 -- -8538.576321 -- 42.620562
             Chain 2 -- -8953.339022 -- 42.620562
             Chain 3 -- -8599.256668 -- 42.620562
             Chain 4 -- -9101.413552 -- 42.620562
    
          Overwriting file "primates.nex.mcmc"
          Overwriting file "primates.nex.run1.p"
          Overwriting file "primates.nex.run1.t"
          Overwriting file "primates.nex.run2.p"
          Overwriting file "primates.nex.run2.t"
    
          Using a relative burnin of 25.0 % for diagnostics
    
          Chain results (20000 generations requested):
    
              0 -- [-8359.577] (-8880.112) (-8865.368) (-8448.856) * [-8538.576] (-8953.339) (-8599.257) (-9101.414) 
            100 -- (-6714.976) (-7250.702) (-6498.845) [-6504.913] * [-6841.064] (-6851.119) (-7008.647) (-6891.966) -- 0:00:00
            200 -- [-6337.488] (-6692.071) (-6336.269) (-6395.133) * (-6307.702) (-6289.426) [-6441.145] (-6596.460) -- 0:01:39
            300 -- (-6263.618) [-6196.794] (-6266.144) (-6301.644) * [-6233.394] (-6250.677) (-6231.711) (-6344.727) -- 0:01:05
            400 -- (-6215.234) [-6158.033] (-6243.005) (-6194.683) * (-6223.068) [-6169.233] (-6204.275) (-6223.223) -- 0:00:49
            500 -- (-6202.697) [-6098.068] (-6226.151) (-6167.621) * [-6145.302] (-6130.365) (-6174.444) (-6184.632) -- 0:00:39
            600 -- (-6193.119) [-6033.404] (-6165.437) (-6159.541) * (-6124.111) [-6105.402] (-6117.984) (-6124.670) -- 0:00:32
            700 -- (-6189.742) [-6031.702] (-6120.920) (-6146.366) * (-6121.133) [-6034.893] (-6118.670) (-6117.659) -- 0:00:27
            800 -- (-6144.832) [-6034.080] (-6117.030) (-6134.936) * (-6105.692) [-5990.337] (-6117.130) (-6110.299) -- 0:00:24
            900 -- (-6097.267) [-6018.106] (-6090.154) (-6129.190) * (-6069.514) [-5993.423] (-6120.650) (-6041.173) -- 0:00:21
           1000 -- (-6076.407) [-6002.290] (-6104.109) (-6120.301) * (-6018.190) [-5991.576] (-6082.136) (-6006.749) -- 0:00:19
    
          Average standard deviation of split frequencies: 0.014285
    
           1100 -- (-6048.022) (-6001.609) [-6030.640] (-6046.151) * (-5982.787) (-5992.195) (-6066.856) [-5989.825] -- 0:00:17
           1200 -- (-6002.899) [-5985.010] (-6013.020) (-6048.992) * (-5968.278) (-5965.512) (-6063.726) [-5972.954] -- 0:00:15
           1300 -- (-6003.337) [-5974.666] (-6014.809) (-6008.899) * [-5940.290] (-5962.034) (-6071.361) (-5971.698) -- 0:00:14
           1400 -- (-5987.601) [-5970.118] (-6018.547) (-5987.989) * [-5927.783] (-5936.402) (-6052.207) (-5972.971) -- 0:00:13
           1500 -- (-5981.968) [-5967.276] (-6017.134) (-5987.953) * (-5923.378) [-5909.277] (-6049.728) (-5980.762) -- 0:00:12
           1600 -- [-5938.293] (-5962.853) (-6011.684) (-5967.793) * (-5887.256) [-5887.534] (-6005.032) (-5957.771) -- 0:00:11
           1700 -- [-5944.441] (-5965.053) (-5978.126) (-5958.660) * [-5889.560] (-5885.143) (-5967.984) (-5956.254) -- 0:00:10
           1800 -- (-5940.195) (-5964.164) (-5940.704) [-5949.051] * [-5880.344] (-5866.230) (-5943.108) (-5956.627) -- 0:00:10
           1900 -- [-5930.199] (-5958.579) (-5944.124) (-5939.348) * (-5882.692) [-5866.299] (-5947.872) (-5925.149) -- 0:00:09
           2000 -- (-5909.854) (-5937.834) [-5926.043] (-5942.063) * (-5845.004) [-5858.399] (-5950.601) (-5926.625) -- 0:00:18
    
          Average standard deviation of split frequencies: 0.000000
    
           2100 -- (-5888.571) (-5920.741) [-5890.124] (-5937.030) * [-5832.273] (-5861.046) (-5923.851) (-5923.322) -- 0:00:17
           2200 -- [-5878.176] (-5921.152) (-5892.339) (-5920.568) * [-5819.306] (-5862.779) (-5924.862) (-5906.262) -- 0:00:16
           2300 -- [-5867.853] (-5913.330) (-5889.468) (-5923.661) * [-5820.249] (-5854.832) (-5894.566) (-5884.470) -- 0:00:15
           2400 -- (-5864.053) (-5918.730) [-5871.594] (-5905.071) * [-5807.469] (-5847.911) (-5892.456) (-5891.942) -- 0:00:14
           2500 -- [-5865.661] (-5919.748) (-5872.145) (-5909.020) * [-5804.171] (-5845.665) (-5893.121) (-5873.177) -- 0:00:14
           2600 -- [-5839.537] (-5914.266) (-5837.645) (-5884.947) * [-5798.932] (-5842.740) (-5858.101) (-5864.482) -- 0:00:13
           2700 -- [-5803.396] (-5895.362) (-5823.369) (-5873.273) * [-5801.493] (-5860.678) (-5862.295) (-5855.501) -- 0:00:12
           2800 -- [-5801.033] (-5888.671) (-5818.424) (-5871.912) * [-5802.868] (-5852.512) (-5850.483) (-5838.441) -- 0:00:12
           2900 -- [-5800.387] (-5883.305) (-5798.798) (-5860.257) * [-5799.001] (-5823.258) (-5819.875) (-5822.122) -- 0:00:11
           3000 -- [-5804.543] (-5886.502) (-5784.698) (-5860.365) * [-5795.309] (-5820.316) (-5812.646) (-5809.257) -- 0:00:11
    
          Average standard deviation of split frequencies: 0.000000
    
           3100 -- [-5796.841] (-5882.148) (-5790.410) (-5858.395) * [-5797.637] (-5798.395) (-5800.859) (-5809.730) -- 0:00:10
           3200 -- (-5795.332) (-5867.889) [-5785.144] (-5853.819) * [-5791.756] (-5791.420) (-5800.638) (-5793.602) -- 0:00:10
           3300 -- [-5798.303] (-5865.213) (-5785.084) (-5854.534) * [-5794.055] (-5780.684) (-5805.403) (-5802.127) -- 0:00:10
           3400 -- (-5793.539) (-5859.036) [-5782.363] (-5857.395) * (-5796.347) [-5764.140] (-5806.997) (-5790.680) -- 0:00:09
           3500 -- [-5789.318] (-5837.522) (-5786.258) (-5806.584) * (-5796.084) [-5762.320] (-5793.343) (-5783.641) -- 0:00:09
           3600 -- (-5791.864) (-5830.957) [-5780.283] (-5812.289) * (-5769.919) (-5761.917) (-5803.307) [-5770.550] -- 0:00:09
           3700 -- (-5785.579) (-5826.152) (-5777.185) [-5806.874] * (-5766.767) [-5760.718] (-5810.248) (-5769.522) -- 0:00:13
           3800 -- [-5775.819] (-5824.981) (-5766.705) (-5804.108) * (-5754.047) [-5750.308] (-5794.345) (-5767.158) -- 0:00:12
           3900 -- [-5763.134] (-5817.462) (-5768.382) (-5798.192) * [-5746.062] (-5753.800) (-5788.108) (-5771.378) -- 0:00:12
           4000 -- (-5769.432) (-5815.989) [-5766.881] (-5787.542) * (-5742.464) (-5750.739) (-5779.637) [-5762.126] -- 0:00:12
    
          Average standard deviation of split frequencies: 0.000000
    
           4100 -- (-5769.072) (-5809.076) [-5770.382] (-5783.828) * (-5742.742) [-5757.866] (-5777.508) (-5759.901) -- 0:00:11
           4200 -- [-5760.648] (-5807.534) (-5774.958) (-5783.717) * (-5739.020) [-5750.732] (-5775.439) (-5766.647) -- 0:00:11
           4300 -- (-5755.945) (-5807.615) [-5754.588] (-5758.120) * [-5737.010] (-5752.427) (-5770.104) (-5749.823) -- 0:00:10
           4400 -- (-5756.335) (-5791.732) (-5748.935) [-5758.388] * [-5731.940] (-5748.518) (-5767.203) (-5746.050) -- 0:00:10
           4500 -- (-5755.378) (-5790.681) (-5749.507) [-5758.244] * [-5733.417] (-5744.445) (-5765.743) (-5734.285) -- 0:00:10
           4600 -- (-5739.457) (-5788.974) [-5756.221] (-5750.356) * (-5729.589) (-5746.975) (-5765.643) [-5734.577] -- 0:00:10
           4700 -- [-5740.099] (-5779.478) (-5757.781) (-5746.983) * (-5731.307) (-5746.836) (-5769.765) [-5738.718] -- 0:00:09
           4800 -- [-5740.512] (-5778.795) (-5749.752) (-5752.733) * [-5729.569] (-5743.520) (-5771.911) (-5735.206) -- 0:00:09
           4900 -- (-5735.253) (-5771.907) [-5752.046] (-5757.440) * [-5735.156] (-5745.543) (-5771.880) (-5732.568) -- 0:00:09
           5000 -- [-5734.969] (-5772.944) (-5754.730) (-5749.784) * (-5734.591) (-5744.803) (-5767.586) [-5731.373] -- 0:00:09
    
          Average standard deviation of split frequencies: 0.000000
    
           5100 -- [-5731.702] (-5774.947) (-5746.148) (-5738.735) * (-5738.993) (-5745.882) (-5768.517) [-5730.934] -- 0:00:08
           5200 -- [-5733.154] (-5778.863) (-5735.003) (-5736.072) * (-5741.984) (-5747.493) (-5764.069) [-5731.240] -- 0:00:08
           5300 -- [-5729.723] (-5759.153) (-5732.569) (-5737.463) * [-5732.702] (-5739.531) (-5766.573) (-5729.404) -- 0:00:08
           5400 -- [-5727.039] (-5759.495) (-5735.504) (-5742.972) * (-5731.011) [-5738.513] (-5763.314) (-5732.439) -- 0:00:08
           5500 -- [-5732.990] (-5754.860) (-5733.377) (-5734.795) * [-5734.391] (-5744.267) (-5764.704) (-5727.206) -- 0:00:10
           5600 -- [-5724.441] (-5758.145) (-5730.899) (-5733.204) * (-5732.508) (-5737.438) (-5762.236) [-5730.049] -- 0:00:10
           5700 -- [-5724.968] (-5753.351) (-5733.510) (-5733.287) * [-5737.292] (-5732.121) (-5763.242) (-5729.095) -- 0:00:10
           5800 -- (-5736.184) (-5748.115) (-5729.773) [-5729.204] * (-5738.875) (-5731.433) (-5754.693) [-5730.651] -- 0:00:09
           5900 -- [-5730.852] (-5742.532) (-5728.327) (-5727.744) * [-5737.130] (-5734.226) (-5743.327) (-5727.915) -- 0:00:09
           6000 -- (-5737.213) [-5741.740] (-5728.939) (-5732.202) * [-5729.385] (-5739.887) (-5747.703) (-5725.932) -- 0:00:09
    
          Average standard deviation of split frequencies: 0.000000
    
           6100 -- [-5727.483] (-5738.936) (-5731.371) (-5729.780) * [-5723.296] (-5738.621) (-5754.850) (-5727.963) -- 0:00:09
           6200 -- [-5725.588] (-5741.830) (-5727.086) (-5731.164) * (-5726.396) (-5738.380) (-5742.770) [-5728.310] -- 0:00:08
           6300 -- (-5730.498) (-5742.007) [-5729.376] (-5728.401) * [-5722.154] (-5731.858) (-5742.365) (-5724.297) -- 0:00:08
           6400 -- (-5729.839) (-5741.523) (-5728.620) [-5727.618] * [-5724.127] (-5730.665) (-5745.060) (-5722.539) -- 0:00:08
           6500 -- [-5723.317] (-5741.060) (-5732.640) (-5727.288) * (-5727.581) (-5734.638) (-5741.516) [-5723.041] -- 0:00:08
           6600 -- (-5722.807) (-5738.380) (-5735.541) [-5727.205] * (-5726.969) (-5730.074) [-5742.827] (-5721.678) -- 0:00:08
           6700 -- (-5732.356) (-5734.974) [-5730.433] (-5733.273) * (-5727.025) (-5741.797) (-5743.863) [-5722.482] -- 0:00:07
           6800 -- [-5729.103] (-5741.732) (-5729.774) (-5730.896) * (-5723.102) (-5732.133) (-5743.598) [-5720.478] -- 0:00:07
           6900 -- (-5727.336) (-5744.062) [-5728.362] (-5732.675) * [-5720.983] (-5742.849) (-5743.789) (-5723.000) -- 0:00:07
           7000 -- (-5729.219) (-5743.354) (-5721.911) [-5733.457] * [-5719.641] (-5729.442) (-5741.570) (-5720.264) -- 0:00:07
    
          Average standard deviation of split frequencies: 0.000000
    
           7100 -- (-5725.926) (-5744.395) [-5722.051] (-5737.685) * [-5723.188] (-5737.467) (-5736.032) (-5724.888) -- 0:00:07
           7200 -- [-5724.995] (-5740.577) (-5726.545) (-5729.189) * (-5722.658) (-5735.505) (-5742.329) [-5722.496] -- 0:00:07
           7300 -- (-5720.723) (-5740.894) [-5727.993] (-5734.244) * (-5722.146) [-5729.589] (-5740.264) (-5719.175) -- 0:00:08
           7400 -- [-5724.088] (-5735.169) (-5729.361) (-5731.524) * [-5731.220] (-5735.183) (-5734.401) (-5725.564) -- 0:00:08
           7500 -- [-5731.686] (-5731.044) (-5731.096) (-5728.375) * (-5731.657) (-5730.538) (-5742.941) [-5727.495] -- 0:00:08
           7600 -- (-5735.450) (-5736.528) (-5731.226) [-5730.017] * (-5725.006) (-5725.554) (-5753.596) [-5725.495] -- 0:00:08
           7700 -- (-5735.852) [-5735.384] (-5733.932) (-5730.568) * (-5723.971) (-5729.865) (-5762.925) [-5723.454] -- 0:00:07
           7800 -- (-5748.008) (-5740.372) (-5726.248) [-5727.403] * [-5724.161] (-5724.334) (-5748.118) (-5728.353) -- 0:00:07
           7900 -- (-5734.400) (-5745.454) [-5729.636] (-5726.444) * (-5730.484) [-5723.185] (-5737.566) (-5723.638) -- 0:00:07
           8000 -- (-5732.447) (-5738.850) (-5729.379) [-5727.822] * [-5732.617] (-5727.593) (-5731.704) (-5723.106) -- 0:00:07
    
          Average standard deviation of split frequencies: 0.001288
    
           8100 -- (-5731.356) (-5747.804) [-5727.078] (-5726.831) * (-5724.882) [-5731.228] (-5733.489) (-5728.101) -- 0:00:07
           8200 -- (-5731.472) (-5736.757) [-5728.496] (-5725.339) * (-5729.369) (-5728.678) [-5734.024] (-5723.595) -- 0:00:07
           8300 -- [-5726.460] (-5735.922) (-5728.167) (-5725.463) * (-5728.678) (-5738.164) (-5737.129) [-5723.503] -- 0:00:07
           8400 -- (-5727.308) (-5734.638) [-5722.374] (-5726.209) * (-5731.491) (-5731.266) (-5741.444) [-5726.076] -- 0:00:06
           8500 -- [-5728.526] (-5728.409) (-5720.956) (-5728.743) * [-5731.772] (-5730.164) (-5736.938) (-5723.420) -- 0:00:06
           8600 -- [-5730.948] (-5736.118) (-5724.144) (-5734.690) * (-5732.452) [-5726.987] (-5737.855) (-5726.519) -- 0:00:06
           8700 -- (-5730.415) (-5738.253) [-5722.600] (-5729.769) * [-5731.669] (-5720.363) (-5736.516) (-5728.521) -- 0:00:06
           8800 -- (-5729.248) (-5738.865) [-5722.169] (-5730.117) * [-5725.273] (-5726.090) (-5731.341) (-5724.176) -- 0:00:06
           8900 -- (-5726.653) (-5733.359) [-5719.936] (-5729.965) * [-5725.700] (-5730.223) (-5729.042) (-5725.456) -- 0:00:06
           9000 -- (-5727.970) (-5738.407) [-5718.382] (-5733.511) * (-5724.181) (-5731.659) (-5725.156) [-5721.857] -- 0:00:06
    
          Average standard deviation of split frequencies: 0.003416
    
           9100 -- (-5733.742) (-5736.049) [-5717.877] (-5733.660) * (-5729.302) (-5737.230) [-5723.805] (-5720.952) -- 0:00:05
           9200 -- [-5728.301] (-5728.367) (-5721.674) (-5735.905) * (-5720.455) [-5729.103] (-5722.105) (-5719.566) -- 0:00:07
           9300 -- (-5725.124) [-5729.112] (-5725.097) (-5739.194) * (-5727.266) (-5731.509) (-5729.425) [-5723.434] -- 0:00:06
           9400 -- (-5728.962) (-5727.077) (-5727.328) [-5731.539] * (-5728.180) (-5726.306) (-5727.773) [-5724.941] -- 0:00:06
           9500 -- (-5731.309) (-5727.229) [-5729.576] (-5743.854) * (-5729.369) [-5726.771] (-5722.132) (-5724.279) -- 0:00:06
           9600 -- (-5728.629) (-5729.293) [-5723.028] (-5738.026) * (-5727.981) (-5731.623) (-5721.404) [-5723.404] -- 0:00:06
           9700 -- (-5727.223) [-5728.486] (-5721.253) (-5734.423) * (-5723.544) (-5735.606) [-5722.992] (-5730.065) -- 0:00:06
           9800 -- (-5728.647) (-5739.653) (-5722.437) [-5730.551] * (-5723.385) [-5729.190] (-5722.165) (-5727.606) -- 0:00:06
           9900 -- (-5733.271) (-5727.112) (-5722.945) [-5732.943] * [-5720.440] (-5738.046) (-5722.121) (-5728.761) -- 0:00:06
          10000 -- [-5724.244] (-5724.896) (-5725.675) (-5734.609) * (-5729.582) (-5726.249) [-5720.872] (-5722.705) -- 0:00:05
    
          Average standard deviation of split frequencies: 0.003101
    
          10100 -- (-5724.157) [-5723.210] (-5726.179) (-5734.683) * [-5719.682] (-5728.589) (-5724.028) (-5726.297) -- 0:00:05
          10200 -- [-5733.666] (-5719.074) (-5725.675) (-5724.655) * (-5721.781) (-5732.732) (-5730.891) [-5724.353] -- 0:00:05
          10300 -- (-5727.222) [-5720.048] (-5723.930) (-5725.123) * [-5720.222] (-5730.104) (-5728.465) (-5727.640) -- 0:00:05
          10400 -- (-5728.807) (-5723.392) (-5726.939) [-5725.544] * [-5721.831] (-5736.132) (-5722.696) (-5723.707) -- 0:00:05
          10500 -- (-5729.245) (-5727.352) (-5722.541) [-5720.705] * [-5723.611] (-5738.559) (-5725.977) (-5727.872) -- 0:00:05
          10600 -- (-5728.125) [-5726.940] (-5725.325) (-5724.342) * (-5726.198) (-5734.384) (-5725.811) [-5718.484] -- 0:00:05
          10700 -- [-5728.417] (-5729.826) (-5722.790) (-5727.697) * (-5735.328) (-5731.863) (-5727.866) [-5720.858] -- 0:00:05
          10800 -- (-5729.217) (-5731.352) (-5727.473) [-5726.737] * (-5728.411) (-5737.970) (-5730.322) [-5718.887] -- 0:00:05
          10900 -- (-5728.351) (-5725.164) [-5728.434] (-5723.290) * [-5724.112] (-5739.802) (-5731.035) (-5716.738) -- 0:00:05
          11000 -- [-5726.644] (-5729.785) (-5728.755) (-5721.014) * (-5727.551) (-5740.833) (-5729.206) [-5720.744] -- 0:00:05
    
          Average standard deviation of split frequencies: 0.002806
    
          11100 -- (-5725.898) [-5728.504] (-5733.987) (-5725.372) * (-5727.663) [-5733.888] (-5729.278) (-5722.583) -- 0:00:05
          11200 -- (-5726.204) [-5726.564] (-5732.169) (-5723.824) * (-5726.538) (-5733.998) (-5724.597) [-5726.003] -- 0:00:05
          11300 -- [-5723.598] (-5731.800) (-5726.879) (-5731.058) * (-5729.035) (-5731.549) (-5724.141) [-5727.369] -- 0:00:05
          11400 -- (-5733.726) (-5731.669) (-5719.781) [-5721.145] * (-5723.318) (-5731.530) (-5723.487) [-5727.898] -- 0:00:05
          11500 -- (-5731.119) (-5730.353) [-5723.195] (-5720.924) * [-5722.368] (-5728.799) (-5727.528) (-5726.534) -- 0:00:05
          11600 -- [-5726.144] (-5733.120) (-5729.423) (-5719.748) * [-5718.841] (-5726.964) (-5725.561) (-5723.426) -- 0:00:05
          11700 -- (-5730.752) (-5733.941) (-5732.855) [-5717.928] * [-5718.165] (-5730.009) (-5725.138) (-5721.283) -- 0:00:04
          11800 -- (-5728.014) (-5742.929) (-5730.604) [-5718.827] * (-5720.266) (-5730.980) (-5725.341) [-5722.231] -- 0:00:04
          11900 -- (-5727.664) (-5738.673) (-5733.307) [-5716.364] * (-5728.758) (-5730.281) [-5721.632] (-5727.691) -- 0:00:04
          12000 -- (-5726.047) (-5732.595) (-5727.744) [-5722.263] * (-5723.215) (-5734.435) [-5726.029] (-5727.281) -- 0:00:04
    
          Average standard deviation of split frequencies: 0.002590
    
          12100 -- (-5726.288) (-5730.652) (-5722.971) [-5722.828] * (-5734.546) (-5733.512) (-5728.783) [-5723.417] -- 0:00:04
          12200 -- [-5728.826] (-5732.320) (-5724.016) (-5724.106) * (-5738.128) [-5734.110] (-5730.156) (-5733.335) -- 0:00:04
          12300 -- [-5726.570] (-5729.378) (-5731.663) (-5719.011) * (-5722.844) (-5727.752) [-5730.246] (-5729.250) -- 0:00:04
          12400 -- (-5724.420) (-5735.834) (-5735.129) [-5723.694] * [-5722.841] (-5726.525) (-5725.039) (-5730.044) -- 0:00:04
          12500 -- (-5727.169) [-5728.016] (-5726.302) (-5724.769) * [-5722.448] (-5728.144) (-5725.520) (-5731.026) -- 0:00:04
          12600 -- [-5724.866] (-5732.918) (-5726.257) (-5722.382) * [-5723.640] (-5734.160) (-5724.119) (-5724.462) -- 0:00:04
          12700 -- (-5729.134) (-5731.359) [-5723.660] (-5721.842) * (-5723.252) (-5727.978) [-5722.724] (-5726.289) -- 0:00:04
          12800 -- (-5726.206) (-5726.073) (-5728.439) [-5720.454] * [-5721.778] (-5726.748) (-5726.569) (-5726.320) -- 0:00:04
          12900 -- (-5724.622) (-5727.780) (-5735.130) [-5722.155] * (-5723.028) (-5731.138) (-5726.616) [-5722.253] -- 0:00:04
          13000 -- [-5727.630] (-5727.297) (-5725.893) (-5726.248) * (-5727.274) (-5729.540) [-5725.944] (-5724.183) -- 0:00:04
    
          Average standard deviation of split frequencies: 0.002381
    
          13100 -- (-5727.883) (-5731.268) [-5724.696] (-5724.735) * [-5725.599] (-5731.204) (-5727.527) (-5723.951) -- 0:00:04
          13200 -- [-5725.493] (-5733.280) (-5723.330) (-5719.888) * (-5724.125) [-5723.531] (-5723.117) (-5723.497) -- 0:00:04
          13300 -- (-5729.488) (-5729.554) (-5724.119) [-5717.327] * (-5721.457) (-5728.072) [-5722.139] (-5723.659) -- 0:00:04
          13400 -- (-5727.202) (-5728.769) [-5720.874] (-5721.878) * [-5723.411] (-5724.947) (-5723.241) (-5729.030) -- 0:00:03
          13500 -- (-5724.352) [-5721.353] (-5720.628) (-5727.605) * [-5724.829] (-5723.802) (-5718.735) (-5727.873) -- 0:00:03
          13600 -- (-5723.094) (-5722.937) [-5725.685] (-5732.399) * (-5728.708) (-5726.918) [-5720.702] (-5729.503) -- 0:00:03
          13700 -- (-5722.157) (-5724.484) [-5725.012] (-5728.918) * (-5732.682) (-5727.996) (-5723.296) [-5727.647] -- 0:00:03
          13800 -- (-5724.166) (-5724.509) (-5725.131) [-5724.434] * (-5734.246) (-5724.340) [-5722.199] (-5727.311) -- 0:00:03
          13900 -- (-5721.148) [-5721.742] (-5721.678) (-5723.368) * (-5734.316) (-5729.147) (-5721.090) [-5725.904] -- 0:00:03
          14000 -- [-5725.191] (-5724.235) (-5719.271) (-5728.087) * (-5735.559) (-5729.418) (-5723.137) [-5722.112] -- 0:00:03
    
          Average standard deviation of split frequencies: 0.002224
    
          14100 -- (-5727.019) (-5727.087) [-5717.851] (-5728.516) * (-5734.647) (-5729.433) (-5723.271) [-5723.577] -- 0:00:03
          14200 -- (-5728.329) (-5732.788) [-5730.826] (-5730.769) * (-5732.764) (-5731.711) [-5725.028] (-5724.478) -- 0:00:03
          14300 -- [-5726.479] (-5731.187) (-5726.817) (-5729.979) * (-5731.186) (-5729.795) [-5728.732] (-5723.964) -- 0:00:03
          14400 -- (-5735.046) (-5728.304) [-5724.111] (-5725.234) * (-5726.544) [-5731.085] (-5735.704) (-5728.115) -- 0:00:03
          14500 -- (-5733.054) (-5730.056) (-5723.547) [-5720.209] * [-5724.752] (-5734.023) (-5732.399) (-5731.136) -- 0:00:03
          14600 -- (-5730.675) (-5728.118) [-5718.308] (-5718.651) * (-5725.421) (-5734.984) [-5724.174] (-5734.171) -- 0:00:03
          14700 -- (-5725.520) [-5727.222] (-5720.001) (-5724.093) * [-5726.582] (-5738.024) (-5720.803) (-5733.441) -- 0:00:03
          14800 -- (-5724.375) (-5724.579) [-5719.872] (-5725.143) * [-5726.744] (-5734.521) (-5734.460) (-5735.381) -- 0:00:03
          14900 -- (-5732.453) (-5727.545) [-5724.258] (-5727.275) * [-5724.848] (-5735.190) (-5731.800) (-5726.094) -- 0:00:03
          15000 -- (-5729.032) (-5722.217) [-5727.760] (-5728.980) * (-5727.988) (-5734.291) (-5727.607) [-5731.476] -- 0:00:02
    
          Average standard deviation of split frequencies: 0.002068
    
          15100 -- [-5720.209] (-5730.488) (-5722.212) (-5729.088) * (-5728.484) (-5737.380) [-5718.535] (-5732.240) -- 0:00:02
          15200 -- (-5723.864) [-5721.700] (-5727.543) (-5724.267) * (-5725.848) (-5738.252) (-5722.907) [-5725.388] -- 0:00:02
          15300 -- (-5727.619) (-5723.206) [-5730.946] (-5723.557) * (-5721.412) (-5737.113) [-5720.987] (-5724.669) -- 0:00:02
          15400 -- [-5723.398] (-5726.372) (-5728.613) (-5728.229) * (-5727.432) (-5728.078) (-5722.057) [-5723.987] -- 0:00:02
          15500 -- [-5723.734] (-5723.829) (-5727.772) (-5724.147) * (-5726.266) (-5730.143) (-5722.332) [-5723.289] -- 0:00:02
          15600 -- [-5724.702] (-5724.576) (-5730.947) (-5724.939) * (-5727.946) (-5732.079) (-5725.731) [-5724.010] -- 0:00:02
          15700 -- [-5722.058] (-5729.497) (-5723.821) (-5729.506) * (-5728.581) (-5726.102) (-5727.228) [-5723.301] -- 0:00:02
          15800 -- [-5722.394] (-5733.427) (-5723.961) (-5728.325) * (-5728.429) (-5732.508) (-5726.296) [-5720.551] -- 0:00:02
          15900 -- [-5724.730] (-5738.681) (-5724.078) (-5727.876) * (-5725.285) (-5732.078) [-5727.876] (-5719.378) -- 0:00:02
          16000 -- [-5722.884] (-5728.813) (-5721.145) (-5727.493) * (-5724.808) (-5728.492) [-5721.245] (-5718.454) -- 0:00:02
    
          Average standard deviation of split frequencies: 0.001948
    
          16100 -- (-5725.460) [-5724.601] (-5719.334) (-5729.304) * (-5724.611) (-5728.099) (-5721.162) [-5720.496] -- 0:00:02
          16200 -- [-5724.067] (-5724.590) (-5721.134) (-5728.971) * (-5725.966) (-5725.281) [-5721.671] (-5718.589) -- 0:00:02
          16300 -- (-5727.090) (-5724.897) [-5723.904] (-5727.716) * (-5725.550) (-5725.096) [-5723.224] (-5721.681) -- 0:00:02
          16400 -- [-5720.352] (-5723.872) (-5723.734) (-5724.691) * [-5721.419] (-5724.322) (-5721.467) (-5722.355) -- 0:00:02
          16500 -- [-5720.822] (-5727.588) (-5728.688) (-5734.791) * (-5719.909) (-5727.665) [-5721.710] (-5725.229) -- 0:00:02
          16600 -- (-5723.595) (-5727.379) (-5732.731) [-5724.297] * (-5719.634) (-5723.578) (-5720.189) [-5722.393] -- 0:00:02
          16700 -- (-5728.267) (-5730.854) (-5727.665) [-5721.596] * [-5722.610] (-5728.566) (-5722.739) (-5721.110) -- 0:00:01
          16800 -- (-5728.366) (-5726.402) (-5718.684) [-5719.133] * (-5719.329) (-5719.024) (-5729.729) [-5725.955] -- 0:00:01
          16900 -- (-5728.312) (-5724.313) [-5716.671] (-5722.797) * (-5720.096) (-5721.578) (-5724.473) [-5721.566] -- 0:00:01
          17000 -- [-5725.502] (-5730.826) (-5720.275) (-5720.601) * (-5717.420) (-5723.382) (-5726.781) [-5720.537] -- 0:00:01
    
          Average standard deviation of split frequencies: 0.001827
    
          17100 -- [-5726.051] (-5732.361) (-5722.877) (-5722.359) * (-5719.030) (-5728.770) (-5721.464) [-5729.847] -- 0:00:01
          17200 -- (-5724.356) (-5727.735) [-5722.299] (-5727.495) * (-5730.898) (-5730.152) [-5724.613] (-5724.609) -- 0:00:01
          17300 -- (-5721.737) (-5727.527) [-5723.220] (-5728.296) * (-5731.768) (-5723.878) [-5723.248] (-5726.244) -- 0:00:01
          17400 -- (-5727.493) (-5720.878) (-5723.109) [-5725.351] * (-5733.123) [-5722.771] (-5724.482) (-5726.217) -- 0:00:01
          17500 -- (-5728.094) (-5728.453) [-5722.660] (-5727.637) * (-5729.610) [-5722.723] (-5728.808) (-5726.949) -- 0:00:01
          17600 -- (-5737.867) (-5731.754) [-5723.410] (-5727.462) * (-5732.245) (-5729.874) (-5722.398) [-5719.713] -- 0:00:01
          17700 -- (-5731.412) (-5729.410) (-5724.486) [-5729.646] * (-5725.761) (-5724.526) [-5719.321] (-5722.213) -- 0:00:01
          17800 -- (-5729.561) (-5735.448) [-5724.403] (-5725.724) * (-5727.323) (-5729.855) [-5723.846] (-5722.452) -- 0:00:01
          17900 -- (-5729.244) [-5733.107] (-5721.230) (-5726.686) * (-5731.273) (-5718.250) [-5724.316] (-5731.280) -- 0:00:01
          18000 -- (-5728.474) [-5732.764] (-5724.433) (-5729.955) * (-5733.984) [-5718.379] (-5727.867) (-5724.729) -- 0:00:01
    
          Average standard deviation of split frequencies: 0.001733
    
          18100 -- (-5724.311) (-5727.588) [-5721.631] (-5726.007) * (-5742.036) [-5717.716] (-5730.041) (-5742.617) -- 0:00:01
          18200 -- [-5725.103] (-5728.252) (-5724.643) (-5727.306) * (-5738.368) [-5723.620] (-5726.772) (-5733.643) -- 0:00:00
          18300 -- [-5727.175] (-5727.760) (-5721.996) (-5727.216) * (-5733.767) (-5728.476) [-5732.986] (-5734.396) -- 0:00:01
          18400 -- (-5727.940) [-5730.007] (-5726.464) (-5725.918) * (-5724.314) [-5726.972] (-5730.050) (-5733.673) -- 0:00:00
          18500 -- (-5732.148) [-5728.923] (-5731.088) (-5725.802) * (-5724.681) [-5722.953] (-5730.904) (-5738.267) -- 0:00:00
          18600 -- (-5730.061) (-5728.293) (-5725.953) [-5725.179] * (-5725.012) [-5725.127] (-5730.579) (-5739.546) -- 0:00:00
          18700 -- (-5730.412) (-5726.046) (-5729.756) [-5724.259] * [-5725.384] (-5731.561) (-5727.154) (-5735.943) -- 0:00:00
          18800 -- [-5734.164] (-5727.731) (-5722.302) (-5726.814) * [-5723.014] (-5727.316) (-5731.566) (-5735.216) -- 0:00:00
          18900 -- (-5732.346) [-5723.646] (-5730.803) (-5728.561) * (-5728.609) [-5726.501] (-5729.409) (-5729.783) -- 0:00:00
          19000 -- (-5731.834) [-5724.578] (-5723.742) (-5725.865) * (-5725.371) (-5725.742) (-5729.768) [-5724.773] -- 0:00:00
    
          Average standard deviation of split frequencies: 0.002182
    
          19100 -- (-5724.895) (-5726.495) (-5725.248) [-5725.703] * (-5721.804) [-5729.159] (-5732.897) (-5719.242) -- 0:00:00
          19200 -- (-5725.332) (-5730.684) (-5728.151) [-5726.269] * (-5724.323) (-5726.969) (-5728.220) [-5729.454] -- 0:00:00
          19300 -- (-5723.558) (-5721.449) (-5733.354) [-5728.800] * [-5724.344] (-5719.856) (-5731.379) (-5720.027) -- 0:00:00
          19400 -- (-5727.556) [-5719.698] (-5729.590) (-5726.735) * [-5724.016] (-5721.150) (-5730.142) (-5724.995) -- 0:00:00
          19500 -- [-5724.879] (-5724.920) (-5726.294) (-5724.530) * (-5734.605) (-5721.787) [-5728.476] (-5725.838) -- 0:00:00
          19600 -- (-5727.922) (-5735.407) [-5727.039] (-5720.444) * [-5732.471] (-5727.823) (-5733.148) (-5720.212) -- 0:00:00
          19700 -- [-5724.907] (-5733.385) (-5720.578) (-5722.213) * (-5732.583) (-5726.699) (-5731.873) [-5719.494] -- 0:00:00
          19800 -- (-5729.590) (-5733.611) (-5721.569) [-5718.356] * (-5729.012) (-5724.126) (-5734.212) [-5720.428] -- 0:00:00
          19900 -- (-5733.810) (-5730.706) [-5722.343] (-5726.957) * (-5729.770) (-5726.371) (-5732.847) [-5724.308] -- 0:00:00
          20000 -- (-5727.230) (-5732.022) [-5726.373] (-5733.094) * (-5726.837) (-5721.051) (-5735.728) [-5723.288] -- 0:00:00
    
          Average standard deviation of split frequencies: 0.002081
    
          Analysis completed in 12 seconds
          Analysis used 11.20 seconds of CPU time
          Likelihood of best state for "cold" chain of run 1 was -5715.69
          Likelihood of best state for "cold" chain of run 2 was -5715.69
    
          Acceptance rates for the moves in the "cold" chain of run 1:
             With prob.   (last 100)   chain accepted proposals by move
                28.7 %     ( 32 %)     Dirichlet(Revmat)
                55.7 %     ( 51 %)     Slider(Revmat)
                18.6 %     ( 20 %)     Dirichlet(Pi)
                21.3 %     ( 20 %)     Slider(Pi)
                39.3 %     ( 38 %)     Multiplier(Alpha)
                66.5 %     ( 64 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.3 %     (  1 %)     ExtTBR(Tau,V)
                 0.4 %     (  0 %)     NNI(Tau,V)
                 0.4 %     (  0 %)     ParsSPR(Tau,V)
                36.4 %     ( 26 %)     Multiplier(V)
                24.4 %     ( 27 %)     Nodeslider(V)
                14.8 %     ( 16 %)     TLMultiplier(V)
    
          Acceptance rates for the moves in the "cold" chain of run 2:
             With prob.   (last 100)   chain accepted proposals by move
                29.4 %     ( 36 %)     Dirichlet(Revmat)
                60.3 %     ( 61 %)     Slider(Revmat)
                19.1 %     ( 26 %)     Dirichlet(Pi)
                20.1 %     ( 18 %)     Slider(Pi)
                35.7 %     ( 37 %)     Multiplier(Alpha)
                65.1 %     ( 72 %)     Slider(Pinvar)
                 0.7 %     (  0 %)     ExtSPR(Tau,V)
                 0.2 %     (  0 %)     ExtTBR(Tau,V)
                 0.1 %     (  1 %)     NNI(Tau,V)
                 0.7 %     (  0 %)     ParsSPR(Tau,V)
                36.7 %     ( 28 %)     Multiplier(V)
                25.9 %     ( 23 %)     Nodeslider(V)
                12.5 %     ( 13 %)     TLMultiplier(V)
    
          Chain swap information for run 1:
    
                     1     2     3     4 
               --------------------------
             1 |        0.67  0.44  0.31 
             2 |  3391        0.67  0.46 
             3 |  3355  3244        0.70 
             4 |  3310  3337  3363       
    
          Chain swap information for run 2:
    
                     1     2     3     4 
               --------------------------
             1 |        0.66  0.45  0.26 
             2 |  3214        0.66  0.42 
             3 |  3352  3314        0.67 
             4 |  3348  3372  3400       
    
          Upper diagonal: Proportion of successful state exchanges between chains
          Lower diagonal: Number of attempted state exchanges between chains
    
          Chain information:
    
            ID -- Heat 
           -----------
             1 -- 1.00  (cold chain)
             2 -- 0.91 
             3 -- 0.83 
             4 -- 0.77 
    
          Heat = 1 / (1 + T * (ID - 1))
             (where T = 0.10 is the temperature and ID is the chain number)
    
          Summarizing parameters in files primates.nex.run1.p and primates.nex.run2.p
          Writing summary statistics to file primates.nex.pstat
          Using relative burnin ('relburnin=yes'), discarding the first 25 % of samples
    
          Below are rough plots of the generation (x-axis) versus the log   
          probability of observing the data (y-axis). You can use these     
          graphs to determine what the burn in for your analysis should be. 
          When the log probability starts to plateau you may be at station- 
          arity. Sample trees and parameters after the log probability      
          plateaus. Of course, this is not a guarantee that you are at sta- 
          tionarity. Also examine the convergence diagnostics provided by   
          the 'sump' and 'sumt' commands for all the parameters in your     
          model. Remember that the burn in is the number of samples to dis- 
          card. There are a total of ngen / samplefreq samples taken during 
          a MCMC analysis.                                                  
    
          Overlay plot for both runs:
          (1 = Run number 1; 2 = Run number 2; * = Both runs)
    
          +------------------------------------------------------------+ -5717.60
          |                           1                   1            |
          |                          2      1                  2       |
          |       2       1     22                     2     2         |
          |        2       1   2  2 1 2   *      11     **            1|
          |     2               1    1   2  2 12   12*1     2         2|
          |           2 *   22         1     *21      21  211 2  22 *  |
          |          2    22  2  1      11 *    1222       2 1     1 1 |
          |    2 1 11        1 1   2    2           1          1 1   2 |
          | 11         1 1        112  2                           2   |
          |     121   1                                       1 1 1    |
          |   1     2    2  1                   2               2      |
          |2   1              1                                        |
          |          1 2                                               |
          |1 22                                                        |
          | 2                                                          |
          +------+-----+-----+-----+-----+-----+-----+-----+-----+-----+ -5735.61
          ^                                                            ^
          5000                                                         20000
    
          Overwriting file "primates.nex.lstat"
    
          Estimated marginal likelihoods for runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             (Use the harmonic mean for Bayes factor comparisons of models)
    
             (Values are saved to the file primates.nex.lstat)
    
          Run   Arithmetic mean   Harmonic mean
          --------------------------------------
            1      -5720.09         -5736.73
            2      -5721.00         -5737.83
          --------------------------------------
          TOTAL    -5720.44         -5737.42
          --------------------------------------
    
    
          Model parameter summaries over the runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             Summaries are based on a total of 302 samples from 2 runs.
             Each run produced 201 samples of which 151 samples were included.
             Parameter summaries saved to file "primates.nex.pstat".
          Overwriting file "primates.nex.pstat"
    
                                                95% HPD Interval
                                              --------------------
          Parameter      Mean      Variance     Lower       Upper       Median    min ESS*  avg ESS    PSRF+ 
          --------------------------------------------------------------------------------------------------
          TL          3.154522    0.092039    2.652347    3.822248    3.119184     41.11     53.77    1.003
          r(A<->C)    0.044178    0.000071    0.028538    0.057435    0.045346     23.62     66.64    1.022
          r(A<->G)    0.463178    0.003224    0.370480    0.573550    0.462748     22.26     23.19    1.098
          r(A<->T)    0.036422    0.000075    0.023274    0.054136    0.034683     59.70     64.62    0.998
          r(C<->G)    0.027169    0.000288    0.003515    0.064507    0.023379     14.44     44.97    1.000
          r(C<->T)    0.405718    0.002445    0.327679    0.501749    0.410502     25.95     88.47    1.093
          r(G<->T)    0.023335    0.000299    0.000066    0.057489    0.019428      7.65     79.33    0.997
          pi(A)       0.357481    0.000150    0.333597    0.379789    0.356375     12.25     33.80    1.002
          pi(C)       0.318275    0.000124    0.296422    0.340439    0.317913     49.18     50.04    0.998
          pi(G)       0.082760    0.000061    0.068573    0.096949    0.083981     31.17     81.53    1.010
          pi(T)       0.241484    0.000111    0.220325    0.259177    0.241658     22.92     47.48    1.012
          alpha       0.600950    0.027349    0.369844    0.906253    0.566067     19.43     23.00    1.000
          pinvar      0.149195    0.006025    0.009223    0.264142    0.154388     15.65     22.46    0.999
          --------------------------------------------------------------------------------------------------
          * Convergence diagnostic (ESS = Estimated Sample Size); min and avg values
            correspond to minimal and average ESS among runs. 
            ESS value below 100 may indicate that the parameter is undersampled. 
          + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
            and Rubin, 1992) should approach 1.0 as runs converge.
    
    
       Summarizing trees in files "primates.nex.run1.t" and "primates.nex.run2.t"
       Using relative burnin ('relburnin=yes'), discarding the first 25 % of sampled trees
       Writing statistics to files primates.nex.<parts|tstat|vstat|trprobs|con>
       Examining first file ...
       Found one tree block in file "primates.nex.run1.t" with 201 trees in last block
       Expecting the same number of trees in the last tree block of all files
    
       Tree reading status:
    
       0      10      20      30      40      50      60      70      80      90     100
       v-------v-------v-------v-------v-------v-------v-------v-------v-------v-------v
       *********************************************************************************
    
       Read a total of 402 trees in 2 files (sampling 302 of them)
          (Each file contained 201 trees of which 151 were sampled)
       Overwriting file "primates.nex.parts"
       Overwriting file "primates.nex.tstat"
       Overwriting file "primates.nex.vstat"
       Overwriting file "primates.nex.con.tre"
       Overwriting file "primates.nex.trprobs"
                                                                                       
       General explanation:                                                          
                                                                                       
       In an unrooted tree, a taxon bipartition (split) is specified by removing a   
       branch, thereby dividing the species into those to the left and those to the  
       right of the branch. Here, taxa to one side of the removed branch are denoted 
       '.' and those to the other side are denoted '*'. Specifically, the '.' symbol 
       is used for the taxa on the same side as the outgroup.                        
                                                                                       
       In a rooted or clock tree, the tree is rooted using the model and not by      
       reference to an outgroup. Each bipartition therefore corresponds to a clade,  
       that is, a group that includes all the descendants of a particular branch in  
       the tree.  Taxa that are included in each clade are denoted using '*', and    
       taxa that are not included are denoted using the '.' symbol.                  
                                                                                       
       The output first includes a key to all the bipartitions with frequency larger 
       or equual to (Minpartfreq) in at least one run. Minpartfreq is a parameter to 
       sumt command and currently it is set to 0.10.  This is followed by a table  
       with statistics for the informative bipartitions (those including at least    
       two taxa), sorted from highest to lowest probability. For each bipartition,   
       the table gives the number of times the partition or split was observed in all
       runs (#obs) and the posterior probability of the bipartition (Probab.), which 
       is the same as the split frequency. If several runs are summarized, this is   
       followed by the minimum split frequency (Min(s)), the maximum frequency       
       (Max(s)), and the standard deviation of frequencies (Stddev(s)) across runs.  
       The latter value should approach 0 for all bipartitions as MCMC runs converge.
                                                                                       
       This is followed by a table summarizing branch lengths, node heights (if a    
       clock model was used) and relaxed clock parameters (if a relaxed clock model  
       was used). The mean, variance, and 95 % credible interval are given for each 
       of these parameters. If several runs are summarized, the potential scale      
       reduction factor (PSRF) is also given; it should approach 1 as runs converge. 
       Node heights will take calibration points into account, if such points were   
       used in the analysis.                                                         
                                                                                     
       Note that Stddev may be unreliable if the partition is not present in all     
       runs (the last column indicates the number of runs that sampled the partition 
       if more than one run is summarized). The PSRF is not calculated at all if     
       the partition is not present in all runs.The PSRF is also sensitive to small  
       sample sizes and it should only be considered a rough guide to convergence    
       since some of the assumptions allowing one to interpret it as a true potential
       scale reduction factor are violated in MrBayes.                               
                                                                                     
       List of taxa in bipartitions:                                                 
                                                                                       
          1 -- Tarsius_syrichta
          2 -- Lemur_catta
          3 -- Homo_sapiens
          4 -- Pan
          5 -- Gorilla
          6 -- Pongo
          7 -- Hylobates
          8 -- Macaca_fuscata
          9 -- M_mulatta
         10 -- M_fascicularis
         11 -- M_sylvanus
         12 -- Saimiri_sciureus
    
       Key to taxon bipartitions (saved to file "primates.nex.parts"):
    
       ID -- Partition
       ------------------
        1 -- .***********
        2 -- .*..........
        3 -- ..*.........
        4 -- ...*........
        5 -- ....*.......
        6 -- .....*......
        7 -- ......*.....
        8 -- .......*....
        9 -- ........*...
       10 -- .........*..
       11 -- ..........*.
       12 -- ...........*
       13 -- ..**********
       14 -- ..***.......
       15 -- ..**........
       16 -- .......****.
       17 -- ..*********.
       18 -- .......**...
       19 -- ..*****.....
       20 -- .......***..
       21 -- ..****......
       ------------------
    
       Summary statistics for informative taxon bipartitions
          (saved to file "primates.nex.tstat"):
    
       ID   #obs    Probab.     Sd(s)+      Min(s)      Max(s)   Nruns 
       ----------------------------------------------------------------
       13   302    1.000000    0.000000    1.000000    1.000000    2
       14   302    1.000000    0.000000    1.000000    1.000000    2
       15   302    1.000000    0.000000    1.000000    1.000000    2
       16   302    1.000000    0.000000    1.000000    1.000000    2
       17   302    1.000000    0.000000    1.000000    1.000000    2
       18   302    1.000000    0.000000    1.000000    1.000000    2
       19   302    1.000000    0.000000    1.000000    1.000000    2
       20   301    0.996689    0.004683    0.993377    1.000000    2
       21   299    0.990066    0.014048    0.980132    1.000000    2
       ----------------------------------------------------------------
       + Convergence diagnostic (standard deviation of split frequencies)
         should approach 0.0 as runs converge.
    
    
       Summary statistics for branch and node parameters
          (saved to file "primates.nex.vstat"):
    
                                               95% HPD Interval
                                             --------------------
       Parameter      Mean       Variance     Lower       Upper       Median     PSRF+  Nruns
       --------------------------------------------------------------------------------------
       length[1]     0.529816    0.008358    0.374652    0.702121    0.530373    0.999    2
       length[2]     0.371217    0.005333    0.251146    0.518802    0.367906    1.018    2
       length[3]     0.051741    0.000123    0.029578    0.072477    0.052103    0.997    2
       length[4]     0.062443    0.000191    0.035207    0.086606    0.062984    0.999    2
       length[5]     0.059864    0.000234    0.033874    0.090400    0.058900    1.002    2
       length[6]     0.156084    0.000909    0.102030    0.211592    0.152625    1.003    2
       length[7]     0.180860    0.000974    0.121118    0.236905    0.178472    0.997    2
       length[8]     0.017937    0.000031    0.007384    0.027798    0.018052    0.998    2
       length[9]     0.024065    0.000046    0.012039    0.036162    0.023029    0.998    2
       length[10]    0.057715    0.000141    0.036406    0.081777    0.056218    1.010    2
       length[11]    0.072994    0.000402    0.038190    0.113820    0.070465    0.997    2
       length[12]    0.467169    0.006317    0.297993    0.619217    0.463612    1.000    2
       length[13]    0.298532    0.005446    0.186894    0.452336    0.291022    0.997    2
       length[14]    0.088743    0.000479    0.051635    0.132529    0.087175    0.997    2
       length[15]    0.032147    0.000144    0.008858    0.052908    0.032248    0.998    2
       length[16]    0.274185    0.002558    0.170827    0.366283    0.270860    0.998    2
       length[17]    0.125452    0.002245    0.038333    0.206828    0.119914    0.997    2
       length[18]    0.038049    0.000119    0.018743    0.059746    0.037937    1.014    2
       length[19]    0.136297    0.001361    0.075354    0.209812    0.132133    1.011    2
       length[20]    0.050378    0.000310    0.016271    0.083181    0.049334    1.011    2
       length[21]    0.059537    0.000496    0.014241    0.099377    0.057869    0.997    2
       --------------------------------------------------------------------------------------
       + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
         and Rubin, 1992) should approach 1.0 as runs converge. NA is reported when
         deviation of parameter values within all runs is 0 or when a parameter
         value (a branch length, for instance) is not sampled in all runs.
    
    
       Summary statistics for partitions with frequency >= 0.10 in at least one run:
           Average standard deviation of split frequencies = 0.002081
           Maximum standard deviation of split frequencies = 0.014048
           Average PSRF for parameter values (excluding NA and >10.0) = 1.002
           Maximum PSRF for parameter values = 1.018
    
    
       Clade credibility values:
    
       /---------------------------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |---------------------------------------------------------- Lemur_catta (2)
       |                                                                               
       |                                                 /-------- Homo_sapiens (3)
       |                                        /---100--+                             
       |                                        |        \-------- Pan (4)
       |                                /--100--+                                      
       |                                |       \----------------- Gorilla (5)
       |                        /---99--+                                              
       +                        |       \------------------------- Pongo (6)
       |                /--100--+                                                      
       |                |       \--------------------------------- Hylobates (7)
       |                |                                                              
       |                |                                /-------- Macaca_fuscata (8)
       |       /---100--+                       /---100--+                             
       |       |        |                       |        \-------- M_mulatta (9)
       |       |        |               /--100--+                                      
       |       |        |               |       \----------------- M_fascicularis (10)
       \--100--+        \------100------+                                              
               |                        \------------------------- M_sylvanus (11)
               |                                                                       
               \-------------------------------------------------- Saimiri_sciure~ (12)
                                                                                       
    
       Phylogram (based on average branch lengths):
    
       /---------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |---------------------------- Lemur_catta (2)
       |                                                                               
       |                                                     /---- Homo_sapiens (3)
       |                                                   /-+                         
       |                                                   | \----- Pan (4)
       |                                            /------+                           
       |                                            |      \---- Gorilla (5)
       |                                        /---+                                  
       +                                        |   \----------- Pongo (6)
       |                              /---------+                                      
       |                              |         \------------- Hylobates (7)
       |                              |                                                
       |                              |                          /- Macaca_fuscata (8)
       |                     /--------+                       /--+                     
       |                     |        |                       |  \- M_mulatta (9)
       |                     |        |                   /---+                        
       |                     |        |                   |   \---- M_fascicularis (10)
       \---------------------+        \-------------------+                            
                             |                            \----- M_sylvanus (11)
                             |                                                         
                             \----------------------------------- Saimiri_sciure~ (12)
                                                                                       
       |-------------| 0.200 expected changes per site
    
                                                                               Calculating tree probabilities...
    
       Credible sets of trees (3 trees sampled):
          99 % credible set contains 2 trees
    
       Terminating log output
       Exiting mrbayes block
       Reached end of file
    
       Tasks completed, exiting program because mode is noninteractive
       To return control to the command line after completion of file processing, 
       set mode to interactive with 'mb -i <filename>' (i is for interactive)
       or use 'set mode=interactive'
    
    
    real	0m12.637s
    user	0m12.472s
    sys	0m0.152s


En mi caso no corre con mrbayes de anaconda, así que procedo a desactivar y correr con el paquete nativo


```bash
conda deactivate
```


```bash
time mb-mpi myfile.nex
```

    
    
                                MrBayes 3.2.7a x86_64
    
                          (Bayesian Analysis of Phylogeny)
    
                  Distributed under the GNU General Public License
    
    
                   Type "help" or "help <command>" for information
                         on the commands that are available.
    
                       Type "about" for authorship and general
                           information about the program.
    
    
    
       Executing file "myfile.nex"
       UNIX line termination
       Longest line length = 97
       Parsing file
       Reading mrbayes block
          Logging screen output to file "test.log"
          Setting autoclose to yes
          Setting nowarnings to yes
          Setting usebeagle to yes
          Setting beagledevice to CPU
          Setting beagleprecision to double
          Setting beaglescaling to Dynamic
          Setting beaglesse to Yes
    
          Executing file "primates.nex"...
    
       DOS line termination
       Longest line length = 920
       Parsing file
       Expecting NEXUS formatted file
       Reading data block
          Allocated taxon set
          Allocated matrix
          Defining new matrix with 12 taxa and 898 characters
          Data is Dna
          Data matrix is not interleaved
          Gaps coded as -
          Taxon  1 -> Tarsius_syrichta
          Taxon  2 -> Lemur_catta
          Taxon  3 -> Homo_sapiens
          Taxon  4 -> Pan
          Taxon  5 -> Gorilla
          Taxon  6 -> Pongo
          Taxon  7 -> Hylobates
          Taxon  8 -> Macaca_fuscata
          Taxon  9 -> M_mulatta
          Taxon 10 -> M_fascicularis
          Taxon 11 -> M_sylvanus
          Taxon 12 -> Saimiri_sciureus
          Successfully read matrix
          Setting default partition (does not divide up characters)
          Setting model defaults
          Seed (for generating default start values) = 1677097779
          Setting output file names to "primates.nex.run<i>.<p|t>"
       Exiting data block
       Reached end of file
    
       Returning execution to calling file ...
    
          Setting Nst to 6
          Setting Rates to Invgamma
          Successfully set likelihood model parameters
    
    
                                MrBayes 3.2.7a x86_64
    
                          (Bayesian Analysis of Phylogeny)
    
                  Distributed under the GNU General Public License
    
    
                   Type "help" or "help <command>" for information
                         on the commands that are available.
    
                       Type "about" for authorship and general
                           information about the program.
    
    
    
       Executing file "myfile.nex"
       UNIX line termination
       Longest line length = 97
       Parsing file
       Reading mrbayes block
          Logging screen output to file "test.log"
          Setting autoclose to yes
          Setting nowarnings to yes
          Setting usebeagle to yes
          Setting beagledevice to CPU
          Setting beagleprecision to double
          Setting beaglescaling to Dynamic
          Setting beaglesse to Yes
    
          Executing file "primates.nex"...
    
       DOS line termination
       Longest line length = 920
       Parsing file
       Expecting NEXUS formatted file
       Reading data block
          Allocated taxon set
          Allocated matrix
          Defining new matrix with 12 taxa and 898 characters
          Data is Dna
          Data matrix is not interleaved
          Gaps coded as -
          Taxon  1 -> Tarsius_syrichta
          Taxon  2 -> Lemur_catta
          Taxon  3 -> Homo_sapiens
          Taxon  4 -> Pan
          Taxon  5 -> Gorilla
          Taxon  6 -> Pongo
          Taxon  7 -> Hylobates
          Taxon  8 -> Macaca_fuscata
          Taxon  9 -> M_mulatta
    
    
                                MrBayes 3.2.7a x86_64
    
                          (Bayesian Analysis of Phylogeny)
    
                  Distributed under the GNU General Public License
    
    
                   Type "help" or "help <command>" for information
          Taxon 10 -> M_fascicularis
                         on the commands that are available.
    
                       Type "about" for authorship and general
                           information about the program.
    
    
    
          Taxon 11 -> M_sylvanus
       Executing file "myfile.nex"
       UNIX line termination
       Longest line length = 97
       Parsing file
       Reading mrbayes block
          Taxon 12 -> Saimiri_sciureus
          Logging screen output to file "test.log"
          Setting autoclose to yes
          Setting nowarnings to yes
          Setting usebeagle to yes
          Setting beagledevice to CPU
          Setting beagleprecision to double
          Setting beaglescaling to Dynamic
          Setting beaglesse to Yes
    
          Executing file "primates.nex"...
    
       DOS line termination
          Successfully read matrix
          Setting default partition (does not divide up characters)
          Setting model defaults
          Seed (for generating default start values) = 1677097779
       Longest line length = 920
       Parsing file
          Setting number of chains to 4
          Setting number of runs to 2
          Setting number of generations to 20000
       Expecting NEXUS formatted file
       Reading data block
          Setting sample frequency to 100
          Setting print frequency to 100
          Allocated taxon set
          Setting diagnosing frequency to 1000
          Setting chain output file names to "primates.nex.run<i>.<p/t>"
          Running Markov chain
          MCMC stamp = 5365503958
          Seed = 1806763618
          Swapseed = 1677097779
          Model settings:
    
             Data not partitioned --
                Datatype  = DNA
                Nucmodel  = 4by4
                Nst       = 6
                            Substitution rates, expressed as proportions
                            of the rate sum, have a Dirichlet prior
                            (1.00,1.00,1.00,1.00,1.00,1.00)
                Covarion  = No
                # States  = 4
                            State frequencies have a Dirichlet prior
                            (1.00,1.00,1.00,1.00)
          Allocated matrix
          Defining new matrix with 12 taxa and 898 characters
                Rates     = Invgamma
                            The distribution is approximated using 4 categories.
          Data is Dna
          Data matrix is not interleaved
                            Shape parameter is exponentially
                            distributed with parameter (1.00).
          Gaps coded as -
                            Proportion of invariable sites is uniformly dist-
                            ributed on the interval (0.00,1.00).
    
          Active parameters: 
    
             Parameters
             ---------------------
             Revmat                  Taxon  1 -> Tarsius_syrichta
      1
             Statefreq           2
             Shape               3
             Pinvar              4
             Ratemultiplier      5
             Topology            6      Taxon  2 -> Lemur_catta
    
             Brlens              7
             ---------------------
    
             1 --  Parameter  = Revmat
                   Type       = Rates of reversible rate matrix
                   Prior      = Dirichlet(1.00,1.00,1.00,1.00,1.00,1.00)
    
             2 --  Parameter  = Pi
                   Type       = Stationary state frequencies
                   Prior      = Dirichlet
    
             3 --  Parameter  = Alpha
          Taxon  3 -> Homo_sapiens
                   Type       = Shape of scaled gamma distribution of site rates
                   Prior      = Exponential(1.00)
    
             4 --  Parameter  = Pinvar
                   Type       = Proportion of invariable sites
                   Prior      = Uniform(0.00,1.00)
    
             5 --  Parameter  = Ratemultiplier
                   Type       = Partition-specific rate multiplier
                   Prior      = Fixed(1.0)
    
             6 --  Parameter  = Tau
                   Type       = Topology
                   Prior      = All topologies equally probable a priori
          Taxon  4 -> Pan
                   Subparam.  = V
    
             7 --  Parameter  = V
                   Type       = Branch lengths
                   Prior      = Unconstrained:GammaDir(1.0,0.1000,1.0,1.0)
    
    
    
          The MCMC sampler will use the following moves:
             With prob.  Chain will use move
          Taxon  5 -> Gorilla
                0.93 %   Dirichlet(Revmat)
                0.93 %   Slider(Revmat)
                0.93 %   Dirichlet(Pi)
                0.93 %   Slider(Pi)
                1.85 %   Multiplier(Alpha)
                1.85 %   Slider(Pinvar)
                9.26 %   ExtSPR(Tau,V)
                9.26 %   ExtTBR(Tau,V)
                9.26 %   NNI(Tau,V)
                9.26 %   ParsSPR(Tau,V)
               37.04 %   Multiplier(V)
          Taxon  6 -> Pongo
               12.96 %   Nodeslider(V)
                5.56 %   TLMultiplier(V)
    
          Taxon  7 -> Hylobates
          Taxon  8 -> Macaca_fuscata
          Setting output file names to "primates.nex.run<i>.<p|t>"
       Exiting data block
       Reached end of file
    
       Returning execution to calling file ...
    
          Taxon  9 -> M_mulatta
          Setting Nst to 6
          Setting Rates to Invgamma
          Division 1 has 413 unique site patterns
          Initializing conditional likelihoods
          Successfully set likelihood model parameters
    
          Running benchmarks to automatically select fastest BEAGLE resource...       Taxon 10 -> M_fascicularis
          Taxon 11 -> M_sylvanus
          Taxon 12 -> Saimiri_sciureus
          Successfully read matrix
          Setting default partition (does not divide up characters)
          Setting model defaults
          Seed (for generating default start values) = 1677097779
    
    
                                MrBayes 3.2.7a x86_64
    
                          (Bayesian Analysis of Phylogeny)
    
                  Distributed under the GNU General Public License
    
    
                   Type "help" or "help <command>" for information
                         on the commands that are available.
    
                       Type "about" for authorship and general
                           information about the program.
    
    
    
       Executing file "myfile.nex"
       UNIX line termination
       Longest line length = 97
       Parsing file
       Reading mrbayes block
          Logging screen output to file "test.log"
          Setting autoclose to yes
          Setting nowarnings to yes
          Setting usebeagle to yes
          Setting beagledevice to CPU
          Setting beagleprecision to double
          Setting beaglescaling to Dynamic
          Setting beaglesse to Yes
    
          Executing file "primates.nex"...
    
       DOS line termination
          Setting number of chains to 4
          Setting number of runs to 2
          Setting number of generations to 20000
          Setting sample frequency to 100
          Setting print frequency to 100
          Setting diagnosing frequency to 1000
          Setting chain output file names to "primates.nex.run<i>.<p/t>"
          Running Markov chain
          MCMC stamp = 5365503958
          Seed = 1806763618
          Swapseed = 1677097779
          Model settings:
    
       Longest line length = 920
       Parsing file
             Data not partitioned --
                Datatype  = DNA
                Nucmodel  = 4by4
                Nst       = 6
                            Substitution rates, expressed as proportions
       Expecting NEXUS formatted file
                            of the rate sum, have a Dirichlet prior
       Reading data block
                            (1.00,1.00,1.00,1.00,1.00,1.00)
                Covarion  = No
                # States  = 4
                            State frequencies have a Dirichlet prior
                            (1.00,1.00,1.00,1.00)
                Rates     = Invgamma
          Allocated taxon set
                            The distribution is approximated using 4 categories.
                            Shape parameter is exponentially
                            distributed with parameter (1.00).
                            Proportion of invariable sites is uniformly dist-
                            ributed on the interval (0.00,1.00).
    
          Active parameters: 
    
             Parameters
             ---------------------
             Revmat              1
             Statefreq           2
             Shape               3
             Pinvar              4
             Ratemultiplier      5
             Topology                Allocated matrix
          Defining new matrix with 12 taxa and 898 characters
      6
             Brlens              7
             ---------------------
    
          Data is Dna
          Data matrix is not interleaved
          Gaps coded as -
             1 --  Parameter  = Revmat
                   Type       = Rates of reversible rate matrix
                   Prior      = Dirichlet(1.00,1.00,1.00,1.00,1.00,1.00)
    
             2 --  Parameter  = Pi
                   Type       = Stationary state frequencies
                   Prior      = Dirichlet
    
             3 --  Parameter  = Alpha
          Taxon  1 -> Tarsius_syrichta
                   Type       = Shape of scaled gamma distribution of site rates
                   Prior      = Exponential(1.00)
    
             4 --  Parameter  = Pinvar
                   Type       = Proportion of invariable sites
                   Prior      = Uniform(0.00,1.00)
    
             5 --  Parameter  = Ratemultiplier
                   Type       = Partition-specific rate multiplier
                   Prior      = Fixed(1.0)
    
             6 --  Parameter  = Tau
                   Type       = Topology
          Setting output file names to "primates.nex.run<i>.<p|t>"
                   Prior      = All topologies equally probable a priori
                   Subparam.  = V
    
       Exiting data block
       Reached end of file
             7 --  Parameter  = V
                   Type       = Branch lengths
    
       Returning execution to calling file ...
    
          Setting Nst to 6
                   Prior      = Unconstrained:GammaDir(1.0,0.1000,1.0,1.0)
    
          Taxon  2 -> Lemur_catta
    
          Setting Rates to Invgamma
          Successfully set likelihood model parameters
    
          The MCMC sampler will use the following moves:
             With prob.  Chain will use move
                0.93 %   Dirichlet(Revmat)
                0.93 %   Slider(Revmat)
                0.93 %   Dirichlet(Pi)
                0.93 %   Slider(Pi)
                1.85 %   Multiplier(Alpha)
                1.85 %   Slider(Pinvar)
          Taxon  3 -> Homo_sapiens
                9.26 %   ExtSPR(Tau,V)
                9.26 %   ExtTBR(Tau,V)
                9.26 %   NNI(Tau,V)
                9.26 %   ParsSPR(Tau,V)
               37.04 %   Multiplier(V)
               12.96 %   Nodeslider(V)
                5.56 %   TLMultiplier(V)
    
          Taxon  4 -> Pan
          Taxon  5 -> Gorilla
          Taxon  6 -> Pongo
          Division 1 has 413 unique site patterns
          Initializing conditional likelihoods
    
          Running benchmarks to automatically select fastest BEAGLE resource...       Taxon  7 -> Hylobates
          Taxon  8 -> Macaca_fuscata
          Taxon  9 -> M_mulatta
          Taxon 10 -> M_fascicularis
          Taxon 11 -> M_sylvanus
          Taxon 12 -> Saimiri_sciureus
          Setting number of chains to 4
          Setting number of runs to 2
          Setting number of generations to 20000
          Setting sample frequency to 100
          Setting print frequency to 100
          Setting diagnosing frequency to 1000
          Setting chain output file names to "primates.nex.run<i>.<p/t>"
          Successfully read matrix
          Running Markov chain
          MCMC stamp = 5365503958
          Seed = 1806763618
          Swapseed = 1677097779
          Setting default partition (does not divide up characters)
          Setting model defaults
          Model settings:
    
             Data not partitioned --
                Datatype  = DNA
                Nucmodel  = 4by4
                Nst       = 6
                            Substitution rates, expressed as proportions
          Seed (for generating default start values) = 1677097779
                            of the rate sum, have a Dirichlet prior
                            (1.00,1.00,1.00,1.00,1.00,1.00)
                Covarion  = No
                # States  = 4
                            State frequencies have a Dirichlet prior
                            (1.00,1.00,1.00,1.00)
                Rates     = Invgamma
                            The distribution is approximated using 4 categories.
                            Shape parameter is exponentially
                            distributed with parameter (1.00).
                            Proportion of invariable sites is uniformly dist-
                            ributed on the interval (0.00,1.00).
    
          Active parameters: 
    
             Parameters
             ---------------------
             Revmat              1
             Statefreq           2
             Shape               3
             Pinvar              4
             Ratemultiplier      5
             Topology            6
             Brlens              7
             ---------------------
    
             1 --  Parameter  = Revmat
                   Type       = Rates of reversible rate matrix
                   Prior      = Dirichlet(1.00,1.00,1.00,1.00,1.00,1.00)
    
             2 --  Parameter  = Pi
                   Type       = Stationary state frequencies
                   Prior      = Dirichlet
    
             3 --  Parameter  = Alpha
                   Type       = Shape of scaled gamma distribution of site rates
                   Prior      = Exponential(1.00)
    
             4 --  Parameter  = Pinvar
                   Type       = Proportion of invariable sites
                   Prior      = Uniform(0.00,1.00)
    
             5 --  Parameter  = Ratemultiplier
                   Type       = Partition-specific rate multiplier
                   Prior      = Fixed(1.0)
    
             6 --  Parameter  = Tau
                   Type       = Topology
                   Prior      = All topologies equally probable a priori
                   Subparam.  = V
    
             7 --  Parameter  = V
                   Type       = Branch lengths
                   Prior      = Unconstrained:GammaDir(1.0,0.1000,1.0,1.0)
    
    
    
          The MCMC sampler will use the following moves:
             With prob.  Chain will use move
                0.93 %   Dirichlet(Revmat)
                0.93 %   Slider(Revmat)
                0.93 %   Dirichlet(Pi)
                0.93 %   Slider(Pi)
                1.85 %   Multiplier(Alpha)
                1.85 %   Slider(Pinvar)
                9.26 %   ExtSPR(Tau,V)
                9.26 %   ExtTBR(Tau,V)
                9.26 %   NNI(Tau,V)
                9.26 %   ParsSPR(Tau,V)
               37.04 %   Multiplier(V)
               12.96 %   Nodeslider(V)
                5.56 %   TLMultiplier(V)
    
          Division 1 has 413 unique site patterns
          Initializing conditional likelihoods
    
          Running benchmarks to automatically select fastest BEAGLE resource...       Setting output file names to "primates.nex.run<i>.<p|t>"
       Exiting data block
       Reached end of file
    
       Returning execution to calling file ...
    
          Setting Nst to 6
          Setting Rates to Invgamma
          Successfully set likelihood model parameters
          Setting number of chains to 4
          Setting number of runs to 2
          Setting number of generations to 20000
          Setting sample frequency to 100
          Setting print frequency to 100
          Setting diagnosing frequency to 1000
          Setting chain output file names to "primates.nex.run<i>.<p/t>"
          Running Markov chain
          MCMC stamp = 5365503958
          Seed = 1806763618
          Swapseed = 1677097779
          Model settings:
    
             Data not partitioned --
                Datatype  = DNA
                Nucmodel  = 4by4
                Nst       = 6
                            Substitution rates, expressed as proportions
                            of the rate sum, have a Dirichlet prior
                            (1.00,1.00,1.00,1.00,1.00,1.00)
                Covarion  = No
                # States  = 4
                            State frequencies have a Dirichlet prior
                            (1.00,1.00,1.00,1.00)
                Rates     = Invgamma
                            The distribution is approximated using 4 categories.
                            Shape parameter is exponentially
                            distributed with parameter (1.00).
                            Proportion of invariable sites is uniformly dist-
                            ributed on the interval (0.00,1.00).
    
          Active parameters: 
    
             Parameters
             ---------------------
             Revmat              1
             Statefreq           2
             Shape               3
             Pinvar              4
             Ratemultiplier      5
             Topology            6
             Brlens              7
             ---------------------
    
             1 --  Parameter  = Revmat
                   Type       = Rates of reversible rate matrix
                   Prior      = Dirichlet(1.00,1.00,1.00,1.00,1.00,1.00)
    
             2 --  Parameter  = Pi
                   Type       = Stationary state frequencies
                   Prior      = Dirichlet
    
             3 --  Parameter  = Alpha
                   Type       = Shape of scaled gamma distribution of site rates
                   Prior      = Exponential(1.00)
    
             4 --  Parameter  = Pinvar
                   Type       = Proportion of invariable sites
                   Prior      = Uniform(0.00,1.00)
    
             5 --  Parameter  = Ratemultiplier
                   Type       = Partition-specific rate multiplier
                   Prior      = Fixed(1.0)
    
             6 --  Parameter  = Tau
                   Type       = Topology
                   Prior      = All topologies equally probable a priori
                   Subparam.  = V
    
             7 --  Parameter  = V
                   Type       = Branch lengths
                   Prior      = Unconstrained:GammaDir(1.0,0.1000,1.0,1.0)
    
    
    
          The MCMC sampler will use the following moves:
             With prob.  Chain will use move
                0.93 %   Dirichlet(Revmat)
                0.93 %   Slider(Revmat)
                0.93 %   Dirichlet(Pi)
                0.93 %   Slider(Pi)
                1.85 %   Multiplier(Alpha)
                1.85 %   Slider(Pinvar)
                9.26 %   ExtSPR(Tau,V)
                9.26 %   ExtTBR(Tau,V)
                9.26 %   NNI(Tau,V)
                9.26 %   ParsSPR(Tau,V)
               37.04 %   Multiplier(V)
               12.96 %   Nodeslider(V)
                5.56 %   TLMultiplier(V)
    
          Division 1 has 413 unique site patterns
          Initializing conditional likelihoods
    
          Running benchmarks to automatically select fastest BEAGLE resource... 
          Using BEAGLE v3.1.2 resource 0 for division 1:
             Rsrc Name : CPU
             Impl Name : CPU-4State-SSE-Double
             Flags: PROCESSOR_CPU PRECISION_DOUBLE COMPUTATION_SYNCH EIGEN_REAL
                    SCALING_MANUAL SCALERS_RAW VECTOR_SSE THREADING_CPP         MODEL STATES: 4
          Initializing invariable-site conditional likelihoods
    
          Initial log likelihoods and log prior probs for run 1:
             Chain 1 -- -8482.991503 -- 42.620562
             Chain 2 -- -8489.894585 -- 42.620562
             Chain 3 -- -8311.784289 -- 42.620562
             Chain 4 -- -8678.516316 -- 42.620562
    
          Initial log likelihoods and log prior probs for run 2:
             Chain 1 -- -8554.038240 -- 42.620562
             Chain 2 -- -8641.614076 -- 42.620562
             Chain 3 -- -8289.641332 -- 42.620562
             Chain 4 -- -8838.702446 -- 42.620562
    
          Overwriting file "primates.nex.mcmc"
          Overwriting file "primates.nex.run1.p"
          Overwriting file "primates.nex.run1.t"
          Overwriting file "primates.nex.run2.p"
          Overwriting file "primates.nex.run2.t"
    
          Using a relative burnin of 25.0 % for diagnostics
    
          Chain results (20000 generations requested):
    
              0 -- [-8482.992] (-8489.895) (-8311.784) (-8678.516) * [-8554.038] (-8641.614) (-8289.641) (-8838.702) 
            100 -- (-6610.678) (-6611.840) [-6463.319] (-7111.460) * (-6754.551) [-6579.679] (-7131.344) (-7136.274) -- 0:00:00
            200 -- (-6422.568) [-6237.957] (-6275.859) (-6408.766) * (-6486.713) (-6387.117) (-6435.498) [-6353.565] -- 0:00:00
    
          Using BEAGLE v3.1.2 resource 0 for division 1:
             Rsrc Name : CPU
             Impl Name : CPU-4State-SSE-Double
             Flags: PROCESSOR_CPU PRECISION_DOUBLE COMPUTATION_SYNCH EIGEN_REAL
                    SCALING_MANUAL SCALERS_RAW VECTOR_SSE THREADING_CPP         MODEL STATES: 4
          Initializing invariable-site conditional likelihoods
    
          Initial log likelihoods and log prior probs for run 1:
             Chain 1 -- -8482.991503 -- 42.620562
             Chain 2 -- -8489.894585 -- 42.620562
             Chain 3 -- -8311.784289 -- 42.620562
             Chain 4 -- -8678.516316 -- 42.620562
    
          Initial log likelihoods and log prior probs for run 2:
             Chain 1 -- -8554.038240 -- 42.620562
             Chain 2 -- -8641.614076 -- 42.620562
             Chain 3 -- -8289.641332 -- 42.620562
             Chain 4 -- -8838.702446 -- 42.620562
    
          Overwriting file "primates.nex.mcmc"
          Overwriting file "primates.nex.run1.p"
          Overwriting file "primates.nex.run1.t"
          Overwriting file "primates.nex.run2.p"
          Overwriting file "primates.nex.run2.t"
    
          Using a relative burnin of 25.0 % for diagnostics
    
          Chain results (20000 generations requested):
    
              0 -- [-8482.992] (-8489.895) (-8311.784) (-8678.516) * [-8554.038] (-8641.614) (-8289.641) (-8838.702) 
            300 -- (-6313.467) [-6154.993] (-6218.104) (-6218.299) * (-6277.058) (-6297.698) (-6322.284) [-6201.068] -- 0:00:00
            100 -- (-6610.678) (-6611.840) [-6463.319] (-7111.460) * (-6754.551) [-6579.679] (-7131.344) (-7136.274) -- 0:00:00
            400 -- (-6251.156) [-6136.708] (-6198.755) (-6150.018) * (-6189.052) (-6252.720) (-6229.334) [-6115.244] -- 0:00:00
    
          Using BEAGLE v3.1.2 resource 0 for division 1:
             Rsrc Name : CPU
             Impl Name : CPU-4State-SSE-Double
             Flags: PROCESSOR_CPU PRECISION_DOUBLE COMPUTATION_SYNCH EIGEN_REAL
                    SCALING_MANUAL SCALERS_RAW VECTOR_SSE THREADING_CPP         MODEL STATES: 4
          Initializing invariable-site conditional likelihoods
    
          Initial log likelihoods and log prior probs for run 1:
             Chain 1 -- -8482.991503 -- 42.620562
             Chain 2 -- -8489.894585 -- 42.620562
             Chain 3 -- -8311.784289 -- 42.620562
             Chain 4 -- -8678.516316 -- 42.620562
    
          Initial log likelihoods and log prior probs for run 2:
             Chain 1 -- -8554.038240 -- 42.620562
             Chain 2 -- -8641.614076 -- 42.620562
             Chain 3 -- -8289.641332 -- 42.620562
             Chain 4 -- -8838.702446 -- 42.620562
    
          Overwriting file "primates.nex.mcmc"
          Overwriting file "primates.nex.run1.p"
          Overwriting file "primates.nex.run1.t"
          Overwriting file "primates.nex.run2.p"
          Overwriting file "primates.nex.run2.t"
    
          Using a relative burnin of 25.0 % for diagnostics
    
          Chain results (20000 generations requested):
    
              0 -- [-8482.992] (-8489.895) (-8311.784) (-8678.516) * [-8554.038] (-8641.614) (-8289.641) (-8838.702) 
    
          Using BEAGLE v3.1.2 resource 0 for division 1:
             Rsrc Name : CPU
             Impl Name : CPU-4State-SSE-Double
             Flags: PROCESSOR_CPU PRECISION_DOUBLE COMPUTATION_SYNCH EIGEN_REAL
                    SCALING_MANUAL SCALERS_RAW VECTOR_SSE THREADING_CPP         MODEL STATES: 4
          Initializing invariable-site conditional likelihoods
    
          Initial log likelihoods and log prior probs for run 1:
             Chain 1 -- -8482.991503 -- 42.620562
             Chain 2 -- -8489.894585 -- 42.620562
             Chain 3 -- -8311.784289 -- 42.620562
             Chain 4 -- -8678.516316 -- 42.620562
    
          Initial log likelihoods and log prior probs for run 2:
             Chain 1 -- -8554.038240 -- 42.620562
             Chain 2 -- -8641.614076 -- 42.620562
             Chain 3 -- -8289.641332 -- 42.620562
             Chain 4 -- -8838.702446 -- 42.620562
    
          Overwriting file "primates.nex.mcmc"
          Overwriting file "primates.nex.run1.p"
          Overwriting file "primates.nex.run1.t"
          Overwriting file "primates.nex.run2.p"
          Overwriting file "primates.nex.run2.t"
    
          Using a relative burnin of 25.0 % for diagnostics
    
          Chain results (20000 generations requested):
    
              0 -- [-8482.992] (-8489.895) (-8311.784) (-8678.516) * [-8554.038] (-8641.614) (-8289.641) (-8838.702) 
            200 -- (-6422.568) [-6237.957] (-6275.859) (-6408.766) * (-6486.713) (-6387.117) (-6435.498) [-6353.565] -- 0:00:00
            500 -- (-6246.345) [-6076.215] (-6176.394) (-6089.703) * (-6156.624) (-6215.010) (-6150.530) [-6046.662] -- 0:00:00
            100 -- (-6610.678) (-6611.840) [-6463.319] (-7111.460) * (-6754.551) [-6579.679] (-7131.344) (-7136.274) -- 0:00:00
            300 -- (-6313.467) [-6154.993] (-6218.104) (-6218.299) * (-6277.058) (-6297.698) (-6322.284) [-6201.068] -- 0:00:00
            600 -- (-6233.744) [-6064.105] (-6170.156) (-6082.064) * (-6149.856) (-6144.919) (-6128.261) [-6015.928] -- 0:00:00
            100 -- (-6610.678) (-6611.840) [-6463.319] (-7111.460) * (-6754.551) [-6579.679] (-7131.344) (-7136.274) -- 0:00:00
            200 -- (-6422.568) [-6237.957] (-6275.859) (-6408.766) * (-6486.713) (-6387.117) (-6435.498) [-6353.565] -- 0:00:00
            700 -- (-6151.842) [-6055.396] (-6171.074) (-6047.616) * (-6082.936) (-6104.383) (-6128.124) [-5995.560] -- 0:00:00
            400 -- (-6251.156) [-6136.708] (-6198.755) (-6150.018) * (-6189.052) (-6252.720) (-6229.334) [-6115.244] -- 0:00:00
            200 -- (-6422.568) [-6237.957] (-6275.859) (-6408.766) * (-6486.713) (-6387.117) (-6435.498) [-6353.565] -- 0:00:00
            300 -- (-6313.467) [-6154.993] (-6218.104) (-6218.299) * (-6277.058) (-6297.698) (-6322.284) [-6201.068] -- 0:01:05
            800 -- (-6136.894) (-6057.882) (-6126.749) [-6013.662] * (-6072.613) (-6101.415) (-6099.529) [-5992.091] -- 0:00:24
            500 -- (-6246.345) [-6076.215] (-6176.394) (-6089.703) * (-6156.624) (-6215.010) (-6150.530) [-6046.662] -- 0:00:39
            400 -- (-6251.156) [-6136.708] (-6198.755) (-6150.018) * (-6189.052) (-6252.720) (-6229.334) [-6115.244] -- 0:00:49
            300 -- (-6313.467) [-6154.993] (-6218.104) (-6218.299) * (-6277.058) (-6297.698) (-6322.284) [-6201.068] -- 0:01:05
            900 -- (-6107.129) (-6022.343) (-6129.193) [-6019.332] * (-6066.510) (-6014.261) (-6044.825) [-5985.574] -- 0:00:21
            500 -- (-6246.345) [-6076.215] (-6176.394) (-6089.703) * (-6156.624) (-6215.010) (-6150.530) [-6046.662] -- 0:00:39
            600 -- (-6233.744) [-6064.105] (-6170.156) (-6082.064) * (-6149.856) (-6144.919) (-6128.261) [-6015.928] -- 0:00:32
            400 -- (-6251.156) [-6136.708] (-6198.755) (-6150.018) * (-6189.052) (-6252.720) (-6229.334) [-6115.244] -- 0:00:49
            600 -- (-6233.744) [-6064.105] (-6170.156) (-6082.064) * (-6149.856) (-6144.919) (-6128.261) [-6015.928] -- 0:00:32
           1000 -- (-6064.455) [-5970.839] (-6125.103) (-5989.892) * (-6044.595) (-6007.041) (-5996.590) [-5977.174] -- 0:00:19
            700 -- (-6151.842) [-6055.396] (-6171.074) (-6047.616) * (-6082.936) (-6104.383) (-6128.124) [-5995.560] -- 0:00:27
    
          Average standard deviation of split frequencies: 0.015713
    
            500 -- (-6246.345) [-6076.215] (-6176.394) (-6089.703) * (-6156.624) (-6215.010) (-6150.530) [-6046.662] -- 0:00:39
            700 -- (-6151.842) [-6055.396] (-6171.074) (-6047.616) * (-6082.936) (-6104.383) (-6128.124) [-5995.560] -- 0:00:27
            600 -- (-6233.744) [-6064.105] (-6170.156) (-6082.064) * (-6149.856) (-6144.919) (-6128.261) [-6015.928] -- 0:00:32
            800 -- (-6136.894) (-6057.882) (-6126.749) [-6013.662] * (-6072.613) (-6101.415) (-6099.529) [-5992.091] -- 0:00:24
           1100 -- (-6064.897) [-5975.070] (-6066.949) (-5986.710) * (-5998.646) [-5937.749] (-5980.814) (-5969.654) -- 0:00:17
            800 -- (-6136.894) (-6057.882) (-6126.749) [-6013.662] * (-6072.613) (-6101.415) (-6099.529) [-5992.091] -- 0:00:24
            700 -- (-6151.842) [-6055.396] (-6171.074) (-6047.616) * (-6082.936) (-6104.383) (-6128.124) [-5995.560] -- 0:00:27
           1200 -- (-6052.355) [-5944.133] (-6056.831) (-5977.738) * (-5988.045) [-5922.557] (-5978.097) (-5960.588) -- 0:00:15
            900 -- (-6107.129) (-6022.343) (-6129.193) [-6019.332] * (-6066.510) (-6014.261) (-6044.825) [-5985.574] -- 0:00:21
            900 -- (-6107.129) (-6022.343) (-6129.193) [-6019.332] * (-6066.510) (-6014.261) (-6044.825) [-5985.574] -- 0:00:21
            800 -- (-6136.894) (-6057.882) (-6126.749) [-6013.662] * (-6072.613) (-6101.415) (-6099.529) [-5992.091] -- 0:00:24
           1300 -- (-6037.629) [-5919.051] (-6054.148) (-5979.522) * (-5978.064) (-5924.794) (-5957.223) [-5918.468] -- 0:00:14
           1000 -- (-6064.455) [-5970.839] (-6125.103) (-5989.892) * (-6044.595) (-6007.041) (-5996.590) [-5977.174] -- 0:00:19
    
          Average standard deviation of split frequencies: 0.015713
    
           1000 -- (-6064.455) [-5970.839] (-6125.103) (-5989.892) * (-6044.595) (-6007.041) (-5996.590) [-5977.174] -- 0:00:38
    
          Average standard deviation of split frequencies: 0.015713
    
           1400 -- (-5942.971) [-5921.733] (-6058.646) (-5959.548) * (-5984.744) (-5930.720) (-5960.243) [-5883.263] -- 0:00:26
            900 -- (-6107.129) (-6022.343) (-6129.193) [-6019.332] * (-6066.510) (-6014.261) (-6044.825) [-5985.574] -- 0:00:42
           1100 -- (-6064.897) [-5975.070] (-6066.949) (-5986.710) * (-5998.646) [-5937.749] (-5980.814) (-5969.654) -- 0:00:34
           1100 -- (-6064.897) [-5975.070] (-6066.949) (-5986.710) * (-5998.646) [-5937.749] (-5980.814) (-5969.654) -- 0:00:34
           1500 -- (-5936.619) [-5905.842] (-6055.511) (-5958.324) * (-5974.069) (-5922.723) (-5968.058) [-5881.903] -- 0:00:24
           1200 -- (-6052.355) [-5944.133] (-6056.831) (-5977.738) * (-5988.045) [-5922.557] (-5978.097) (-5960.588) -- 0:00:31
           1000 -- (-6064.455) [-5970.839] (-6125.103) (-5989.892) * (-6044.595) (-6007.041) (-5996.590) [-5977.174] -- 0:00:38
    
          Average standard deviation of split frequencies: 0.015713
    
           1600 -- (-5939.209) [-5906.038] (-6028.327) (-5951.753) * (-5930.670) (-5925.341) (-5954.107) [-5875.126] -- 0:00:23
           1300 -- (-6037.629) [-5919.051] (-6054.148) (-5979.522) * (-5978.064) (-5924.794) (-5957.223) [-5918.468] -- 0:00:28
           1200 -- (-6052.355) [-5944.133] (-6056.831) (-5977.738) * (-5988.045) [-5922.557] (-5978.097) (-5960.588) -- 0:00:31
           1100 -- (-6064.897) [-5975.070] (-6066.949) (-5986.710) * (-5998.646) [-5937.749] (-5980.814) (-5969.654) -- 0:00:34
           1700 -- (-5925.471) [-5866.059] (-6027.870) (-5934.270) * (-5921.679) (-5887.971) (-5959.299) [-5871.791] -- 0:00:21
           1400 -- (-5942.971) [-5921.733] (-6058.646) (-5959.548) * (-5984.744) (-5930.720) (-5960.243) [-5883.263] -- 0:00:26
           1300 -- (-6037.629) [-5919.051] (-6054.148) (-5979.522) * (-5978.064) (-5924.794) (-5957.223) [-5918.468] -- 0:00:28
           1800 -- (-5924.112) [-5859.918] (-6017.117) (-5931.956) * (-5911.316) (-5881.171) (-5903.580) [-5870.162] -- 0:00:20
           1200 -- (-6052.355) [-5944.133] (-6056.831) (-5977.738) * (-5988.045) [-5922.557] (-5978.097) (-5960.588) -- 0:00:31
           1500 -- (-5936.619) [-5905.842] (-6055.511) (-5958.324) * (-5974.069) (-5922.723) (-5968.058) [-5881.903] -- 0:00:24
           1400 -- (-5942.971) [-5921.733] (-6058.646) (-5959.548) * (-5984.744) (-5930.720) (-5960.243) [-5883.263] -- 0:00:26
           1900 -- (-5888.391) [-5856.998] (-5970.093) (-5929.575) * (-5886.402) [-5859.824] (-5906.440) (-5858.227) -- 0:00:19
           1300 -- (-6037.629) [-5919.051] (-6054.148) (-5979.522) * (-5978.064) (-5924.794) (-5957.223) [-5918.468] -- 0:00:28
           1500 -- (-5936.619) [-5905.842] (-6055.511) (-5958.324) * (-5974.069) (-5922.723) (-5968.058) [-5881.903] -- 0:00:24
           1600 -- (-5939.209) [-5906.038] (-6028.327) (-5951.753) * (-5930.670) (-5925.341) (-5954.107) [-5875.126] -- 0:00:23
           2000 -- (-5881.901) [-5858.339] (-5928.297) (-5930.163) * (-5881.756) [-5861.379] (-5871.767) (-5861.313) -- 0:00:18
    
          Average standard deviation of split frequencies: 0.000000
    
           1600 -- (-5939.209) [-5906.038] (-6028.327) (-5951.753) * (-5930.670) (-5925.341) (-5954.107) [-5875.126] -- 0:00:23
           1400 -- (-5942.971) [-5921.733] (-6058.646) (-5959.548) * (-5984.744) (-5930.720) (-5960.243) [-5883.263] -- 0:00:39
           1700 -- (-5925.471) [-5866.059] (-6027.870) (-5934.270) * (-5921.679) (-5887.971) (-5959.299) [-5871.791] -- 0:00:32
           2100 -- (-5867.846) [-5822.081] (-5910.800) (-5940.378) * (-5884.841) (-5839.097) [-5858.145] (-5860.418) -- 0:00:25
           1700 -- (-5925.471) [-5866.059] (-6027.870) (-5934.270) * (-5921.679) (-5887.971) (-5959.299) [-5871.791] -- 0:00:32
           2200 -- (-5861.538) [-5820.055] (-5904.513) (-5929.881) * (-5875.736) [-5837.207] (-5852.940) (-5863.666) -- 0:00:24
           1500 -- (-5936.619) [-5905.842] (-6055.511) (-5958.324) * (-5974.069) (-5922.723) (-5968.058) [-5881.903] -- 0:00:37
           1800 -- (-5924.112) [-5859.918] (-6017.117) (-5931.956) * (-5911.316) (-5881.171) (-5903.580) [-5870.162] -- 0:00:30
           1800 -- (-5924.112) [-5859.918] (-6017.117) (-5931.956) * (-5911.316) (-5881.171) (-5903.580) [-5870.162] -- 0:00:30
           2300 -- (-5861.363) [-5785.781] (-5906.019) (-5872.931) * (-5872.361) [-5835.288] (-5853.760) (-5849.226) -- 0:00:23
           1600 -- (-5939.209) [-5906.038] (-6028.327) (-5951.753) * (-5930.670) (-5925.341) (-5954.107) [-5875.126] -- 0:00:34
           1900 -- (-5888.391) [-5856.998] (-5970.093) (-5929.575) * (-5886.402) [-5859.824] (-5906.440) (-5858.227) -- 0:00:28
           1900 -- (-5888.391) [-5856.998] (-5970.093) (-5929.575) * (-5886.402) [-5859.824] (-5906.440) (-5858.227) -- 0:00:28
           2400 -- (-5863.480) [-5780.194] (-5889.966) (-5862.687) * (-5873.994) [-5836.942] (-5853.956) (-5850.371) -- 0:00:22
           1700 -- (-5925.471) [-5866.059] (-6027.870) (-5934.270) * (-5921.679) (-5887.971) (-5959.299) [-5871.791] -- 0:00:32
           2000 -- (-5881.901) [-5858.339] (-5928.297) (-5930.163) * (-5881.756) [-5861.379] (-5871.767) (-5861.313) -- 0:00:27
    
          Average standard deviation of split frequencies: 0.000000
    
           2000 -- (-5881.901) [-5858.339] (-5928.297) (-5930.163) * (-5881.756) [-5861.379] (-5871.767) (-5861.313) -- 0:00:27
    
          Average standard deviation of split frequencies: 0.000000
    
           2500 -- (-5850.721) [-5765.225] (-5885.818) (-5851.547) * (-5848.686) (-5837.194) [-5840.981] (-5856.070) -- 0:00:20
           1800 -- (-5924.112) [-5859.918] (-6017.117) (-5931.956) * (-5911.316) (-5881.171) (-5903.580) [-5870.162] -- 0:00:30
           2100 -- (-5867.846) [-5822.081] (-5910.800) (-5940.378) * (-5884.841) (-5839.097) [-5858.145] (-5860.418) -- 0:00:25
           2100 -- (-5867.846) [-5822.081] (-5910.800) (-5940.378) * (-5884.841) (-5839.097) [-5858.145] (-5860.418) -- 0:00:25
           2600 -- (-5832.787) [-5761.895] (-5891.083) (-5850.181) * (-5848.454) [-5820.715] (-5841.344) (-5853.031) -- 0:00:20
           1900 -- (-5888.391) [-5856.998] (-5970.093) (-5929.575) * (-5886.402) [-5859.824] (-5906.440) (-5858.227) -- 0:00:28
           2200 -- (-5861.538) [-5820.055] (-5904.513) (-5929.881) * (-5875.736) [-5837.207] (-5852.940) (-5863.666) -- 0:00:24
           2700 -- (-5832.970) [-5750.259] (-5881.416) (-5849.214) * (-5844.614) [-5824.943] (-5841.621) (-5838.337) -- 0:00:25
           2200 -- (-5861.538) [-5820.055] (-5904.513) (-5929.881) * (-5875.736) [-5837.207] (-5852.940) (-5863.666) -- 0:00:32
           2000 -- (-5881.901) [-5858.339] (-5928.297) (-5930.163) * (-5881.756) [-5861.379] (-5871.767) (-5861.313) -- 0:00:36
    
          Average standard deviation of split frequencies: 0.000000
    
           2300 -- (-5861.363) [-5785.781] (-5906.019) (-5872.931) * (-5872.361) [-5835.288] (-5853.760) (-5849.226) -- 0:00:30
           2800 -- (-5837.206) [-5754.125] (-5883.836) (-5854.017) * (-5850.463) [-5803.295] (-5815.495) (-5828.485) -- 0:00:24
           2300 -- (-5861.363) [-5785.781] (-5906.019) (-5872.931) * (-5872.361) [-5835.288] (-5853.760) (-5849.226) -- 0:00:30
           2100 -- (-5867.846) [-5822.081] (-5910.800) (-5940.378) * (-5884.841) (-5839.097) [-5858.145] (-5860.418) -- 0:00:34
           2400 -- (-5863.480) [-5780.194] (-5889.966) (-5862.687) * (-5873.994) [-5836.942] (-5853.956) (-5850.371) -- 0:00:29
           2900 -- (-5830.131) [-5750.851] (-5878.003) (-5853.018) * (-5836.659) [-5782.801] (-5791.126) (-5811.695) -- 0:00:23
           2500 -- (-5850.721) [-5765.225] (-5885.818) (-5851.547) * (-5848.686) (-5837.194) [-5840.981] (-5856.070) -- 0:00:28
           2400 -- (-5863.480) [-5780.194] (-5889.966) (-5862.687) * (-5873.994) [-5836.942] (-5853.956) (-5850.371) -- 0:00:29
           2200 -- (-5861.538) [-5820.055] (-5904.513) (-5929.881) * (-5875.736) [-5837.207] (-5852.940) (-5863.666) -- 0:00:32
           2600 -- (-5832.787) [-5761.895] (-5891.083) (-5850.181) * (-5848.454) [-5820.715] (-5841.344) (-5853.031) -- 0:00:26
           2500 -- (-5850.721) [-5765.225] (-5885.818) (-5851.547) * (-5848.686) (-5837.194) [-5840.981] (-5856.070) -- 0:00:28
           3000 -- (-5811.157) [-5751.417] (-5877.768) (-5847.569) * (-5824.971) [-5779.733] (-5788.971) (-5809.142) -- 0:00:22
    
          Average standard deviation of split frequencies: 0.000000
    
           2300 -- (-5861.363) [-5785.781] (-5906.019) (-5872.931) * (-5872.361) [-5835.288] (-5853.760) (-5849.226) -- 0:00:30
           2700 -- (-5832.970) [-5750.259] (-5881.416) (-5849.214) * (-5844.614) [-5824.943] (-5841.621) (-5838.337) -- 0:00:25
           2600 -- (-5832.787) [-5761.895] (-5891.083) (-5850.181) * (-5848.454) [-5820.715] (-5841.344) (-5853.031) -- 0:00:26
           2400 -- (-5863.480) [-5780.194] (-5889.966) (-5862.687) * (-5873.994) [-5836.942] (-5853.956) (-5850.371) -- 0:00:29
           3100 -- (-5809.221) [-5744.164] (-5860.892) (-5838.484) * (-5808.206) [-5781.919] (-5789.815) (-5812.047) -- 0:00:21
           2800 -- (-5837.206) [-5754.125] (-5883.836) (-5854.017) * (-5850.463) [-5803.295] (-5815.495) (-5828.485) -- 0:00:24
           2500 -- (-5850.721) [-5765.225] (-5885.818) (-5851.547) * (-5848.686) (-5837.194) [-5840.981] (-5856.070) -- 0:00:35
           2700 -- (-5832.970) [-5750.259] (-5881.416) (-5849.214) * (-5844.614) [-5824.943] (-5841.621) (-5838.337) -- 0:00:32
           3200 -- (-5810.479) [-5743.854] (-5844.747) (-5834.616) * (-5804.038) (-5775.769) [-5789.204] (-5798.454) -- 0:00:26
           2900 -- (-5830.131) [-5750.851] (-5878.003) (-5853.018) * (-5836.659) [-5782.801] (-5791.126) (-5811.695) -- 0:00:29
           2800 -- (-5837.206) [-5754.125] (-5883.836) (-5854.017) * (-5850.463) [-5803.295] (-5815.495) (-5828.485) -- 0:00:30
           3300 -- (-5811.638) [-5742.487] (-5841.691) (-5840.756) * (-5807.478) (-5769.163) [-5785.355] (-5801.157) -- 0:00:25
           2600 -- (-5832.787) [-5761.895] (-5891.083) (-5850.181) * (-5848.454) [-5820.715] (-5841.344) (-5853.031) -- 0:00:33
           2900 -- (-5830.131) [-5750.851] (-5878.003) (-5853.018) * (-5836.659) [-5782.801] (-5791.126) (-5811.695) -- 0:00:29
           3000 -- (-5811.157) [-5751.417] (-5877.768) (-5847.569) * (-5824.971) [-5779.733] (-5788.971) (-5809.142) -- 0:00:28
    
          Average standard deviation of split frequencies: 0.000000
    
           3400 -- (-5793.685) [-5743.790] (-5837.023) (-5839.889) * (-5799.786) [-5745.239] (-5789.666) (-5786.829) -- 0:00:24
           2700 -- (-5832.970) [-5750.259] (-5881.416) (-5849.214) * (-5844.614) [-5824.943] (-5841.621) (-5838.337) -- 0:00:32
           3000 -- (-5811.157) [-5751.417] (-5877.768) (-5847.569) * (-5824.971) [-5779.733] (-5788.971) (-5809.142) -- 0:00:28
    
          Average standard deviation of split frequencies: 0.000000
    
           3500 -- (-5799.620) [-5738.242] (-5836.115) (-5823.168) * (-5801.389) [-5745.418] (-5787.121) (-5781.701) -- 0:00:23
           3100 -- (-5809.221) [-5744.164] (-5860.892) (-5838.484) * (-5808.206) [-5781.919] (-5789.815) (-5812.047) -- 0:00:27
           2800 -- (-5837.206) [-5754.125] (-5883.836) (-5854.017) * (-5850.463) [-5803.295] (-5815.495) (-5828.485) -- 0:00:30
           3100 -- (-5809.221) [-5744.164] (-5860.892) (-5838.484) * (-5808.206) [-5781.919] (-5789.815) (-5812.047) -- 0:00:27
           3600 -- (-5797.706) [-5744.163] (-5813.845) (-5820.907) * (-5803.545) [-5744.788] (-5782.013) (-5782.235) -- 0:00:22
           3200 -- (-5810.479) [-5743.854] (-5844.747) (-5834.616) * (-5804.038) (-5775.769) [-5789.204] (-5798.454) -- 0:00:26
           2900 -- (-5830.131) [-5750.851] (-5878.003) (-5853.018) * (-5836.659) [-5782.801] (-5791.126) (-5811.695) -- 0:00:29
           3200 -- (-5810.479) [-5743.854] (-5844.747) (-5834.616) * (-5804.038) (-5775.769) [-5789.204] (-5798.454) -- 0:00:26
           3300 -- (-5811.638) [-5742.487] (-5841.691) (-5840.756) * (-5807.478) (-5769.163) [-5785.355] (-5801.157) -- 0:00:25
           3700 -- (-5800.170) [-5741.475] (-5805.002) (-5818.728) * (-5802.931) [-5751.249] (-5785.305) (-5782.558) -- 0:00:22
           3000 -- (-5811.157) [-5751.417] (-5877.768) (-5847.569) * (-5824.971) [-5779.733] (-5788.971) (-5809.142) -- 0:00:28
    
          Average standard deviation of split frequencies: 0.000000
    
           3800 -- (-5798.279) [-5734.465] (-5790.701) (-5817.183) * (-5788.434) [-5744.722] (-5780.346) (-5784.678) -- 0:00:21
           3300 -- (-5811.638) [-5742.487] (-5841.691) (-5840.756) * (-5807.478) (-5769.163) [-5785.355] (-5801.157) -- 0:00:25
           3400 -- (-5793.685) [-5743.790] (-5837.023) (-5839.889) * (-5799.786) [-5745.239] (-5789.666) (-5786.829) -- 0:00:24
           3100 -- (-5809.221) [-5744.164] (-5860.892) (-5838.484) * (-5808.206) [-5781.919] (-5789.815) (-5812.047) -- 0:00:32
           3900 -- (-5799.973) [-5733.989] (-5769.033) (-5816.806) * (-5794.320) [-5741.048] (-5785.053) (-5778.099) -- 0:00:24
           3400 -- (-5793.685) [-5743.790] (-5837.023) (-5839.889) * (-5799.786) [-5745.239] (-5789.666) (-5786.829) -- 0:00:29       3200 -- (-5810.479) 
    [-5743.854] (-5844.747) (-5834.616) * (-5804.038) (-5775.769) [-5789.204] (-5798.454) -- 0:00:31
           3500 -- (-5799.620) [-5738.242] (-5836.115) (-5823.168) * (-5801.389) [-5745.418] (-5787.121) (-5781.701) -- 0:00:28
           4000 -- (-5806.568) [-5736.093] (-5756.277) (-5811.278) * (-5772.092) [-5740.123] (-5777.967) (-5780.094) -- 0:00:24
    
          Average standard deviation of split frequencies: 0.000000
    
           3300 -- (-5811.638) [-5742.487] (-5841.691) (-5840.756) * (-5807.478) (-5769.163) [-5785.355] (-5801.157) -- 0:00:30
           3500 -- (-5799.620) [-5738.242] (-5836.115) (-5823.168) * (-5801.389) [-5745.418] (-5787.121) (-5781.701) -- 0:00:28
           3600 -- (-5797.706) [-5744.163] (-5813.845) (-5820.907) * (-5803.545) [-5744.788] (-5782.013) (-5782.235) -- 0:00:27
           4100 -- (-5796.320) (-5729.635) [-5747.185] (-5812.914) * (-5773.345) [-5739.354] (-5772.834) (-5782.862) -- 0:00:23
           3400 -- (-5793.685) [-5743.790] (-5837.023) (-5839.889) * (-5799.786) [-5745.239] (-5789.666) (-5786.829) -- 0:00:29
           3600 -- (-5797.706) [-5744.163] (-5813.845) (-5820.907) * (-5803.545) [-5744.788] (-5782.013) (-5782.235) -- 0:00:27
           3700 -- (-5800.170) [-5741.475] (-5805.002) (-5818.728) * (-5802.931) [-5751.249] (-5785.305) (-5782.558) -- 0:00:26
           3500 -- (-5799.620) [-5738.242] (-5836.115) (-5823.168) * (-5801.389) [-5745.418] (-5787.121) (-5781.701) -- 0:00:28
           4200 -- (-5785.095) [-5737.736] (-5743.230) (-5793.283) * (-5776.896) [-5739.706] (-5773.360) (-5776.020) -- 0:00:22
           3700 -- (-5800.170) [-5741.475] (-5805.002) (-5818.728) * (-5802.931) [-5751.249] (-5785.305) (-5782.558) -- 0:00:26
           3600 -- (-5797.706) [-5744.163] (-5813.845) (-5820.907) * (-5803.545) [-5744.788] (-5782.013) (-5782.235) -- 0:00:27
           3800 -- (-5798.279) [-5734.465] (-5790.701) (-5817.183) * (-5788.434) [-5744.722] (-5780.346) (-5784.678) -- 0:00:25
           4300 -- (-5782.151) (-5731.931) [-5740.589] (-5779.153) * (-5775.374) [-5741.116] (-5768.376) (-5772.087) -- 0:00:21
           3700 -- (-5800.170) [-5741.475] (-5805.002) (-5818.728) * (-5802.931) [-5751.249] (-5785.305) (-5782.558) -- 0:00:26
           3800 -- (-5798.279) [-5734.465] (-5790.701) (-5817.183) * (-5788.434) [-5744.722] (-5780.346) (-5784.678) -- 0:00:25
           4400 -- (-5779.234) (-5733.215) [-5743.029] (-5772.127) * (-5767.962) [-5743.248] (-5764.069) (-5768.616) -- 0:00:21
           3900 -- (-5799.973) [-5733.989] (-5769.033) (-5816.806) * (-5794.320) [-5741.048] (-5785.053) (-5778.099) -- 0:00:24
           3800 -- (-5798.279) [-5734.465] (-5790.701) (-5817.183) * (-5788.434) [-5744.722] (-5780.346) (-5784.678) -- 0:00:25
           4500 -- (-5785.058) (-5733.019) [-5747.841] (-5771.062) * (-5764.475) [-5743.338] (-5761.333) (-5765.323) -- 0:00:24
           3900 -- (-5799.973) [-5733.989] (-5769.033) (-5816.806) * (-5794.320) [-5741.048] (-5785.053) (-5778.099) -- 0:00:28
           4000 -- (-5806.568) [-5736.093] (-5756.277) (-5811.278) * (-5772.092) [-5740.123] (-5777.967) (-5780.094) -- 0:00:28
    
          Average standard deviation of split frequencies: 0.000000
    
           4600 -- (-5777.833) [-5731.816] (-5739.938) (-5760.379) * (-5769.558) [-5738.396] (-5761.618) (-5763.780) -- 0:00:23
           3900 -- (-5799.973) [-5733.989] (-5769.033) (-5816.806) * (-5794.320) [-5741.048] (-5785.053) (-5778.099) -- 0:00:28
           4000 -- (-5806.568) [-5736.093] (-5756.277) (-5811.278) * (-5772.092) [-5740.123] (-5777.967) (-5780.094) -- 0:00:28
    
          Average standard deviation of split frequencies: 0.000000
    
           4700 -- (-5776.748) [-5729.221] (-5742.037) (-5764.126) * (-5780.158) [-5740.616] (-5755.969) (-5767.188) -- 0:00:22
           4100 -- (-5796.320) (-5729.635) [-5747.185] (-5812.914) * (-5773.345) [-5739.354] (-5772.834) (-5782.862) -- 0:00:27
           4000 -- (-5806.568) [-5736.093] (-5756.277) (-5811.278) * (-5772.092) [-5740.123] (-5777.967) (-5780.094) -- 0:00:28
    
          Average standard deviation of split frequencies: 0.000000
    
           4800 -- (-5766.352) [-5727.504] (-5738.362) (-5758.409) * (-5771.096) [-5736.967] (-5756.037) (-5764.399) -- 0:00:22
           4100 -- (-5796.320) (-5729.635) [-5747.185] (-5812.914) * (-5773.345) [-5739.354] (-5772.834) (-5782.862) -- 0:00:27
           4200 -- (-5785.095) [-5737.736] (-5743.230) (-5793.283) * (-5776.896) [-5739.706] (-5773.360) (-5776.020) -- 0:00:26
           4100 -- (-5796.320) (-5729.635) [-5747.185] (-5812.914) * (-5773.345) [-5739.354] (-5772.834) (-5782.862) -- 0:00:27
           4900 -- (-5765.212) [-5729.519] (-5735.090) (-5763.523) * (-5771.622) [-5736.175] (-5746.681) (-5765.647) -- 0:00:21
           4200 -- (-5785.095) [-5737.736] (-5743.230) (-5793.283) * (-5776.896) [-5739.706] (-5773.360) (-5776.020) -- 0:00:26
           4200 -- (-5785.095) [-5737.736] (-5743.230) (-5793.283) * (-5776.896) [-5739.706] (-5773.360) (-5776.020) -- 0:00:26
           4300 -- (-5782.151) (-5731.931) [-5740.589] (-5779.153) * (-5775.374) [-5741.116] (-5768.376) (-5772.087) -- 0:00:25
           5000 -- (-5769.111) [-5729.469] (-5731.255) (-5756.034) * (-5765.667) [-5738.547] (-5748.622) (-5775.086) -- 0:00:21
    
          Average standard deviation of split frequencies: 0.000000
    
           4300 -- (-5782.151) (-5731.931) [-5740.589] (-5779.153) * (-5775.374) [-5741.116] (-5768.376) (-5772.087) -- 0:00:25
           4300 -- (-5782.151) (-5731.931) [-5740.589] (-5779.153) * (-5775.374) [-5741.116] (-5768.376) (-5772.087) -- 0:00:25
           4400 -- (-5779.234) (-5733.215) [-5743.029] (-5772.127) * (-5767.962) [-5743.248] (-5764.069) (-5768.616) -- 0:00:24
           5100 -- (-5766.691) [-5724.795] (-5730.254) (-5752.502) * (-5754.168) [-5734.828] (-5748.010) (-5759.884) -- 0:00:20
           4400 -- (-5779.234) (-5733.215) [-5743.029] (-5772.127) * (-5767.962) [-5743.248] (-5764.069) (-5768.616) -- 0:00:24
           4400 -- (-5779.234) (-5733.215) [-5743.029] (-5772.127) * (-5767.962) [-5743.248] (-5764.069) (-5768.616) -- 0:00:24
           4500 -- (-5785.058) (-5733.019) [-5747.841] (-5771.062) * (-5764.475) [-5743.338] (-5761.333) (-5765.323) -- 0:00:24
           5200 -- (-5758.431) (-5722.197) [-5730.771] (-5754.512) * (-5755.271) (-5723.806) [-5742.037] (-5749.546) -- 0:00:19
           4500 -- (-5785.058) (-5733.019) [-5747.841] (-5771.062) * (-5764.475) [-5743.338] (-5761.333) (-5765.323) -- 0:00:24
           4500 -- (-5785.058) (-5733.019) [-5747.841] (-5771.062) * (-5764.475) [-5743.338] (-5761.333) (-5765.323) -- 0:00:24
           4600 -- (-5777.833) [-5731.816] (-5739.938) (-5760.379) * (-5769.558) [-5738.396] (-5761.618) (-5763.780) -- 0:00:26
           4600 -- (-5777.833) [-5731.816] (-5739.938) (-5760.379) * (-5769.558) [-5738.396] (-5761.618) (-5763.780) -- 0:00:26
           5300 --        4600 -- (-5777.833) (-5752.060) (-5730.073) [-5730.894] (-5754.820) * (-5752.571) (-5726.751) [-5731.816] (-5739.938) (-5760.379) (-5740.839) * (-5769.558) [-5738.396] (-5761.618) (-5763.780) -- 0:00:26
    [-5742.941] -- 0:00:22
           4700 -- (-5776.748) [-5729.221] (-5742.037) (-5764.126) * (-5780.158) [-5740.616] (-5755.969) (-5767.188) -- 0:00:26
           4700 -- (-5776.748) [-5729.221] (-5742.037) (-5764.126) * (-5780.158) [-5740.616] (-5755.969) (-5767.188) -- 0:00:26
           4700 -- (-5776.748) [-5729.221] (-5742.037) (-5764.126) * (-5780.158) [-5740.616] (-5755.969) (-5767.188) -- 0:00:26
           4800 -- (-5766.352) [-5727.504] (-5738.362) (-5758.409) * (-5771.096) [-5736.967] (-5756.037) (-5764.399) -- 0:00:25
           5400 -- (-5746.171) [-5727.443] (-5732.867) (-5757.073) * (-5746.814) [-5725.255] (-5751.844) (-5741.018) -- 0:00:21
           4800 -- (-5766.352) [-5727.504] (-5738.362) (-5758.409) * (-5771.096) [-5736.967] (-5756.037) (-5764.399) -- 0:00:25
           4900 -- (-5765.212) [-5729.519] (-5735.090) (-5763.523) * (-5771.622) [-5736.175] (-5746.681) (-5765.647) -- 0:00:24
           4800 -- (-5766.352) [-5727.504] (-5738.362) (-5758.409) * (-5771.096) [-5736.967] (-5756.037) (-5764.399) -- 0:00:25
           5500 -- (-5752.598) (-5729.074) [-5728.114] (-5756.150) * (-5746.138) (-5725.008) (-5747.724) [-5735.613] -- 0:00:21
           4900 -- (-5765.212) [-5729.519] (-5735.090) (-5763.523) * (-5771.622) [-5736.175] (-5746.681) (-5765.647) -- 0:00:24
           5000 -- (-5769.111) [-5729.469] (-5731.255) (-5756.034) * (-5765.667) [-5738.547] (-5748.622) (-5775.086) -- 0:00:24
    
          Average standard deviation of split frequencies: 0.000000
    
           4900 -- (-5765.212) [-5729.519] (-5735.090) (-5763.523) * (-5771.622) [-5736.175] (-5746.681) (-5765.647) -- 0:00:24
           5600 -- (-5745.383) [-5730.773] (-5732.063) (-5749.216) * (-5747.493) (-5719.690) (-5742.623) [-5735.947] -- 0:00:20
           5000 -- (-5769.111) [-5729.469] (-5731.255) (-5756.034) * (-5765.667) [-5738.547] (-5748.622) (-5775.086) -- 0:00:24
    
          Average standard deviation of split frequencies: 0.000000
    
           5100 -- (-5766.691) [-5724.795] (-5730.254) (-5752.502) * (-5754.168) [-5734.828] (-5748.010) (-5759.884) -- 0:00:23
           5100 -- (-5766.691) [-5724.795] (-5730.254) (-5752.502) * (-5754.168) [-5734.828] (-5748.010) (-5759.884) -- 0:00:23
           5000 -- (-5769.111) [-5729.469] (-5731.255) (-5756.034) * (-5765.667) [-5738.547] (-5748.622) (-5775.086) -- 0:00:24
    
          Average standard deviation of split frequencies: 0.000000
    
           5700 -- (-5742.718) (-5732.627) [-5732.648] (-5756.803) * [-5740.893] (-5724.764) (-5733.538) (-5735.818) -- 0:00:20
           5200 -- (-5758.431) (-5722.197) [-5730.771] (-5754.512) * (-5755.271) (-5723.806) [-5742.037] (-5749.546) -- 0:00:25
           5200 -- (-5758.431) (-5722.197) [-5730.771] (-5754.512) * (-5755.271) (-5723.806) [-5742.037] (-5749.546) -- 0:00:25
           5100 -- (-5766.691) [-5724.795] (-5730.254) (-5752.502) * (-5754.168) [-5734.828] (-5748.010) (-5759.884) -- 0:00:26
           5800 -- [-5741.683] (-5730.215) (-5728.827) (-5754.803) * (-5741.341) (-5730.570) (-5734.455) [-5733.586] -- 0:00:22
           5300 -- (-5752.060) (-5730.073) [-5730.894] (-5754.820) * (-5752.571) (-5726.751) (-5740.839) [-5742.941] -- 0:00:24
           5300 -- (-5752.060) (-5730.073) [-5730.894] (-5754.820) * (-5752.571) (-5726.751) (-5740.839) [-5742.941] -- 0:00:24
           5400 -- (-5746.171) [-5727.443] (-5732.867) (-5757.073) * (-5746.814) [-5725.255] (-5751.844) (-5741.018) -- 0:00:24
           5200 -- (-5758.431) (-5722.197) [-5730.771] (-5754.512) * (-5755.271) (-5723.806) [-5742.037] (-5749.546) -- 0:00:25
           5400 -- (-5746.171) [-5727.443] (-5732.867) (-5757.073) * (-5746.814) [-5725.255] (-5751.844) (-5741.018) -- 0:00:24
           5900 -- (-5746.442) [-5727.987] (-5727.515) (-5751.152) * (-5747.644) (-5730.480) [-5733.741] (-5732.498) -- 0:00:21
           5500 -- (-5752.598) (-5729.074) [-5728.114] (-5756.150) * (-5746.138) (-5725.008) (-5747.724) [-5735.613] -- 0:00:23
           5500 -- (-5752.598) (-5729.074) [-5728.114] (-5756.150) * (-5746.138) (-5725.008) (-5747.724) [-5735.613] -- 0:00:23
           5300 -- (-5752.060) (-5730.073) [-5730.894] (-5754.820) * (-5752.571) (-5726.751) (-5740.839) [-5742.941] -- 0:00:24
           6000 -- (-5743.553) [-5730.659] (-5730.083) (-5754.410) * (-5749.157) [-5736.028] (-5733.360) (-5734.443) -- 0:00:21
    
          Average standard deviation of split frequencies: 0.001708
    
           5600 -- (-5745.383) [-5730.773] (-5732.063) (-5749.216) * (-5747.493) (-5719.690) (-5742.623) [-5735.947] -- 0:00:23
           5600 -- (-5745.383) [-5730.773] (-5732.063) (-5749.216) * (-5747.493) (-5719.690) (-5742.623) [-5735.947] -- 0:00:23
           5400 -- (-5746.171) [-5727.443] (-5732.867) (-5757.073) * (-5746.814) [-5725.255] (-5751.844) (-5741.018) -- 0:00:24
           6100 -- (-5736.472) (-5737.637) [-5728.925] (-5752.297) * (-5746.435) (-5740.118) [-5732.070] (-5739.048) -- 0:00:20
           5700 -- (-5742.718) (-5732.627) [-5732.648] (-5756.803) * [-5740.893] (-5724.764) (-5733.538) (-5735.818) -- 0:00:22
           5500 -- (-5752.598) (-5729.074) [-5728.114] (-5756.150) * (-5746.138) (-5725.008) (-5747.724) [-5735.613] -- 0:00:23
           5700 -- (-5742.718) (-5732.627) [-5732.648] (-5756.803) * [-5740.893] (-5724.764) (-5733.538) (-5735.818) -- 0:00:22
           5800 -- [-5741.683] (-5730.215) (-5728.827) (-5754.803) * (-5741.341) (-5730.570) (-5734.455) [-5733.586] -- 0:00:22
           6200 -- (-5736.663) (-5732.917) [-5725.189] (-5751.956) * (-5743.599) (-5741.521) [-5735.678] (-5732.935) -- 0:00:20
           5600 -- (-5745.383) [-5730.773] (-5732.063) (-5749.216) * (-5747.493) (-5719.690) (-5742.623) [-5735.947] -- 0:00:25
           5800 -- [-5741.683] (-5730.215) (-5728.827) (-5754.803) * (-5741.341) (-5730.570) (-5734.455) [-5733.586] -- 0:00:24
           5900 -- (-5746.442) [-5727.987] (-5727.515) (-5751.152) * (-5747.644) (-5730.480) [-5733.741] (-5732.498) -- 0:00:23
           5700 -- (-5742.718) (-5732.627) [-5732.648] (-5756.803) * [-5740.893] (-5724.764) (-5733.538) (-5735.818) -- 0:00:25
           6300 -- [-5735.226] (-5742.418) (-5729.513) (-5747.679) * (-5737.647) (-5741.488) (-5734.072) [-5737.010] -- 0:00:21
           6000 -- (-5743.553) [-5730.659] (-5730.083) (-5754.410) * (-5749.157) [-5736.028] (-5733.360) (-5734.443) -- 0:00:23
    
          Average standard deviation of split frequencies: 0.001708
    
           5900 -- (-5746.442) [-5727.987] (-5727.515) (-5751.152) * (-5747.644) (-5730.480) [-5733.741] (-5732.498) -- 0:00:23
           5800 -- [-5741.683] (-5730.215) (-5728.827) (-5754.803) * (-5741.341) (-5730.570) (-5734.455) [-5733.586] -- 0:00:24
           6100 -- (-5736.472) (-5737.637) [-5728.925] (-5752.297) * (-5746.435) (-5740.118) [-5732.070] (-5739.048) -- 0:00:22
           6400 -- (-5738.288) (-5737.122) (-5730.119) [-5743.984] * (-5735.470) (-5732.773) (-5732.856) [-5738.829] -- 0:00:21
           6000 -- (-5743.553) [-5730.659] (-5730.083) (-5754.410) * (-5749.157) [-5736.028] (-5733.360) (-5734.443) -- 0:00:23
    
          Average standard deviation of split frequencies: 0.001708
    
           5900 -- (-5746.442) [-5727.987] (-5727.515) (-5751.152) * (-5747.644) (-5730.480) [-5733.741] (-5732.498) -- 0:00:23
           6200 -- (-5736.663) (-5732.917) [-5725.189] (-5751.956) * (-5743.599) (-5741.521) [-5735.678] (-5732.935) -- 0:00:22
           6500 -- (-5743.370) (-5734.267) (-5734.430) [-5743.011] * (-5723.221) (-5739.013) [-5733.230] (-5735.750) -- 0:00:20
           6000 -- (-5743.553) [-5730.659] (-5730.083) (-5754.410) * (-5749.157) [-5736.028] (-5733.360) (-5734.443) -- 0:00:23
    
          Average standard deviation of split frequencies: 0.001708
    
           6100 -- (-5736.472) (-5737.637) [-5728.925] (-5752.297) * (-5746.435) (-5740.118) [-5732.070] (-5739.048) -- 0:00:22
           6300 -- [-5735.226] (-5742.418) (-5729.513) (-5747.679) * (-5737.647) (-5741.488) (-5734.072) [-5737.010] -- 0:00:21
           6600 -- [-5741.705] (-5729.456) (-5733.329) (-5740.190) * (-5731.475) (-5724.034) [-5726.151] (-5730.476) -- 0:00:20
           6100 -- (-5736.472) (-5737.637) [-5728.925] (-5752.297) * (-5746.435) (-5740.118) [-5732.070] (-5739.048) -- 0:00:22
           6200 -- (-5736.663) (-5732.917) [-5725.189] (-5751.956) * (-5743.599) (-5741.521) [-5735.678] (-5732.935) -- 0:00:22
           6400 -- (-5738.288) (-5737.122) (-5730.119) [-5743.984] * (-5735.470) (-5732.773) (-5732.856) [-5738.829] -- 0:00:21
           6700 -- (-5738.835) [-5729.409] (-5725.175) (-5746.714) * (-5731.896) [-5723.418] (-5731.950) (-5735.254) -- 0:00:19
           6200 -- (-5736.663) (-5732.917) [-5725.189] (-5751.956) * (-5743.599) (-5741.521) [-5735.678] (-5732.935) -- 0:00:22
           6300 -- [-5735.226] (-5742.418) (-5729.513) (-5747.679) * (-5737.647) (-5741.488) (-5734.072) [-5737.010] -- 0:00:23
           6500 -- (-5743.370) (-5734.267) (-5734.430) [-5743.011] * (-5723.221) (-5739.013) [-5733.230] (-5735.750) -- 0:00:22
           6800 -- (-5740.323) (-5729.093) [-5729.099] (-5750.796) * (-5733.497) (-5728.237) [-5730.322] (-5741.997) -- 0:00:21
           6300 -- [-5735.226] (-5742.418) (-5729.513) (-5747.679) * (-5737.647) (-5741.488) (-5734.072) [-5737.010] -- 0:00:23
           6900 -- [-5744.064] (-5724.369) (-5722.446) (-5749.664) * (-5728.168) [-5725.633] (-5728.376) (-5737.502) -- 0:00:20
           6400 -- (-5738.288) (-5737.122) (-5730.119) [-5743.984] * (-5735.470) (-5732.773) (-5732.856) [-5738.829] -- 0:00:23
           6400 -- (-5738.288) (-5737.122) (-5730.119) [-5743.984] * (-5735.470) (-5732.773) (-5732.856) [-5738.829] -- 0:00:23
           6600 -- [-5741.705] (-5729.456) (-5733.329) (-5740.190) * (-5731.475) (-5724.034) [-5726.151] (-5730.476) -- 0:00:22
           7000 -- (-5744.730) (-5723.904) [-5726.420] (-5745.641) * (-5723.905) (-5725.063) [-5734.751] (-5739.244) -- 0:00:20
    
          Average standard deviation of split frequencies: 0.001455
    
           6500 -- (-5743.370) (-5734.267) (-5734.430) [-5743.011] * (-5723.221) (-5739.013) [-5733.230] (-5735.750) -- 0:00:22
           6500 -- (-5743.370) (-5734.267) (-5734.430) [-5743.011] * (-5723.221) (-5739.013) [-5733.230] (-5735.750) -- 0:00:22
           6700 -- (-5738.835) [-5729.409] (-5725.175) (-5746.714) * (-5731.896) [-5723.418] (-5731.950) (-5735.254) -- 0:00:21
           7100 -- (-5744.049) [-5724.324] (-5726.993) (-5742.410) * [-5725.341] (-5721.999) (-5735.703) (-5740.701) -- 0:00:19
           6600 -- [-5741.705] (-5729.456) (-5733.329) (-5740.190) * (-5731.475) (-5724.034) [-5726.151] (-5730.476) -- 0:00:22
           6800 -- (-5740.323) (-5729.093) [-5729.099] (-5750.796) * (-5733.497) (-5728.237) [-5730.322] (-5741.997) -- 0:00:21
           6600 -- [-5741.705] (-5729.456) (-5733.329) (-5740.190) * (-5731.475) (-5724.034) [-5726.151] (-5730.476) -- 0:00:22
           7200 -- (-5740.200) [-5724.728] (-5733.697) (-5742.521) * [-5729.343] (-5727.104) (-5738.152) (-5742.233) -- 0:00:19
           6700 -- (-5738.835) [-5729.409] (-5725.175) (-5746.714) * (-5731.896) [-5723.418] (-5731.950) (-5735.254) -- 0:00:21
           7300 -- (-5735.058) (-5728.465) [-5727.678] (-5741.053) * (-5736.153) [-5726.145] (-5733.910) (-5742.443) -- 0:00:19
           6800 -- (-5740.323) (-5729.093) [-5729.099] (-5750.796) * (-5733.497) (-5728.237) [-5730.322] (-5741.997) -- 0:00:21
           6900 -- [-5744.064] (-5724.369) (-5722.446) (-5749.664) * (-5728.168) [-5725.633] (-5728.376) (-5737.502) -- 0:00:20
           6700 -- (-5738.835) [-5729.409] (-5725.175) (-5746.714) * (-5731.896) [-5723.418] (-5731.950) (-5735.254) -- 0:00:21
           7400 -- (-5734.965) (-5724.648) [-5728.481] (-5746.892) * (-5731.174) [-5730.834] (-5740.025) (-5739.095) -- 0:00:18
           6900 -- [-5744.064] (-5724.369) (-5722.446) (-5749.664) * (-5728.168) [-5725.633] (-5728.376) (-5737.502) -- 0:00:20
           7000 -- (-5744.730) (-5723.904) [-5726.420] (-5745.641) * (-5723.905) (-5725.063) [-5734.751] (-5739.244) -- 0:00:20
    
          Average standard deviation of split frequencies: 0.001455
    
           6800 -- (-5740.323) (-5729.093) [-5729.099] (-5750.796) * (-5733.497) (-5728.237) [-5730.322] (-5741.997) -- 0:00:21
           7500 -- (-5736.041) [-5727.860] (-5723.953) (-5745.809) * (-5726.806) [-5727.206] (-5737.097) (-5730.264) -- 0:00:18
           7000 -- (-5744.730) (-5723.904) [-5726.420] (-5745.641) * (-5723.905) (-5725.063) [-5734.751] (-5739.244) -- 0:00:20
    
          Average standard deviation of split frequencies: 0.001455
    
           7100 -- (-5744.049) [-5724.324] (-5726.993) (-5742.410) * [-5725.341] (-5721.999) (-5735.703) (-5740.701) -- 0:00:21
           6900 -- [-5744.064] (-5724.369) (-5722.446) (-5749.664) * (-5728.168) [-5725.633] (-5728.376) (-5737.502) -- 0:00:22
           7600 -- (-5733.621) (-5722.231) [-5724.634] (-5745.887) * (-5730.728) (-5726.395) [-5735.874] (-5730.867) -- 0:00:19
           7100 -- (-5744.049) [-5724.324] (-5726.993) (-5742.410) * [-5725.341] (-5721.999) (-5735.703) (-5740.701) -- 0:00:21
           7200 -- (-5740.200) [-5724.728] (-5733.697) (-5742.521) * [-5729.343] (-5727.104) (-5738.152) (-5742.233) -- 0:00:21
           7000 -- (-5744.730) (-5723.904) [-5726.420] (-5745.641) * (-5723.905) (-5725.063) [-5734.751] (-5739.244) -- 0:00:22
    
          Average standard deviation of split frequencies: 0.001455
    
           7700 -- (-5727.996) [-5724.889] (-5730.333) (-5745.149) * (-5735.388) (-5728.957) [-5727.127] (-5737.751) -- 0:00:19
           7200 -- (-5740.200) [-5724.728] (-5733.697) (-5742.521) * [-5729.343] (-5727.104) (-5738.152) (-5742.233) -- 0:00:21
           7300 -- (-5735.058) (-5728.465) [-5727.678] (-5741.053) * (-5736.153) [-5726.145] (-5733.910) (-5742.443) -- 0:00:20
           7100 -- (-5744.049) [-5724.324] (-5726.993) (-5742.410) * [-5725.341] (-5721.999) (-5735.703) (-5740.701) -- 0:00:21
           7800 -- (-5727.781) [-5724.382] (-5735.162) (-5736.647) * (-5730.092) [-5725.157] (-5730.569) (-5732.569) -- 0:00:18
           7300 -- (-5735.058) (-5728.465) [-5727.678] (-5741.053) * (-5736.153) [-5726.145] (-5733.910) (-5742.443) -- 0:00:20
           7400 -- (-5734.965) (-5724.648) [-5728.481] (-5746.892) * (-5731.174) [-5730.834] (-5740.025) (-5739.095) -- 0:00:20
           7900 -- (-5725.840) (-5724.659) [-5732.508] (-5732.543) * [-5726.425] (-5726.648) (-5739.700) (-5732.791) -- 0:00:18
           7200 -- (-5740.200) [-5724.728] (-5733.697) (-5742.521) * [-5729.343] (-5727.104) (-5738.152) (-5742.233) -- 0:00:21
           7400 -- (-5734.965) (-5724.648) [-5728.481] (-5746.892) * (-5731.174) [-5730.834] (-5740.025) (-5739.095) -- 0:00:20
           7500 -- (-5736.041) [-5727.860] (-5723.953) (-5745.809) * (-5726.806) [-5727.206] (-5737.097) (-5730.264) -- 0:00:20
           7300 -- (-5735.058) (-5728.465) [-5727.678] (-5741.053) * (-5736.153) [-5726.145] (-5733.910) (-5742.443) -- 0:00:20
           8000 -- [-5726.183] (-5723.910) (-5732.217) (-5739.800) * [-5730.628] (-5723.441) (-5738.161) (-5733.204) -- 0:00:18
    
          Average standard deviation of split frequencies: 0.001288
    
           7600 -- (-5733.621) (-5722.231) [-5724.634] (-5745.887) * (-5730.728) (-5726.395) [-5735.874] (-5730.867) -- 0:00:19
           7500 -- (-5736.041) [-5727.860] (-5723.953) (-5745.809) * (-5726.806) [-5727.206] (-5737.097) (-5730.264) -- 0:00:20
           7400 -- (-5734.965) (-5724.648) [-5728.481] (-5746.892) * (-5731.174) [-5730.834] (-5740.025) (-5739.095) -- 0:00:20
           8100 -- (-5728.586) [-5720.844] (-5724.415) (-5732.461) * (-5731.344) [-5728.834] (-5735.099) (-5735.367) -- 0:00:17
           7700 -- (-5727.996) [-5724.889] (-5730.333) (-5745.149) * (-5735.388) (-5728.957) [-5727.127] (-5737.751) -- 0:00:19
           7600 -- (-5733.621) (-5722.231) [-5724.634] (-5745.887) * (-5730.728) (-5726.395) [-5735.874] (-5730.867) -- 0:00:19
           7500 -- (-5736.041) [-5727.860] (-5723.953) (-5745.809) * (-5726.806) [-5727.206] (-5737.097) (-5730.264) -- 0:00:21
           8200 -- (-5726.756) (-5721.446) (-5721.697) [-5734.363] * [-5726.169] (-5726.302) (-5733.560) (-5732.003) -- 0:00:18
           7800 -- (-5727.781) [-5724.382] (-5735.162) (-5736.647) * (-5730.092) [-5725.157] (-5730.569) (-5732.569) -- 0:00:20
           7700 -- (-5727.996) [-5724.889] (-5730.333) (-5745.149) * (-5735.388) (-5728.957) [-5727.127] (-5737.751) -- 0:00:20
           8300 -- (-5732.022) (-5722.169) [-5728.406] (-5735.689) * (-5727.833) [-5722.760] (-5729.993) (-5733.681) -- 0:00:18
           7600 -- (-5733.621) (-5722.231) [-5724.634] (-5745.887) * (-5730.728) (-5726.395) [-5735.874] (-5730.867) -- 0:00:21
           7900 -- (-5725.840) (-5724.659) [-5732.508] (-5732.543) * [-5726.425] (-5726.648) (-5739.700) (-5732.791) -- 0:00:19
           7800 -- (-5727.781) [-5724.382] (-5735.162) (-5736.647) * (-5730.092) [-5725.157] (-5730.569) (-5732.569) -- 0:00:20
           8400 -- (-5740.352) [-5719.719] (-5732.710) (-5727.399) * [-5729.923] (-5725.364) (-5730.043) (-5731.316) -- 0:00:17
           8000 -- [-5726.183] (-5723.910) (-5732.217) (-5739.800) * [-5730.628] (-5723.441) (-5738.161) (-5733.204) -- 0:00:19
    
          Average standard deviation of split frequencies: 0.001288
    
           7700 -- (-5727.996) [-5724.889] (-5730.333) (-5745.149) * (-5735.388) (-5728.957) [-5727.127] (-5737.751) -- 0:00:20
           7900 -- (-5725.840) (-5724.659) [-5732.508] (-5732.543) * [-5726.425] (-5726.648) (-5739.700) (-5732.791) -- 0:00:19
           8500 -- (-5731.410) [-5719.833] (-5730.232) (-5732.842) * (-5731.553) [-5720.166] (-5728.363) (-5727.029) -- 0:00:17
           8000 -- [-5726.183] (-5723.910) (-5732.217) (-5739.800) * [-5730.628] (-5723.441) (-5738.161) (-5733.204) -- 0:00:19
    
          Average standard deviation of split frequencies: 0.001288
    
           8100 -- (-5728.586) [-5720.844] (-5724.415) (-5732.461) * (-5731.344) [-5728.834] (-5735.099) (-5735.367) -- 0:00:19
           7800 -- (-5727.781) [-5724.382] (-5735.162) (-5736.647) * (-5730.092) [-5725.157] (-5730.569) (-5732.569) -- 0:00:20
           8600 -- [-5729.906] (-5720.347) (-5722.266) (-5725.722) * (-5726.647) [-5719.062] (-5727.316) (-5726.882) -- 0:00:17
           8100 -- (-5728.586) [-5720.844] (-5724.415) (-5732.461) * (-5731.344) [-5728.834] (-5735.099) (-5735.367) -- 0:00:19
           8200 -- (-5726.756) (-5721.446) (-5721.697) [-5734.363] * [-5726.169] (-5726.302) (-5733.560) (-5732.003) -- 0:00:18
           8700 -- (-5724.946) (-5724.318) [-5727.270] (-5722.736) * (-5732.397) (-5719.706) [-5721.750] (-5731.842) -- 0:00:16
           7900 -- (-5725.840) (-5724.659) [-5732.508] (-5732.543) * [-5726.425] (-5726.648) (-5739.700) (-5732.791) -- 0:00:19
           8200 -- (-5726.756) (-5721.446) (-5721.697) [-5734.363] * [-5726.169] (-5726.302) (-5733.560) (-5732.003) -- 0:00:18
           8800 -- (-5726.648) (-5725.421) (-5720.381) [-5725.573] * (-5739.793) (-5721.052) [-5720.941] (-5734.413) -- 0:00:16
           8300 -- (-5732.022) (-5722.169) [-5728.406] (-5735.689) * (-5727.833) [-5722.760] (-5729.993) (-5733.681) -- 0:00:18
           8000 -- [-5726.183] (-5723.910) (-5732.217) (-5739.800) * [-5730.628] (-5723.441) (-5738.161) (-5733.204) -- 0:00:19
    
          Average standard deviation of split frequencies: 0.001288
    
           8900 -- (-5729.377) [-5720.744]        8300 -- (-5732.022) (-5722.169) [-5728.406] (-5735.689) * (-5725.026) (-5730.678) * (-5731.020) (-5727.563) (-5727.833) [-5722.760] (-5729.993) (-5733.681) -- 0:00:18[-5719.635] (-5731.000) 
    -- 0:00:16
           8100 -- (-5728.586) [-5720.844] (-5724.415) (-5732.461) * (-5731.344) [-5728.834] (-5735.099) (-5735.367) -- 0:00:20
           8400 -- (-5740.352) [-5719.719] (-5732.710) (-5727.399) * [-5729.923] (-5725.364) (-5730.043) (-5731.316) -- 0:00:19
           9000 -- (-5726.077) (-5726.677) [-5723.487] (-5731.761) * (-5732.141) (-5728.763) [-5721.707] (-5727.971) -- 0:00:17
    
          Average standard deviation of split frequencies: 0.001139
    
           8200 -- (-5726.756) (-5721.446) (-5721.697) [-5734.363] * [-5726.169] (-5726.302) (-5733.560) (-5732.003) -- 0:00:20
           8400 -- (-5740.352) [-5719.719] (-5732.710) (-5727.399) * [-5729.923] (-5725.364) (-5730.043) (-5731.316) -- 0:00:19
           8500 -- (-5731.410) [-5719.833] (-5730.232) (-5732.842) * (-5731.553) [-5720.166] (-5728.363) (-5727.029) -- 0:00:18
           9100 -- (-5723.045) (-5732.405) [-5724.735] (-5733.206) * (-5733.648) (-5724.061) [-5722.886] (-5727.168) -- 0:00:16
           8300 -- (-5732.022) (-5722.169) [-5728.406] (-5735.689) * (-5727.833) [-5722.760] (-5729.993) (-5733.681) -- 0:00:19
           8500 -- (-5731.410) [-5719.833] (-5730.232) (-5732.842) * (-5731.553) [-5720.166] (-5728.363) (-5727.029) -- 0:00:18
           9200 -- (-5724.200) (-5731.354) [-5720.636] (-5732.604) * (-5735.137) (-5723.359) [-5727.435] (-5730.529) -- 0:00:16
           8600 -- [-5729.906] (-5720.347) (-5722.266) (-5725.722) * (-5726.647) [-5719.062] (-5727.316) (-5726.882) -- 0:00:18
           8400 -- (-5740.352) [-5719.719] (-5732.710) (-5727.399) * [-5729.923] (-5725.364) (-5730.043) (-5731.316) -- 0:00:19
           9300 -- [-5721.991] (-5727.592) (-5721.925) (-5728.239) * (-5721.534) (-5725.740) [-5726.783] (-5729.507) -- 0:00:16
           8600 -- [-5729.906] (-5720.347) (-5722.266) (-5725.722) * (-5726.647) [-5719.062] (-5727.316) (-5726.882) -- 0:00:18
           8500 -- (-5731.410) [-5719.833] (-5730.232) (-5732.842) * (-5731.553) [-5720.166] (-5728.363) (-5727.029) -- 0:00:18
           8700 -- (-5724.946) (-5724.318) [-5727.270] (-5722.736) * (-5732.397) (-5719.706) [-5721.750] (-5731.842) -- 0:00:18
           9400 -- (-5729.327) (-5731.239) [-5725.349] (-5722.658) * [-5723.947] (-5733.197) (-5725.057) (-5726.895) -- 0:00:15
           8600 -- [-5729.906] (-5720.347) (-5722.266) (-5725.722) * (-5726.647) [-5719.062] (-5727.316) (-5726.882) -- 0:00:18
           8700 -- (-5724.946) (-5724.318) [-5727.270] (-5722.736) * (-5732.397) (-5719.706) [-5721.750] (-5731.842) -- 0:00:18
           8800 -- (-5726.648) (-5725.421) (-5720.381) [-5725.573] * (-5739.793) (-5721.052) [-5720.941] (-5734.413) -- 0:00:17
           9500 -- (-5730.380) [-5727.390] (-5725.833) (-5730.686) * [-5725.338] (-5730.566) (-5721.734) (-5730.257) -- 0:00:15
           8700 -- (-5724.946) (-5724.318) [-5727.270] (-5722.736) * (-5732.397) (-5719.706) [-5721.750] (-5731.842) -- 0:00:18
           8800 -- (-5726.648) (-5725.421) (-5720.381) [-5725.573] * (-5739.793) (-5721.052) [-5720.941] (-5734.413) -- 0:00:17
           8900 -- (-5729.377) [-5720.744] (-5725.026) (-5730.678) * (-5731.020) (-5727.563) [-5719.635] (-5731.000) -- 0:00:17
           9600 -- (-5724.955) (-5723.965) [-5721.996] (-5722.744) * [-5724.616] (-5728.762) (-5724.218) (-5723.309) -- 0:00:15
           8800 -- (-5726.648) (-5725.421) (-5720.381) [-5725.573] * (-5739.793) (-5721.052) [-5720.941] (-5734.413) -- 0:00:17
           8900 -- (-5729.377) [-5720.744] (-5725.026) (-5730.678) * (-5731.020) (-5727.563) [-5719.635] (-5731.000) -- 0:00:17
           9000 -- (-5726.077) (-5726.677) [-5723.487] (-5731.761) * (-5732.141) (-5728.763) [-5721.707] (-5727.971) -- 0:00:18
    
          Average standard deviation of split frequencies: 0.001139
    
           9700 -- (-5724.709) (-5726.159) [-5726.824] (-5721.529) * (-5737.113) (-5724.250) [-5721.678] (-5720.893) -- 0:00:15
           8900 -- (-5729.377) [-5720.744] (-5725.026) (-5730.678) * (-5731.020) (-5727.563) [-5719.635] (-5731.000) -- 0:00:18
           9000 -- (-5726.077) (-5726.677) [-5723.487] (-5731.761) * (-5732.141) (-5728.763) [-5721.707] (-5727.971) -- 0:00:18
    
          Average standard deviation of split frequencies: 0.001139
    
           9100 -- (-5723.045) (-5732.405) [-5724.735] (-5733.206) * (-5733.648) (-5724.061) [-5722.886] (-5727.168) -- 0:00:17
           9000 -- (-5726.077) (-5726.677) [-5723.487] (-5731.761) * (-5732.141) (-5728.763) [-5721.707] (-5727.971) -- 0:00:18
    
          Average standard deviation of split frequencies: 0.001139
    
           9800 -- (-5726.695) (-5722.500) (-5725.940) [-5724.450] * (-5734.677) (-5725.489) [-5718.459] (-5722.481) -- 0:00:15
           9100 -- (-5723.045) (-5732.405) [-5724.735] (-5733.206) * (-5733.648) (-5724.061) [-5722.886] (-5727.168) -- 0:00:17
           9200 -- (-5724.200) (-5731.354) [-5720.636] (-5732.604) * (-5735.137) (-5723.359) [-5727.435] (-5730.529) -- 0:00:17
           9100 -- (-5723.045) (-5732.405) [-5724.735] (-5733.206) * (-5733.648) (-5724.061) [-5722.886] (-5727.168) -- 0:00:17
           9900 -- (-5730.309) (-5722.643) (-5743.964) [-5723.915] * (-5737.200) (-5728.500) (-5722.491) [-5724.985] -- 0:00:15
           9200 -- (-5724.200) (-5731.354) [-5720.636] (-5732.604) * (-5735.137) (-5723.359) [-5727.435] (-5730.529) -- 0:00:17
           9300 -- [-5721.991] (-5727.592) (-5721.925) (-5728.239) * (-5721.534) (-5725.740) [-5726.783] (-5729.507) -- 0:00:17
           9200 -- (-5724.200) (-5731.354) [-5720.636] (-5732.604) * (-5735.137) (-5723.359) [-5727.435] (-5730.529) -- 0:00:17
          10000 -- (-5728.517) [-5717.188] (-5736.363) (-5723.559) * (-5727.804) (-5722.700) (-5720.362) [-5724.409] -- 0:00:15
    
          Average standard deviation of split frequencies: 0.001034
    
           9300 -- [-5721.991] (-5727.592) (-5721.925) (-5728.239) * (-5721.534) (-5725.740) [-5726.783] (-5729.507) -- 0:00:17
           9400 -- (-5729.327) (-5731.239) [-5725.349] (-5722.658) * [-5723.947] (-5733.197) (-5725.057) (-5726.895) -- 0:00:16
           9300 -- [-5721.991] (-5727.592) (-5721.925) (-5728.239) * (-5721.534) (-5725.740) [-5726.783] (-5729.507) -- 0:00:17
           9400 -- (-5729.327) (-5731.239) [-5725.349] (-5722.658) * [-5723.947] (-5733.197) (-5725.057) (-5726.895) -- 0:00:16
          10100 -- (-5735.995) [-5719.363] (-5724.096) (-5721.395) * (-5735.238) [-5721.244] (-5721.190) (-5723.230) -- 0:00:14
           9500 -- (-5730.380) [-5727.390] (-5725.833) (-5730.686) * [-5725.338] (-5730.566) (-5721.734) (-5730.257) -- 0:00:16
           9400 -- (-5729.327) (-5731.239) [-5725.349] (-5722.658) * [-5723.947] (-5733.197) (-5725.057) (-5726.895) -- 0:00:16
          10200 -- (-5726.701) [-5717.904] (-5723.350) (-5718.789) * (-5735.703) (-5722.635) (-5721.016) [-5717.744] -- 0:00:14
           9500 -- (-5730.380) [-5727.390] (-5725.833) (-5730.686) * [-5725.338] (-5730.566) (-5721.734) (-5730.257) -- 0:00:16
           9600 -- (-5724.955) (-5723.965) [-5721.996] (-5722.744) * [-5724.616] (-5728.762) (-5724.218) (-5723.309) -- 0:00:16
           9500 -- (-5730.380) [-5727.390] (-5725.833) (-5730.686) * [-5725.338] (-5730.566) (-5721.734) (-5730.257) -- 0:00:16
          10300 -- [-5731.448] (-5724.489) (-5731.047) (-5728.046) * (-5734.056) (-5725.980) (-5720.987) [-5719.382] -- 0:00:14
           9600 -- (-5724.955) (-5723.965) [-5721.996] (-5722.744) * [-5724.616] (-5728.762) (-5724.218) (-5723.309) -- 0:00:16
           9700 -- (-5724.709) (-5726.159) [-5726.824] (-5721.529) * (-5737.113) (-5724.250) [-5721.678] (-5720.893) -- 0:00:16
          10400 -- (-5728.485) (-5719.834) [-5728.785] (-5721.922) * (-5732.822) (-5734.118) [-5722.121] (-5722.994) -- 0:00:14
           9600 -- (-5724.955) (-5723.965) [-5721.996] (-5722.744) * [-5724.616] (-5728.762) (-5724.218) (-5723.309) -- 0:00:17
           9800 -- (-5726.695) (-5722.500) (-5725.940) [-5724.450] * (-5734.677) (-5725.489) [-5718.459] (-5722.481) -- 0:00:16
           9700 -- (-5724.709) (-5726.159) [-5726.824] (-5721.529) * (-5737.113) (-5724.250) [-5721.678] (-5720.893) -- 0:00:16
           9900 -- (-5730.309) (-5722.643) (-5743.964) [-5723.915] * (-5737.200) (-5728.500) (-5722.491) [-5724.985] -- 0:00:16
          10500 -- (-5726.157) (-5717.962) (-5729.250) [-5722.883] * (-5727.731) (-5734.726) (-5723.085) [-5725.918] -- 0:00:14
           9700 -- (-5724.709) (-5726.159) [-5726.824] (-5721.529) * (-5737.113) (-5724.250) [-5721.678] (-5720.893) -- 0:00:16
           9800 -- (-5726.695) (-5722.500) (-5725.940) [-5724.450] * (-5734.677) (-5725.489) [-5718.459] (-5722.481) -- 0:00:16
          10000 -- (-5728.517) [-5717.188] (-5736.363) (-5723.559) * (-5727.804) (-5722.700) (-5720.362) [-5724.409] -- 0:00:16
    
          Average standard deviation of split frequencies: 0.001034
    
          10600 -- (-5731.968) (-5717.004) [-5725.074] (-5723.964) * (-5725.380) (-5730.054) [-5723.685] (-5730.575) -- 0:00:14
           9800 -- (-5726.695) (-5722.500) (-5725.940) [-5724.450] * (-5734.677) (-5725.489) [-5718.459] (-5722.481) -- 0:00:16
          10100 -- (-5735.995) [-5719.363] (-5724.096) (-5721.395) * (-5735.238) [-5721.244] (-5721.190) (-5723.230) -- 0:00:15
           9900 -- (-5730.309) (-5722.643) (-5743.964) [-5723.915] * (-5737.200) (-5728.500) (-5722.491) [-5724.985] -- 0:00:16
          10700 -- (-5726.652) (-5720.267) [-5722.155] (-5727.143) * (-5731.834) (-5732.950) (-5717.560) [-5726.022] -- 0:00:13
          10000 -- (-5728.517) [-5717.188] (-5736.363) (-5723.559) * (-5727.804) (-5722.700) (-5720.362) [-5724.409] -- 0:00:16
           9900 -- (-5730.309) (-5722.643) (-5743.964) [-5723.915] * (-5737.200) (-5728.500) (-5722.491) [-5724.985] -- 0:00:16
    
          Average standard deviation of split frequencies: 0.001034
    
          10200 -- (-5726.701) [-5717.904] (-5723.350) (-5718.789) * (-5735.703) (-5722.635) (-5721.016) [-5717.744] -- 0:00:15
          10800 -- (-5719.967) [-5721.376] (-5716.193) (-5726.481) * (-5728.673) [-5732.770] (-5719.363) (-5733.236) -- 0:00:13
          10000 -- (-5728.517) [-5717.188] (-5736.363) (-5723.559) * (-5727.804) (-5722.700) (-5720.362) [-5724.409] -- 0:00:16
    
          Average standard deviation of split frequencies: 0.001034
    
          10100 -- (-5735.995) [-5719.363] (-5724.096) (-5721.395) * (-5735.238) [-5721.244] (-5721.190) (-5723.230) -- 0:00:15
          10300 -- [-5731.448] (-5724.489) (-5731.047) (-5728.046) * (-5734.056) (-5725.980) (-5720.987) [-5719.382] -- 0:00:15
          10900 -- (-5722.423) [-5724.365] (-5715.524) (-5728.063) * (-5733.850) (-5726.617) [-5721.100] (-5734.834) -- 0:00:13
          10100 -- (-5735.995) [-5719.363] (-5724.096) (-5721.395) * (-5735.238) [-5721.244] (-5721.190) (-5723.230) -- 0:00:15
          10200 -- (-5726.701) [-5717.904] (-5723.350) (-5718.789) * (-5735.703) (-5722.635) (-5721.016) [-5717.744] -- 0:00:15
          10400 -- (-5728.485) (-5719.834) [-5728.785] (-5721.922) * (-5732.822) (-5734.118) [-5722.121] (-5722.994) -- 0:00:14
          11000 -- (-5725.257) (-5728.117) [-5719.779] (-5729.126) * (-5734.161) [-5729.041] (-5723.785) (-5733.908) -- 0:00:13
    
          Average standard deviation of split frequencies: 0.001871
    
          10200 -- (-5726.701) [-5717.904] (-5723.350) (-5718.789) * (-5735.703) (-5722.635) (-5721.016) [-5717.744] -- 0:00:15
          10300 -- [-5731.448] (-5724.489) (-5731.047) (-5728.046) * (-5734.056) (-5725.980) (-5720.987) [-5719.382] -- 0:00:15
          10500 -- (-5726.157) (-5717.962) (-5729.250) [-5722.883] * (-5727.731) (-5734.726) (-5723.085) [-5725.918] -- 0:00:14
          11100 -- [-5720.340] (-5730.757) (-5720.135) (-5719.775) * (-5738.977) (-5733.070) [-5722.174] (-5732.403) -- 0:00:13
          10300 -- [-5731.448] (-5724.489) (-5731.047) (-5728.046) * (-5734.056) (-5725.980) (-5720.987) [-5719.382] -- 0:00:16
          10400 -- (-5728.485) (-5719.834) [-5728.785] (-5721.922) * (-5732.822) (-5734.118) [-5722.121] (-5722.994) -- 0:00:15
          11200 -- (-5726.638) (-5727.246) (-5725.653) [-5725.660] * (-5737.882) (-5729.733) [-5722.162] (-5726.755) -- 0:00:13
          10600 -- (-5731.968) (-5717.004) [-5725.074] (-5723.964) * (-5725.380) (-5730.054) [-5723.685] (-5730.575) -- 0:00:15
          10400 -- (-5728.485) (-5719.834) [-5728.785] (-5721.922) * (-5732.822) (-5734.118) [-5722.121] (-5722.994) -- 0:00:15
          10500 -- (-5726.157) (-5717.962) (-5729.250) [-5722.883] * (-5727.731) (-5734.726) (-5723.085) [-5725.918] -- 0:00:15
          11300 -- (-5726.368) [-5721.965] (-5729.896) (-5727.838) * (-5735.893) [-5724.914] (-5721.700) (-5730.304) -- 0:00:13
          10500 -- (-5726.157) (-5717.962) (-5729.250) [-5722.883] * (-5727.731) (-5734.726) (-5723.085) [-5725.918] -- 0:00:15
          10700 -- (-5726.652) (-5720.267) [-5722.155] (-5727.143) * (-5731.834) (-5732.950) (-5717.560) [-5726.022] -- 0:00:14
          10600 -- (-5731.968) (-5717.004) [-5725.074] (-5723.964) * (-5725.380) (-5730.054) [-5723.685] (-5730.575) -- 0:00:15
          11400 -- [-5721.737] (-5720.679) (-5734.962) (-5730.160) * (-5739.444) (-5730.506) [-5719.829] (-5727.907) -- 0:00:12
          10600 -- (-5731.968) (-5717.004) [-5725.074] (-5723.964) * (-5725.380) (-5730.054) [-5723.685] (-5730.575) -- 0:00:15
          10800 -- (-5719.967) [-5721.376] (-5716.193) (-5726.481) * (-5728.673) [-5732.770] (-5719.363) (-5733.236) -- 0:00:14
          10700 -- (-5726.652) (-5720.267) [-5722.155] (-5727.143) * (-5731.834) (-5732.950) (-5717.560) [-5726.022] -- 0:00:14
          11500 -- [-5722.822] (-5722.036) (-5724.492) (-5731.860) * (-5735.513) (-5729.273) [-5720.300] (-5733.004) -- 0:00:12
          10700 -- (-5726.652) (-5720.267) [-5722.155] (-5727.143) * (-5731.834) (-5732.950) (-5717.560) [-5726.022] -- 0:00:14
          10900 -- (-5722.423) [-5724.365] (-5715.524) (-5728.063) * (-5733.850) (-5726.617) [-5721.100] (-5734.834) -- 0:00:14
          10800 -- (-5719.967) [-5721.376] (-5716.193) (-5726.481) * (-5728.673) [-5732.770] (-5719.363) (-5733.236) -- 0:00:14
          10800 -- (-5719.967) [-5721.376] (-5716.193) (-5726.481) * (-5728.673) [-5732.770] (-5719.363) (-5733.236) -- 0:00:14
          11600 -- [-5727.799] (-5728.655) (-5728.852) (-5732.873) * (-5729.607) [-5725.569] (-5728.140) (-5718.391) -- 0:00:12
          11000 -- (-5725.257)       10900 -- (-5722.423) [-5724.365] (-5715.524) (-5728.063) * (-5733.850) (-5726.617) [-5721.100] (-5734.834) -- 0:00:14
    (-5728.117) [-5719.779] (-5729.126) * (-5734.161) [-5729.041] (-5723.785) (-5733.908) -- 0:00:13
    
          Average standard deviation of split frequencies: 0.001871
    
          11700 -- (-5735.289) (-5725.228) [-5725.992] (-5729.943) * (-5729.358) (-5730.407) (-5730.201) [-5721.423] -- 0:00:12
          10900 -- (-5722.423) [-5724.365] (-5715.524) (-5728.063) * (-5733.850) (-5726.617) [-5721.100] (-5734.834) -- 0:00:14
          11100 -- [-5720.340] (-5730.757) (-5720.135) (-5719.775) * (-5738.977) (-5733.070) [-5722.174] (-5732.403) -- 0:00:13
          11000 -- (-5725.257) (-5728.117) [-5719.779] (-5729.126) * (-5734.161) [-5729.041] (-5723.785) (-5733.908) -- 0:00:13
    
          Average standard deviation of split frequencies: 0.001871
    
          11800 -- (-5733.338) (-5737.474) [-5724.400] (-5727.480) * (-5730.937) (-5728.018) [-5729.014] (-5723.934) -- 0:00:11
          11000 -- (-5725.257) (-5728.117) [-5719.779] (-5729.126) * (-5734.161) [-5729.041] (-5723.785) (-5733.908) -- 0:00:13
    
          Average standard deviation of split frequencies: 0.001871
    
          11200 -- (-5726.638) (-5727.246) (-5725.653) [-5725.660] * (-5737.882) (-5729.733) [-5722.162] (-5726.755) -- 0:00:14
          11900 -- (-5726.424) (-5732.089) [-5723.252] (-5735.073) * (-5727.007) [-5722.773] (-5725.119) (-5723.347) -- 0:00:12
          11100 -- [-5720.340] (-5730.757) (-5720.135) (-5719.775) * (-5738.977) (-5733.070) [-5722.174] (-5732.403) -- 0:00:14
          11300 -- (-5726.368) [-5721.965] (-5729.896) (-5727.838) * (-5735.893) [-5724.914] (-5721.700) (-5730.304) -- 0:00:13
          11100 -- [-5720.340] (-5730.757) (-5720.135) (-5719.775) * (-5738.977) (-5733.070) [-5722.174] (-5732.403) -- 0:00:14
          12000 -- (-5723.357) [-5734.877] (-5725.660) (-5720.223) * (-5736.824) (-5725.159) (-5730.894) [-5725.843] -- 0:00:12
    
          Average standard deviation of split frequencies: 0.001727
    
          11200 -- (-5726.638) (-5727.246) (-5725.653) [-5725.660] * (-5737.882) (-5729.733) [-5722.162] (-5726.755) -- 0:00:14
          11400 -- [-5721.737] (-5720.679) (-5734.962) (-5730.160) * (-5739.444) (-5730.506) [-5719.829] (-5727.907) -- 0:00:13
          12100 -- [-5728.497] (-5731.761) (-5729.328) (-5722.507) * (-5728.662) [-5723.481] (-5729.149) (-5728.633) -- 0:00:11
          11200 -- (-5726.638) (-5727.246) (-5725.653) [-5725.660] * (-5737.882) (-5729.733) [-5722.162] (-5726.755) -- 0:00:14
          11500 -- [-5722.822] (-5722.036) (-5724.492) (-5731.860) * (-5735.513) (-5729.273) [-5720.300] (-5733.004) -- 0:00:13
          11300 -- (-5726.368) [-5721.965] (-5729.896) (-5727.838) * (-5735.893) [-5724.914] (-5721.700) (-5730.304) -- 0:00:13
          12200 -- [-5737.149] (-5733.500) (-5733.184) (-5724.066) * (-5730.053) [-5726.114] (-5732.434) (-5725.705) -- 0:00:11
          11300 -- (-5726.368) [-5721.965] (-5729.896) (-5727.838) * (-5735.893) [-5724.914] (-5721.700) (-5730.304) -- 0:00:13
          11600 -- [-5727.799] (-5728.655) (-5728.852) (-5732.873) * (-5729.607) [-5725.569] (-5728.140) (-5718.391) -- 0:00:13
          12300 -- (-5735.175) (-5725.407) [-5728.778] (-5728.061) * (-5731.795) [-5723.837] (-5731.560) (-5731.337) -- 0:00:11
          11400 -- [-5721.737] (-5720.679) (-5734.962) (-5730.160) * (-5739.444) (-5730.506) [-5719.829] (-5727.907) -- 0:00:13
          11400 -- [-5721.737] (-5720.679) (-5734.962) (-5730.160) * (-5739.444) (-5730.506) [-5719.829] (-5727.907) -- 0:00:13
          11700 -- (-5735.289) (-5725.228) [-5725.992] (-5729.943) * (-5729.358) (-5730.407) (-5730.201) [-5721.423] -- 0:00:12
          12400 -- (-5724.230) [-5726.981] (-5727.067) (-5720.132) * (-5737.250) [-5728.183] (-5732.079) (-5731.944) -- 0:00:11
          11500 -- [-5722.822] (-5722.036) (-5724.492) (-5731.860) * (-5735.513) (-5729.273) [-5720.300] (-5733.004) -- 0:00:13
          11500 -- [-5722.822] (-5722.036) (-5724.492) (-5731.860) * (-5735.513) (-5729.273) [-5720.300] (-5733.004) -- 0:00:13
          11800 -- (-5733.338) (-5737.474) [-5724.400] (-5727.480) * (-5730.937) (-5728.018) [-5729.014] (-5723.934) -- 0:00:12
          12500 -- [-5725.373] (-5728.665) (-5728.768) (-5718.357) * (-5731.637) [-5729.254] (-5721.641) (-5728.456) -- 0:00:10
          11600 -- [-5727.799] (-5728.655) (-5728.852) (-5732.873) * (-5729.607) [-5725.569] (-5728.140) (-5718.391) -- 0:00:13
          11600 -- [-5727.799] (-5728.655) (-5728.852) (-5732.873) * (-5729.607) [-5725.569] (-5728.140) (-5718.391) -- 0:00:13
          11900 -- (-5726.424) (-5732.089) [-5723.252] (-5735.073) * (-5727.007) [-5722.773] (-5725.119) (-5723.347) -- 0:00:12
          12600 -- (-5725.706) (-5730.670) (-5733.244) [-5720.568] * (-5736.779) (-5728.234) (-5722.505) [-5724.952] -- 0:00:11
          11700 -- (-5735.289) (-5725.228) [-5725.992] (-5729.943) * (-5729.358) (-5730.407) (-5730.201) [-5721.423] -- 0:00:13
          11700 -- (-5735.289) (-5725.228) [-5725.992] (-5729.943) * (-5729.358) (-5730.407) (-5730.201) [-5721.423] -- 0:00:13
          12700 -- (-5725.810) [-5721.797] (-5738.685) (-5723.627) * (-5732.725) (-5727.061) [-5722.201] (-5722.736) -- 0:00:10
          12000 -- (-5723.357) [-5734.877] (-5725.660) (-5720.223) * (-5736.824) (-5725.159) (-5730.894) [-5725.843] -- 0:00:12
    
          Average standard deviation of split frequencies: 0.001727
    
          11800 -- (-5733.338) (-5737.474) [-5724.400] (-5727.480) * (-5730.937) (-5728.018) [-5729.014] (-5723.934) -- 0:00:13
          11800 -- (-5733.338) (-5737.474) [-5724.400] (-5727.480) * (-5730.937) (-5728.018) [-5729.014] (-5723.934) -- 0:00:13
          12800 -- (-5722.119) [-5722.066] (-5736.343) (-5719.922) * (-5730.500) (-5723.570) (-5729.273) [-5724.877] -- 0:00:10
          11900 -- (-5726.424) (-5732.089) [-5723.252] (-5735.073) * (-5727.007) [-5722.773] (-5725.119) (-5723.347) -- 0:00:12
          12100 -- [-5728.497] (-5731.761) (-5729.328) (-5722.507) * (-5728.662) [-5723.481] (-5729.149) (-5728.633) -- 0:00:12
          11900 -- (-5726.424) (-5732.089) [-5723.252] (-5735.073) * (-5727.007) [-5722.773] (-5725.119) (-5723.347) -- 0:00:12
          12900 -- [-5724.033] (-5729.224) (-5732.021) (-5723.431) * (-5733.912) [-5724.809] (-5725.294) (-5725.397) -- 0:00:10
          12000 -- (-5723.357) [-5734.877] (-5725.660) (-5720.223) * (-5736.824) (-5725.159) (-5730.894) [-5725.843] -- 0:00:12
    
          Average standard deviation of split frequencies: 0.001727
    
          12000 -- (-5723.357) [-5734.877] (-5725.660) (-5720.223) * (-5736.824) (-5725.159) (-5730.894) [-5725.843] -- 0:00:12
    
          Average standard deviation of split frequencies: 0.001727
    
          12200 -- [-5737.149] (-5733.500) (-5733.184) (-5724.066) * (-5730.053) [-5726.114] (-5732.434) (-5725.705) -- 0:00:12
          13000 -- (-5722.832) (-5724.882) (-5732.400) [-5725.339] * (-5730.979) (-5723.729) [-5720.125] (-5725.806) -- 0:00:10
    
          Average standard deviation of split frequencies: 0.001587
    
          12100 -- [-5728.497] (-5731.761) (-5729.328) (-5722.507) * (-5728.662) [-5723.481] (-5729.149) (-5728.633) -- 0:00:12
          12100 -- [-5728.497] (-5731.761) (-5729.328) (-5722.507) * (-5728.662) [-5723.481] (-5729.149) (-5728.633) -- 0:00:12
          13100 -- (-5722.109) (-5727.236) (-5737.671) [-5724.296] * [-5721.358] (-5725.297) (-5720.361) (-5726.646) -- 0:00:10
          12300 -- (-5735.175) (-5725.407) [-5728.778] (-5728.061) * (-5731.795) [-5723.837] (-5731.560) (-5731.337) -- 0:00:11
          12200 -- [-5737.149] (-5733.500) (-5733.184) (-5724.066) * (-5730.053) [-5726.114] (-5732.434) (-5725.705) -- 0:00:12
          12200 -- [-5737.149] (-5733.500) (-5733.184) (-5724.066) * (-5730.053) [-5726.114] (-5732.434) (-5725.705) -- 0:00:12
          13200 -- (-5722.762) [-5729.003] (-5731.927) (-5720.043) * [-5721.746] (-5725.028) (-5722.090) (-5725.950) -- 0:00:09
          12400 -- (-5724.230) [-5726.981] (-5727.067) (-5720.132) * (-5737.250) [-5728.183] (-5732.079) (-5731.944) -- 0:00:11
          12300 -- (-5735.175) (-5725.407) [-5728.778] (-5728.061) * (-5731.795) [-5723.837] (-5731.560) (-5731.337) -- 0:00:11
          12300 -- (-5735.175) (-5725.407) [-5728.778] (-5728.061) * (-5731.795) [-5723.837] (-5731.560) (-5731.337) -- 0:00:11
          13300 -- [-5725.578] (-5735.873) (-5729.720) (-5724.898) * (-5720.631) [-5723.993] (-5725.509) (-5726.413) -- 0:00:09
          12500 -- [-5725.373] (-5728.665) (-5728.768) (-5718.357) * (-5731.637) [-5729.254] (-5721.641) (-5728.456) -- 0:00:11
          12400 -- (-5724.230) [-5726.981] (-5727.067) (-5720.132) * (-5737.250) [-5728.183] (-5732.079) (-5731.944) -- 0:00:11
          12400 -- (-5724.230) [-5726.981] (-5727.067) (-5720.132) * (-5737.250) [-5728.183] (-5732.079) (-5731.944) -- 0:00:11
          13400 -- (-5728.974) (-5735.431) (-5730.749) [-5717.877] * (-5716.186) (-5726.568) (-5725.910) [-5727.487] -- 0:00:09
          12500 -- [-5725.373] (-5728.665) (-5728.768) (-5718.357) * (-5731.637) [-5729.254] (-5721.641) (-5728.456) -- 0:00:11
          12600 -- (-5725.706) (-5730.670) (-5733.244) [-5720.568] * (-5736.779) (-5728.234) (-5722.505) [-5724.952] -- 0:00:11
          12500 -- [-5725.373] (-5728.665) (-5728.768) (-5718.357) * (-5731.637) [-5729.254] (-5721.641) (-5728.456) -- 0:00:11
          13500 -- (-5728.575) (-5729.589) (-5732.550) [-5721.760] * [-5719.288] (-5722.982) (-5724.350) (-5726.083) -- 0:00:09
          12600 -- (-5725.706) (-5730.670) (-5733.244) [-5720.568] * (-5736.779) (-5728.234) (-5722.505) [-5724.952] -- 0:00:11
          12700 -- (-5725.810) [-5721.797] (-5738.685) (-5723.627) * (-5732.725) (-5727.061) [-5722.201] (-5722.736) -- 0:00:11
          13600 -- [-5719.318] (-5730.425) (-5724.717) (-5721.880) * (-5718.451) (-5726.928) [-5719.113] (-5729.035) -- 0:00:09
          12600 -- (-5725.706) (-5730.670) (-5733.244) [-5720.568] * (-5736.779) (-5728.234) (-5722.505) [-5724.952] -- 0:00:11
          12700 -- (-5725.810) [-5721.797] (-5738.685) (-5723.627) * (-5732.725) (-5727.061) [-5722.201] (-5722.736) -- 0:00:11
          12800 -- (-5722.119) [-5722.066] (-5736.343) (-5719.922) * (-5730.500) (-5723.570) (-5729.273) [-5724.877] -- 0:00:11
          13700 -- (-5720.551) (-5726.435) (-5722.149) [-5726.408] * [-5720.168] (-5724.301) (-5725.893) (-5730.779) -- 0:00:09
          12700 -- (-5725.810) [-5721.797] (-5738.685) (-5723.627) * (-5732.725) (-5727.061) [-5722.201] (-5722.736) -- 0:00:11
          12800 -- (-5722.119) [-5722.066] (-5736.343) (-5719.922) * (-5730.500) (-5723.570) (-5729.273) [-5724.877] -- 0:00:11
          12900 -- [-5724.033] (-5729.224) (-5732.021) (-5723.431) * (-5733.912) [-5724.809] (-5725.294) (-5725.397) -- 0:00:11
          13800 -- (-5725.391) (-5724.503) [-5724.865] (-5722.276) * (-5720.535) [-5722.761] (-5721.004) (-5733.028) -- 0:00:08
          12900 -- [-5724.033] (-5729.224) (-5732.021) (-5723.431) * (-5733.912) [-5724.809] (-5725.294) (-5725.397) -- 0:00:11
          13000 -- (-5722.832) (-5724.882) (-5732.400) [-5725.339] * (-5730.979) (-5723.729) [-5720.125] (-5725.806) -- 0:00:10
    
          Average standard deviation of split frequencies: 0.001587
    
          12800 -- (-5722.119) [-5722.066] (-5736.343) (-5719.922) * (-5730.500) (-5723.570) (-5729.273) [-5724.877] -- 0:00:11
          13900 -- (-5722.931) [-5724.084] (-5730.974) (-5728.404) * (-5720.203) (-5720.881) [-5726.816] (-5735.713) -- 0:00:08
          13000 -- (-5722.832) (-5724.882) (-5732.400) [-5725.339] * (-5730.979) (-5723.729) [-5720.125] (-5725.806) -- 0:00:10
    
          Average standard deviation of split frequencies: 0.001587
    
          13100 -- (-5722.109) (-5727.236) (-5737.671) [-5724.296] * [-5721.358] (-5725.297) (-5720.361) (-5726.646) -- 0:00:10
          12900 -- [-5724.033] (-5729.224) (-5732.021) (-5723.431) * (-5733.912) [-5724.809] (-5725.294) (-5725.397) -- 0:00:11
          14000 -- [-5720.721] (-5726.761) (-5726.037) (-5723.575) * (-5719.610) [-5715.878] (-5727.886) (-5732.081) -- 0:00:08
    
          Average standard deviation of split frequencies: 0.001482
    
          13100 -- (-5722.109) (-5727.236) (-5737.671) [-5724.296] * [-5721.358] (-5725.297) (-5720.361) (-5726.646) -- 0:00:10
          13200 -- (-5722.762) [-5729.003] (-5731.927) (-5720.043) * [-5721.746] (-5725.028) (-5722.090) (-5725.950) -- 0:00:10
          14100 -- (-5719.638) (-5728.243) [-5727.058] (-5727.516) * (-5720.963) [-5721.041] (-5720.374) (-5727.838) -- 0:00:08
          13000 -- (-5722.832) (-5724.882) (-5732.400) [-5725.339] * (-5730.979) (-5723.729) [-5720.125] (-5725.806) -- 0:00:10
    
          Average standard deviation of split frequencies: 0.001587
    
          13200 -- (-5722.762) [-5729.003] (-5731.927) (-5720.043) * [-5721.746] (-5725.028) (-5722.090) (-5725.950) -- 0:00:10
          13300 -- [-5725.578] (-5735.873) (-5729.720) (-5724.898) * (-5720.631) [-5723.993] (-5725.509) (-5726.413) -- 0:00:10
          14200 -- (-5721.115) (-5727.046) [-5725.035] (-5735.487) * [-5720.365] (-5718.496) (-5728.077) (-5725.377) -- 0:00:08
          13100 -- (-5722.109) (-5727.236) (-5737.671) [-5724.296] * [-5721.358] (-5725.297) (-5720.361) (-5726.646) -- 0:00:10
          13300 -- [-5725.578] (-5735.873) (-5729.720) (-5724.898) * (-5720.631) [-5723.993] (-5725.509) (-5726.413) -- 0:00:10
          13400 -- (-5728.974) (-5735.431) (-5730.749) [-5717.877] * (-5716.186) (-5726.568) (-5725.910) [-5727.487] -- 0:00:09
          14300 -- (-5720.809) (-5729.179) [-5726.137] (-5731.374) * (-5720.383) [-5728.538] (-5731.899) (-5726.856) -- 0:00:07
          13400 -- (-5728.974) (-5735.431) (-5730.749) [-5717.877] * (-5716.186) (-5726.568) (-5725.910) [-5727.487] -- 0:00:09
          13200 -- (-5722.762) [-5729.003] (-5731.927) (-5720.043) * [-5721.746] (-5725.028) (-5722.090) (-5725.950) -- 0:00:10
          13500 -- (-5728.575) (-5729.589) (-5732.550) [-5721.760] * [-5719.288] (-5722.982) (-5724.350) (-5726.083) -- 0:00:10
          13300 -- [-5725.578] (-5735.873) (-5729.720) (-5724.898) * (-5720.631) [-5723.993] (-5725.509) (-5726.413) -- 0:00:10
          14400 -- (-5722.431) [-5726.482] (-5727.648) (-5729.059) * [-5718.341] (-5727.093) (-5723.303) (-5733.069) -- 0:00:08
          13500 -- (-5728.575) (-5729.589) (-5732.550) [-5721.760] * [-5719.288] (-5722.982) (-5724.350) (-5726.083) -- 0:00:10
          13600 -- [-5719.318] (-5730.425) (-5724.717) (-5721.880) * (-5718.451) (-5726.928) [-5719.113] (-5729.035) -- 0:00:09
          13400 -- (-5728.974) (-5735.431) (-5730.749) [-5717.877] * (-5716.186) (-5726.568) (-5725.910) [-5727.487] -- 0:00:10
          13700 -- (-5720.551) (-5726.435) (-5722.149) [-5726.408] * [-5720.168] (-5724.301) (-5725.893) (-5730.779) -- 0:00:09
          14500 -- (-5725.552) (-5720.875) [-5729.975] (-5735.555) * (-5723.577) [-5731.073] (-5724.089) (-5733.918) -- 0:00:07
          13600 -- [-5719.318] (-5730.425) (-5724.717) (-5721.880) * (-5718.451) (-5726.928) [-5719.113] (-5729.035) -- 0:00:09
          13500 -- (-5728.575) (-5729.589) (-5732.550) [-5721.760] * [-5719.288] (-5722.982) (-5724.350) (-5726.083) -- 0:00:10
          13800 -- (-5725.391) (-5724.503) [-5724.865] (-5722.276) * (-5720.535) [-5722.761] (-5721.004) (-5733.028) -- 0:00:09
          14600 -- (-5726.552) (-5719.243) [-5725.630] (-5734.834) * [-5725.254] (-5732.943) (-5722.413) (-5728.009) -- 0:00:07
          13600 -- [-5719.318] (-5730.425) (-5724.717) (-5721.880) * (-5718.451) (-5726.928) [-5719.113] (-5729.035) -- 0:00:09
          13700 -- (-5720.551) (-5726.435) (-5722.149) [-5726.408] * [-5720.168] (-5724.301) (-5725.893) (-5730.779) -- 0:00:09
          13900 -- (-5722.931) [-5724.084] (-5730.974) (-5728.404) * (-5720.203) (-5720.881) [-5726.816] (-5735.713) -- 0:00:09
          13700 -- (-5720.551) (-5726.435) (-5722.149) [-5726.408] * [-5720.168] (-5724.301) (-5725.893) (-5730.779) -- 0:00:09
          13800 -- (-5725.391) (-5724.503) [-5724.865] (-5722.276) * (-5720.535) [-5722.761] (-5721.004) (-5733.028) -- 0:00:09
          14700 -- (-5733.157) (-5726.213) [-5732.351] (-5724.671) * (-5728.528) [-5726.616] (-5721.205) (-5727.863) -- 0:00:07
          14000 -- [-5720.721] (-5726.761) (-5726.037) (-5723.575) * (-5719.610) [-5715.878] (-5727.886) (-5732.081) -- 0:00:09
    
          Average standard deviation of split frequencies: 0.001482
    
          13800 -- (-5725.391) (-5724.503) [-5724.865] (-5722.276) * (-5720.535) [-5722.761] (-5721.004) (-5733.028) -- 0:00:09
          13900 -- (-5722.931) [-5724.084] (-5730.974) (-5728.404) * (-5720.203) (-5720.881) [-5726.816] (-5735.713) -- 0:00:09
          14800 -- [-5732.059] (-5722.995) (-5728.204) (-5720.961) * (-5727.202) (-5732.294) [-5720.080] (-5727.765) -- 0:00:07
          14100 -- (-5719.638) (-5728.243) [-5727.058] (-5727.516) * (-5720.963) [-5721.041] (-5720.374) (-5727.838) -- 0:00:08
          14900 -- (-5737.260) (-5725.036) [-5722.656] (-5719.735) * (-5721.679) [-5731.134] (-5725.309) (-5724.948) -- 0:00:07
          14000 -- [-5720.721] (-5726.761) (-5726.037) (-5723.575) * (-5719.610) [-5715.878] (-5727.886) (-5732.081) -- 0:00:09
    
          Average standard deviation of split frequencies: 0.001482
    
          13900 -- (-5722.931) [-5724.084] (-5730.974) (-5728.404) * (-5720.203) (-5720.881) [-5726.816] (-5735.713) -- 0:00:09
          14200 -- (-5721.115) (-5727.046) [-5725.035] (-5735.487) * [-5720.365] (-5718.496) (-5728.077) (-5725.377) -- 0:00:08
          15000 -- (-5728.537) (-5722.854) [-5722.771] (-5720.461) * (-5728.147) (-5734.908) [-5726.780] (-5729.643) -- 0:00:07
    
          Average standard deviation of split frequencies: 0.001378
    
          14100 -- (-5719.638) (-5728.243) [-5727.058] (-5727.516) * (-5720.963) [-5721.041] (-5720.374) (-5727.838) -- 0:00:09
          14000 -- [-5720.721] (-5726.761) (-5726.037) (-5723.575) * (-5719.610) [-5715.878] (-5727.886) (-5732.081) -- 0:00:09
    
          Average standard deviation of split frequencies: 0.001482
    
          14300 -- (-5720.809) (-5729.179) [-5726.137] (-5731.374) * (-5720.383) [-5728.538] (-5731.899) (-5726.856) -- 0:00:08
          15100 -- (-5732.873) (-5722.903) [-5717.691] (-5726.712) * [-5727.634] (-5744.966) (-5727.394) (-5733.162) -- 0:00:07
          15200 -- (-5730.942) (-5730.923) [-5718.755] (-5726.290)       14200 -- (-5721.115) (-5727.046) [-5725.035] (-5735.487) * [-5720.365] (-5718.496) (-5728.077) (-5725.377) * (-5721.486) [-5736.946] (-5724.459) -- 0:00:08(-5723.360) -- 0:00:06
    
          14100 -- (-5719.638) (-5728.243) [-5727.058] (-5727.516) * (-5720.963) [-5721.041] (-5720.374) (-5727.838) -- 0:00:09
          14400 -- (-5722.431) [-5726.482] (-5727.648) (-5729.059) * [-5718.341] (-5727.093) (-5723.303) (-5733.069) -- 0:00:08
          15300 -- (-5722.750) [-5721.650] (-5719.004) (-5721.561) * (-5723.283) (-5724.464) (-5724.672) [-5718.739] -- 0:00:06
          14500 -- (-5725.552) (-5720.875) [-5729.975] (-5735.555) * (-5723.577) [-5731.073] (-5724.089) (-5733.918) -- 0:00:08
          14300 -- (-5720.809) (-5729.179) [-5726.137] (-5731.374) * (-5720.383) [-5728.538] (-5731.899) (-5726.856) -- 0:00:08
          14200 -- (-5721.115) (-5727.046) [-5725.035] (-5735.487) * [-5720.365] (-5718.496) (-5728.077) (-5725.377) -- 0:00:08
          15400 -- (-5725.422) [-5725.919] (-5721.988) (-5718.124) * (-5725.594) [-5723.639] (-5725.505) (-5716.909) -- 0:00:06
          14400 -- (-5722.431) [-5726.482] (-5727.648) (-5729.059) * [-5718.341] (-5727.093) (-5723.303) (-5733.069) -- 0:00:08
          14300 -- (-5720.809) (-5729.179) [-5726.137] (-5731.374) * (-5720.383) [-5728.538] (-5731.899) (-5726.856) -- 0:00:08
          14600 -- (-5726.552) (-5719.243) [-5725.630] (-5734.834) * [-5725.254] (-5732.943) (-5722.413) (-5728.009) -- 0:00:08
          15500 -- (-5730.057) (-5723.065) [-5722.636] (-5722.618) * (-5732.190) [-5726.277] (-5730.910) (-5717.508) -- 0:00:06
          14500 -- (-5725.552) (-5720.875) [-5729.975] (-5735.555) * (-5723.577) [-5731.073] (-5724.089) (-5733.918) -- 0:00:08
          14400 -- (-5722.431) [-5726.482] (-5727.648) (-5729.059) * [-5718.341] (-5727.093) (-5723.303) (-5733.069) -- 0:00:08
          14700 -- (-5733.157) (-5726.213) [-5732.351] (-5724.671) * (-5728.528) [-5726.616] (-5721.205) (-5727.863) -- 0:00:07
          15600 -- (-5726.176) [-5722.339] (-5723.325) (-5721.710) * (-5730.906) (-5720.941) (-5736.631) [-5721.507] -- 0:00:06
          14600 -- (-5726.552) (-5719.243) [-5725.630] (-5734.834) * [-5725.254] (-5732.943) (-5722.413) (-5728.009) -- 0:00:08
          14500 -- (-5725.552) (-5720.875) [-5729.975] (-5735.555) * (-5723.577) [-5731.073] (-5724.089) (-5733.918) -- 0:00:08
          14800 -- [-5732.059] (-5722.995) (-5728.204) (-5720.961) * (-5727.202) (-5732.294) [-5720.080] (-5727.765) -- 0:00:07
          15700 -- (-5730.564) (-5721.305) (-5725.520) [-5721.517] * (-5723.832) (-5718.786) (-5720.056) [-5719.640] -- 0:00:06
          14700 -- (-5733.157) (-5726.213) [-5732.351] (-5724.671) * (-5728.528) [-5726.616] (-5721.205) (-5727.863) -- 0:00:07
          14600 -- (-5726.552) (-5719.243) [-5725.630] (-5734.834) * [-5725.254] (-5732.943) (-5722.413) (-5728.009) -- 0:00:08
          14900 -- (-5737.260) (-5725.036) [-5722.656] (-5719.735) * (-5721.679) [-5731.134] (-5725.309) (-5724.948) -- 0:00:07
          15800 -- (-5730.685) [-5724.610] (-5728.845) (-5722.775) * (-5722.281) (-5721.197) (-5719.949) [-5724.413] -- 0:00:05
          14800 -- [-5732.059] (-5722.995) (-5728.204) (-5720.961) * (-5727.202) (-5732.294) [-5720.080] (-5727.765) -- 0:00:07
          14700 -- (-5733.157) (-5726.213) [-5732.351] (-5724.671) * (-5728.528) [-5726.616] (-5721.205) (-5727.863) -- 0:00:07
          15000 -- (-5728.537) (-5722.854) [-5722.771] (-5720.461) * (-5728.147) (-5734.908) [-5726.780] (-5729.643) -- 0:00:07
    
          Average standard deviation of split frequencies: 0.001378
    
          15900 -- (-5730.233) [-5720.874] (-5721.360) (-5716.936) * (-5718.728) [-5726.128] (-5721.867) (-5728.211) -- 0:00:05
          14900 -- (-5737.260) (-5725.036) [-5722.656] (-5719.735) * (-5721.679) [-5731.134] (-5725.309) (-5724.948) -- 0:00:07
          14800 -- [-5732.059] (-5722.995) (-5728.204) (-5720.961) * (-5727.202) (-5732.294) [-5720.080] (-5727.765) -- 0:00:08
          15100 -- (-5732.873) (-5722.903) [-5717.691] (-5726.712) * [-5727.634] (-5744.966) (-5727.394) (-5733.162) -- 0:00:07
          16000 -- (-5724.701) (-5728.120) (-5725.555) [-5716.844] * (-5722.829) (-5726.733) (-5721.227) [-5729.168] -- 0:00:05
    
          Average standard deviation of split frequencies: 0.001299
    
          15000 -- (-5728.537) (-5722.854) [-5722.771] (-5720.461) * (-5728.147) (-5734.908) [-5726.780] (-5729.643) -- 0:00:07
    
          Average standard deviation of split frequencies: 0.001378
    
          14900 -- (-5737.260) (-5725.036) [-5722.656] (-5719.735) * (-5721.679) [-5731.134] (-5725.309) (-5724.948) -- 0:00:07
          16100 -- (-5729.968) (-5730.688) (-5728.395) [-5715.400] * (-5722.684) [-5722.172] (-5717.511) (-5726.538) -- 0:00:05
          15200 -- (-5730.942) (-5730.923) [-5718.755] (-5726.290) * (-5721.486) [-5736.946] (-5724.459) (-5723.360) -- 0:00:07
          15100 -- (-5732.873) (-5722.903) [-5717.691] (-5726.712) * [-5727.634] (-5744.966) (-5727.394) (-5733.162) -- 0:00:07
          15000 -- (-5728.537) (-5722.854) [-5722.771] (-5720.461) * (-5728.147) (-5734.908) [-5726.780] (-5729.643) -- 0:00:07
    
          Average standard deviation of split frequencies: 0.001378
    
          16200 -- (-5734.327) (-5730.839) [-5725.423] (-5719.036) * (-5727.968) [-5718.557] (-5720.286) (-5729.888) -- 0:00:05
          15300 -- (-5722.750) [-5721.650] (-5719.004) (-5721.561) * (-5723.283) (-5724.464) (-5724.672) [-5718.739] -- 0:00:07
          15200 -- (-5730.942) (-5730.923) [-5718.755] (-5726.290) * (-5721.486) [-5736.946] (-5724.459) (-5723.360) -- 0:00:07
          16300 -- (-5732.643) (-5731.464) (-5728.754) [-5718.806] * (-5728.767) [-5717.598] (-5718.221) (-5731.754) -- 0:00:05
          15100 -- (-5732.873) (-5722.903) [-5717.691] (-5726.712) * [-5727.634] (-5744.966) (-5727.394) (-5733.162) -- 0:00:07
          15300 -- (-5722.750) [-5721.650] (-5719.004) (-5721.561) * (-5723.283) (-5724.464) (-5724.672) [-5718.739] -- 0:00:07
          15400 -- (-5725.422) [-5725.919] (-5721.988) (-5718.124) * (-5725.594) [-5723.639] (-5725.505) (-5716.909) -- 0:00:06
          16400 -- (-5740.149) [-5728.116] (-5724.440) (-5726.050) * (-5726.314) (-5718.695) [-5723.699] (-5727.052) -- 0:00:05
          15200 -- (-5730.942) (-5730.923) [-5718.755] (-5726.290) * (-5721.486) [-5736.946] (-5724.459) (-5723.360) -- 0:00:07
          15400 -- (-5725.422) [-5725.919] (-5721.988) (-5718.124) * (-5725.594) [-5723.639] (-5725.505) (-5716.909) -- 0:00:06
          15500 -- (-5730.057) (-5723.065) [-5722.636] (-5722.618) * (-5732.190) [-5726.277] (-5730.910) (-5717.508) -- 0:00:06
          15300 -- (-5722.750) [-5721.650] (-5719.004) (-5721.561) * (-5723.283) (-5724.464) (-5724.672) [-5718.739] -- 0:00:07
          16500 -- (-5731.944) [-5721.722] (-5731.254) (-5720.658) * (-5723.325) [-5720.163] (-5723.014) (-5725.567) -- 0:00:04
          15400 -- (-5725.422) [-5725.919] (-5721.988) (-5718.124) * (-5725.594) [-5723.639] (-5725.505) (-5716.909) -- 0:00:06
          15500 -- (-5730.057) (-5723.065) [-5722.636] (-5722.618) * (-5732.190) [-5726.277] (-5730.910) (-5717.508) -- 0:00:06
          15600 -- (-5726.176) [-5722.339] (-5723.325) (-5721.710) * (-5730.906) (-5720.941) (-5736.631) [-5721.507] -- 0:00:06
          16600 -- (-5726.187) [-5721.264] (-5734.784) (-5721.492) * (-5727.368) (-5729.765) (-5729.332) [-5724.478] -- 0:00:04
          15500 -- (-5730.057) (-5723.065) [-5722.636] (-5722.618) * (-5732.190) [-5726.277] (-5730.910) (-5717.508) -- 0:00:06
          15700 -- (-5730.564) (-5721.305) (-5725.520) [-5721.517] * (-5723.832) (-5718.786) (-5720.056) [-5719.640] -- 0:00:06
          15600 -- (-5726.176) [-5722.339] (-5723.325) (-5721.710) * (-5730.906) (-5720.941) (-5736.631) [-5721.507] -- 0:00:06
          16700 -- (-5729.877) (-5729.976) (-5728.600) [-5718.183] * (-5728.899) (-5722.331) (-5727.319) [-5727.384] -- 0:00:04
          15600 -- (-5726.176) [-5722.339] (-5723.325) (-5721.710) * (-5730.906) (-5720.941) (-5736.631) [-5721.507] -- 0:00:06
          15800 -- (-5730.685) [-5724.610] (-5728.845) (-5722.775) * (-5722.281) (-5721.197) (-5719.949) [-5724.413] -- 0:00:06
          15700 -- (-5730.564) (-5721.305) (-5725.520) [-5721.517] * (-5723.832) (-5718.786) (-5720.056) [-5719.640] -- 0:00:06
          15700 -- (-5730.564) (-5721.305) (-5725.520) [-5721.517] * (-5723.832) (-5718.786) (-5720.056) [-5719.640] -- 0:00:06
          16800 -- (-5727.557) (-5726.533) (-5724.656) [-5724.758] * (-5723.884) (-5728.237) [-5720.225] (-5731.968) -- 0:00:04
          15900 -- (-5730.233) [-5720.874] (-5721.360) (-5716.936) * (-5718.728) [-5726.128] (-5721.867) (-5728.211) -- 0:00:06
          15800 -- (-5730.685) [-5724.610] (-5728.845) (-5722.775) * (-5722.281) (-5721.197) (-5719.949) [-5724.413] -- 0:00:06
          15800 -- (-5730.685) [-5724.610] (-5728.845) (-5722.775) * (-5722.281) (-5721.197) (-5719.949) [-5724.413] -- 0:00:06
          16900 -- (-5726.037) [-5724.908] (-5726.514) (-5725.302) * [-5723.588] (-5731.350) (-5725.020) (-5739.245) -- 0:00:04
          16000 -- (-5724.701) (-5728.120) (-5725.555) [-5716.844] * (-5722.829) (-5726.733) (-5721.227) [-5729.168] -- 0:00:06
    
          Average standard deviation of split frequencies: 0.001299
    
          15900 -- (-5730.233) [-5720.874] (-5721.360) (-5716.936) * (-5718.728) [-5726.128] (-5721.867) (-5728.211) -- 0:00:06
          15900 -- (-5730.233) [-5720.874] (-5721.360) (-5716.936) * (-5718.728) [-5726.128] (-5721.867) (-5728.211) -- 0:00:06
          17000 -- (-5732.962) (-5721.905) [-5728.426] (-5719.372) * (-5720.779) (-5726.952) [-5724.329] (-5730.844) -- 0:00:04
    
          Average standard deviation of split frequencies: 0.001218
    
          16000 -- (-5724.701) (-5728.120) (-5725.555) [-5716.844] * (-5722.829) (-5726.733) (-5721.227) [-5729.168] -- 0:00:06
    
          Average standard deviation of split frequencies: 0.001299
    
          16100 -- (-5729.968) (-5730.688) (-5728.395) [-5715.400] * (-5722.684) [-5722.172] (-5717.511) (-5726.538) -- 0:00:05
          16000 -- (-5724.701) (-5728.120) (-5725.555) [-5716.844] * (-5722.829) (-5726.733) (-5721.227) [-5729.168] -- 0:00:06
    
          Average standard deviation of split frequencies: 0.001299
    
          16100 -- (-5729.968) (-5730.688) (-5728.395) [-5715.400] * (-5722.684) [-5722.172] (-5717.511) (-5726.538) -- 0:00:05
          17100 -- (-5727.676) [-5722.382] (-5726.936) (-5725.046) * (-5730.661) (-5726.107) (-5723.521) [-5725.782] -- 0:00:04
          16200 -- (-5734.327) (-5730.839) [-5725.423] (-5719.036) * (-5727.968) [-5718.557] (-5720.286) (-5729.888) -- 0:00:05
          16200 -- (-5734.327) (-5730.839) [-5725.423] (-5719.036) * (-5727.968) [-5718.557] (-5720.286) (-5729.888) -- 0:00:05
          16100 -- (-5729.968) (-5730.688) (-5728.395) [-5715.400] * (-5722.684) [-5722.172] (-5717.511) (-5726.538) -- 0:00:05
          17200 -- (-5728.116) [-5723.977] (-5727.443) (-5728.729) * [-5726.148] (-5722.286) (-5729.694) (-5727.399) -- 0:00:03
          16300 -- (-5732.643) (-5731.464) (-5728.754) [-5718.806] * (-5728.767) [-5717.598] (-5718.221) (-5731.754) -- 0:00:05
          16300 -- (-5732.643) (-5731.464) (-5728.754) [-5718.806] * (-5728.767) [-5717.598] (-5718.221) (-5731.754) -- 0:00:05
          16200 -- (-5734.327) (-5730.839) [-5725.423] (-5719.036) * (-5727.968) [-5718.557] (-5720.286) (-5729.888) -- 0:00:05
          16400 -- (-5740.149) [-5728.116] (-5724.440) (-5726.050) * (-5726.314) (-5718.695) [-5723.699] (-5727.052) -- 0:00:05
          17300 -- (-5728.789) (-5727.289) (-5733.828) [-5720.318] * [-5723.584] (-5721.294) (-5725.312) (-5730.203) -- 0:00:03
          16400 -- (-5740.149) [-5728.116] (-5724.440) (-5726.050) * (-5726.314) (-5718.695) [-5723.699] (-5727.052) -- 0:00:05
          16500 -- (-5731.944) [-5721.722] (-5731.254) (-5720.658) * (-5723.325) [-5720.163] (-5723.014) (-5725.567) -- 0:00:05
          16300 -- (-5732.643) (-5731.464) (-5728.754) [-5718.806] * (-5728.767) [-5717.598] (-5718.221) (-5731.754) -- 0:00:05
          17400 -- [-5724.332] (-5722.702) (-5731.807) (-5725.978) * (-5731.522) (-5727.438) [-5723.060] (-5729.899) -- 0:00:03
          16500 -- (-5731.944) [-5721.722] (-5731.254) (-5720.658) * (-5723.325) [-5720.163] (-5723.014) (-5725.567) -- 0:00:05
          16400 -- (-5740.149) [-5728.116] (-5724.440) (-5726.050) * (-5726.314) (-5718.695) [-5723.699] (-5727.052) -- 0:00:05
          16600 -- (-5726.187) [-5721.264] (-5734.784) (-5721.492) * (-5727.368) (-5729.765) (-5729.332) [-5724.478] -- 0:00:05
          17500 -- (-5727.862) [-5723.706] (-5728.585) (-5725.109) * (-5724.662) [-5728.111] (-5725.047) (-5729.773) -- 0:00:03
          16600 -- (-5726.187) [-5721.264] (-5734.784) (-5721.492) * (-5727.368) (-5729.765) (-5729.332) [-5724.478] -- 0:00:05
          16500 -- (-5731.944) [-5721.722] (-5731.254) (-5720.658) * (-5723.325) [-5720.163] (-5723.014) (-5725.567) -- 0:00:05
          16700 -- (-5729.877) (-5729.976) (-5728.600) [-5718.183] * (-5728.899) (-5722.331) (-5727.319) [-5727.384] -- 0:00:04
          16600 -- (-5726.187) [-5721.264] (-5734.784) (-5721.492) * (-5727.368) (-5729.765) (-5729.332) [-5724.478] -- 0:00:05
          17600 -- (-5734.397) [-5724.068] (-5735.467) (-5725.463) * (-5736.723) [-5726.122] (-5730.654) (-5725.711) -- 0:00:03
          16700 -- (-5729.877) (-5729.976) (-5728.600) [-5718.183] * (-5728.899) (-5722.331) (-5727.319) [-5727.384] -- 0:00:04
          16800 -- (-5727.557) (-5726.533) (-5724.656) [-5724.758] * (-5723.884) (-5728.237) [-5720.225] (-5731.968) -- 0:00:04
          16700 -- (-5729.877) (-5729.976) (-5728.600) [-5718.183] * (-5728.899) (-5722.331) (-5727.319) [-5727.384] -- 0:00:04
          17700 -- (-5737.800) [-5728.511] (-5731.461) (-5730.346) * (-5728.356) (-5724.674) [-5735.632] (-5726.219) -- 0:00:03
          16900 -- (-5726.037) [-5724.908] (-5726.514) (-5725.302) * [-5723.588] (-5731.350) (-5725.020) (-5739.245) -- 0:00:04
          16800 -- (-5727.557) (-5726.533) (-5724.656) [-5724.758] * (-5723.884) (-5728.237) [-5720.225] (-5731.968) -- 0:00:04
          16800 -- (-5727.557) (-5726.533) (-5724.656) [-5724.758] * (-5723.884) (-5728.237) [-5720.225] (-5731.968) -- 0:00:04
          17000 -- (-5732.962) (-5721.905) [-5728.426] (-5719.372) * (-5720.779) (-5726.952) [-5724.329] (-5730.844) -- 0:00:04
    
          Average standard deviation of split frequencies: 0.001218
    
          17800 -- (-5739.042) (-5731.302) (-5730.410) [-5724.198] * (-5727.102) [-5729.676] (-5731.464) (-5726.987) -- 0:00:03
          16900 -- (-5726.037) [-5724.908] (-5726.514) (-5725.302) * [-5723.588] (-5731.350) (-5725.020) (-5739.245) -- 0:00:04
          16900 -- (-5726.037) [-5724.908] (-5726.514) (-5725.302) * [-5723.588] (-5731.350) (-5725.020) (-5739.245) -- 0:00:04
          17100 -- (-5727.676) [-5722.382] (-5726.936) (-5725.046) * (-5730.661) (-5726.107) (-5723.521) [-5725.782] -- 0:00:04
          17000 -- (-5732.962) (-5721.905) [-5728.426] (-5719.372) * (-5720.779) (-5726.952) [-5724.329] (-5730.844) -- 0:00:04
    
          Average standard deviation of split frequencies: 0.001218
    
          17000 -- (-5732.962) (-5721.905) [-5728.426] (-5719.372) * (-5720.779) (-5726.952) [-5724.329] (-5730.844) -- 0:00:04
    
          Average standard deviation of split frequencies: 0.001218
    
          17900 -- [-5735.500] (-5730.463) (-5729.759) (-5725.094) * (-5724.342) [-5723.118] (-5738.444) (-5721.626) -- 0:00:02
          17200 -- (-5728.116) [-5723.977] (-5727.443) (-5728.729) * [-5726.148] (-5722.286) (-5729.694) (-5727.399) -- 0:00:04
          17100 -- (-5727.676) [-5722.382] (-5726.936) (-5725.046) * (-5730.661) (-5726.107) (-5723.521) [-5725.782] -- 0:00:04
          17100 -- (-5727.676) [-5722.382] (-5726.936) (-5725.046) * (-5730.661) (-5726.107) (-5723.521) [-5725.782] -- 0:00:04
          18000 -- (-5742.337) (-5742.013) (-5729.212) [-5724.559] * (-5727.803) (-5721.049) (-5735.020) [-5719.054] -- 0:00:02
    
          Average standard deviation of split frequencies: 0.001155
    
          17300 -- (-5728.789) (-5727.289) (-5733.828) [-5720.318] * [-5723.584] (-5721.294) (-5725.312) (-5730.203) -- 0:00:03
          17200 -- (-5728.116) [-5723.977] (-5727.443) (-5728.729) * [-5726.148] (-5722.286) (-5729.694) (-5727.399) -- 0:00:04
          17200 -- (-5728.116) [-5723.977] (-5727.443) (-5728.729) * [-5726.148] (-5722.286) (-5729.694) (-5727.399) -- 0:00:04
          17400 -- [-5724.332] (-5722.702) (-5731.807) (-5725.978) * (-5731.522) (-5727.438) [-5723.060] (-5729.899) -- 0:00:03
          18100 -- (-5731.297) (-5738.964) (-5724.940) [-5723.504] * (-5729.888) (-5720.235) [-5726.476] (-5723.079) -- 0:00:02
          17300 -- (-5728.789) (-5727.289) (-5733.828) [-5720.318] * [-5723.584] (-5721.294) (-5725.312) (-5730.203) -- 0:00:04
          17500 -- (-5727.862) [-5723.706] (-5728.585) (-5725.109) * (-5724.662) [-5728.111] (-5725.047) (-5729.773) -- 0:00:03
          17300 -- (-5728.789) (-5727.289) (-5733.828) [-5720.318] * [-5723.584] (-5721.294) (-5725.312) (-5730.203) -- 0:00:04
          18200 -- (-5727.183) (-5735.275) (-5725.253) [-5722.824] * (-5731.776) (-5721.081) (-5728.769) [-5722.803] -- 0:00:02
          17600 -- (-5734.397) [-5724.068] (-5735.467) (-5725.463) * (-5736.723) [-5726.122] (-5730.654) (-5725.711) -- 0:00:03
          17400 -- [-5724.332] (-5722.702) (-5731.807) (-5725.978) * (-5731.522) (-5727.438) [-5723.060] (-5729.899) -- 0:00:03
          17400 -- [-5724.332] (-5722.702) (-5731.807) (-5725.978) * (-5731.522) (-5727.438) [-5723.060] (-5729.899) -- 0:00:03
          18300 -- [-5721.667] (-5741.136) (-5725.062) (-5721.019) * (-5729.471) (-5727.424) [-5731.155] (-5724.154) -- 0:00:02
          17700 -- (-5737.800) [-5728.511] (-5731.461) (-5730.346) * (-5728.356) (-5724.674) [-5735.632] (-5726.219) -- 0:00:03
          17500 -- (-5727.862) [-5723.706] (-5728.585) (-5725.109) * (-5724.662) [-5728.111] (-5725.047) (-5729.773) -- 0:00:03
          17500 -- (-5727.862) [-5723.706] (-5728.585) (-5725.109) * (-5724.662) [-5728.111] (-5725.047) (-5729.773) -- 0:00:03
          18400 -- (-5723.957) (-5733.610) (-5722.752) [-5722.436] * (-5736.680) (-5727.644) (-5732.302) [-5736.457] -- 0:00:02
          17800 -- (-5739.042) (-5731.302) (-5730.410) [-5724.198] * (-5727.102) [-5729.676] (-5731.464) (-5726.987) -- 0:00:03
          17600 -- (-5734.397) [-5724.068] (-5735.467) (-5725.463) * (-5736.723) [-5726.122] (-5730.654) (-5725.711) -- 0:00:03
          17600 -- (-5734.397) [-5724.068] (-5735.467) (-5725.463) * (-5736.723) [-5726.122] (-5730.654) (-5725.711) -- 0:00:03
          18500 -- (-5722.817) [-5727.167] (-5728.187) (-5729.686) * (-5736.840) [-5723.462] (-5739.067) (-5726.745) -- 0:00:02
          17700 -- (-5737.800) [-5728.511] (-5731.461) (-5730.346) * (-5728.356) (-5724.674) [-5735.632] (-5726.219) -- 0:00:03
          17900 -- [-5735.500] (-5730.463) (-5729.759) (-5725.094) * (-5724.342) [-5723.118] (-5738.444) (-5721.626) -- 0:00:03
          17700 -- (-5737.800) [-5728.511] (-5731.461) (-5730.346) * (-5728.356) (-5724.674) [-5735.632] (-5726.219) -- 0:00:03
          18600 -- [-5720.014] (-5731.885) (-5725.664) (-5733.503) * (-5730.787) (-5721.155) (-5737.632) [-5721.669] -- 0:00:01
          17800 -- (-5739.042) (-5731.302) (-5730.410) [-5724.198] * (-5727.102) [-5729.676] (-5731.464) (-5726.987) -- 0:00:03
          17800 -- (-5739.042) (-5731.302) (-5730.410) [-5724.198] * (-5727.102) [-5729.676] (-5731.464) (-5726.987) -- 0:00:03
          18000 -- (-5742.337) (-5742.013) (-5729.212) [-5724.559] * (-5727.803) (-5721.049) (-5735.020) [-5719.054] -- 0:00:02
    
          Average standard deviation of split frequencies: 0.001155
    
          18700 -- [-5728.444] (-5734.843) (-5722.440) (-5736.249) * (-5735.879) [-5716.177] (-5731.012) (-5721.993) -- 0:00:01
          17900 -- [-5735.500] (-5730.463) (-5729.759) (-5725.094) * (-5724.342) [-5723.118] (-5738.444) (-5721.626) -- 0:00:03
          17900 -- [-5735.500] (-5730.463) (-5729.759) (-5725.094) * (-5724.342) [-5723.118] (-5738.444) (-5721.626) -- 0:00:03
          18100 -- (-5731.297) (-5738.964) (-5724.940) [-5723.504] * (-5729.888) (-5720.235) [-5726.476] (-5723.079) -- 0:00:02
          18800 -- [-5725.183] (-5745.390) (-5721.720) (-5732.793) * (-5736.300) (-5725.704) (-5729.583) [-5719.448] -- 0:00:01
          18000 -- (-5742.337) (-5742.013) (-5729.212) [-5724.559] * (-5727.803) (-5721.049) (-5735.020) [-5719.054] -- 0:00:02
    
          Average standard deviation of split frequencies: 0.001155
    
          18000 -- (-5742.337) (-5742.013) (-5729.212) [-5724.559] * (-5727.803) (-5721.049) (-5735.020) [-5719.054] -- 0:00:02
    
          Average standard deviation of split frequencies: 0.001155
    
          18200 -- (-5727.183) (-5735.275) (-5725.253) [-5722.824] * (-5731.776) (-5721.081) (-5728.769) [-5722.803] -- 0:00:02
          18900 -- (-5727.591) (-5742.519) [-5722.949] (-5733.986) * (-5738.555) (-5719.196) [-5727.433] (-5721.550) -- 0:00:01
          18100 -- (-5731.297) (-5738.964) (-5724.940) [-5723.504] * (-5729.888) (-5720.235) [-5726.476] (-5723.079) -- 0:00:02
          18100 -- (-5731.297) (-5738.964) (-5724.940) [-5723.504] * (-5729.888) (-5720.235) [-5726.476] (-5723.079) -- 0:00:02
          18300 -- [-5721.667] (-5741.136) (-5725.062) (-5721.019) * (-5729.471) (-5727.424) [-5731.155] (-5724.154) -- 0:00:02
          19000 -- [-5722.022] (-5728.043) (-5724.555) (-5730.599) * (-5731.933) [-5716.153] (-5735.581) (-5724.384) -- 0:00:01
    
          Average standard deviation of split frequencies: 0.001091
    
          18200 -- (-5727.183) (-5735.275) (-5725.253) [-5722.824] * (-5731.776) (-5721.081) (-5728.769) [-5722.803] -- 0:00:02
          18200 -- (-5727.183) (-5735.275) (-5725.253) [-5722.824] * (-5731.776) (-5721.081) (-5728.769) [-5722.803] -- 0:00:02
          18400 -- (-5723.957) (-5733.610) (-5722.752) [-5722.436] * (-5736.680) (-5727.644) (-5732.302) [-5736.457] -- 0:00:02
          19100 -- [-5727.475] (-5732.105) (-5724.896) (-5726.508) * (-5730.487) (-5719.253) [-5733.808] (-5732.199) -- 0:00:01
          18300 -- [-5721.667] (-5741.136) (-5725.062) (-5721.019) * (-5729.471) (-5727.424) [-5731.155] (-5724.154) -- 0:00:02
          18500 -- (-5722.817) [-5727.167] (-5728.187) (-5729.686) * (-5736.840) [-5723.462] (-5739.067) (-5726.745) -- 0:00:02
          18300 -- [-5721.667] (-5741.136) (-5725.062) (-5721.019) * (-5729.471) (-5727.424) [-5731.155] (-5724.154) -- 0:00:02
          19200 -- [-5722.505] (-5733.322) (-5724.313) (-5728.193) * [-5726.219] (-5723.355) (-5737.119) (-5727.731) -- 0:00:01
          18400 -- (-5723.957) (-5733.610) (-5722.752) [-5722.436] * (-5736.680) (-5727.644) (-5732.302) [-5736.457] -- 0:00:02
          18600 -- [-5720.014] (-5731.885) (-5725.664) (-5733.503) * (-5730.787) (-5721.155) (-5737.632) [-5721.669] -- 0:00:02
          18400 -- (-5723.957) (-5733.610) (-5722.752) [-5722.436] * (-5736.680) (-5727.644) (-5732.302) [-5736.457] -- 0:00:02
          19300 -- (-5721.874) [-5724.792] (-5724.485) (-5728.373) * [-5726.595] (-5727.388) (-5740.025) (-5723.424) -- 0:00:00
          18500 -- (-5722.817) [-5727.167] (-5728.187) (-5729.686) * (-5736.840) [-5723.462] (-5739.067) (-5726.745) -- 0:00:02
          18700 -- [-5728.444] (-5734.843) (-5722.440) (-5736.249) * (-5735.879) [-5716.177] (-5731.012) (-5721.993) -- 0:00:01
          18500 -- (-5722.817) [-5727.167] (-5728.187) (-5729.686) * (-5736.840) [-5723.462] (-5739.067) (-5726.745) -- 0:00:02
          19400 -- (-5726.046) [-5724.227] (-5730.617) (-5729.921) * (-5730.258) [-5726.591] (-5736.859) (-5726.019) -- 0:00:00
          18600 -- [-5720.014] (-5731.885) (-5725.664) (-5733.503) * (-5730.787) (-5721.155) (-5737.632) [-5721.669] -- 0:00:02
          18800 -- [-5725.183] (-5745.390) (-5721.720) (-5732.793) * (-5736.300) (-5725.704) (-5729.583) [-5719.448] -- 0:00:01
          18700 -- [-5728.444] (-5734.843) (-5722.440) (-5736.249) * (-5735.879) [-5716.177] (-5731.012) (-5721.993) -- 0:00:01
          18600 -- [-5720.014] (-5731.885) (-5725.664) (-5733.503) * (-5730.787) (-5721.155) (-5737.632) [-5721.669] -- 0:00:02
          19500 -- [-5723.966] (-5721.868) (-5728.441) (-5733.949) * (-5728.097) [-5723.998] (-5735.081) (-5726.068) -- 0:00:00
          18900 -- (-5727.591) (-5742.519) [-5722.949] (-5733.986) * (-5738.555) (-5719.196) [-5727.433] (-5721.550) -- 0:00:01
          18700 -- [-5728.444] (-5734.843) (-5722.440) (-5736.249) * (-5735.879) [-5716.177] (-5731.012) (-5721.993) -- 0:00:01
          19600 -- (-5725.838) [-5724.349] (-5723.589) (-5731.765) * (-5730.122) (-5722.817) (-5732.089) [-5723.389] -- 0:00:00
          18800 -- [-5725.183] (-5745.390) (-5721.720) (-5732.793) * (-5736.300) (-5725.704) (-5729.583) [-5719.448] -- 0:00:01
          19000 -- [-5722.022] (-5728.043) (-5724.555) (-5730.599) * (-5731.933) [-5716.153] (-5735.581) (-5724.384) -- 0:00:01
    
          Average standard deviation of split frequencies: 0.001091
    
          18800 -- [-5725.183] (-5745.390) (-5721.720) (-5732.793) * (-5736.300) (-5725.704) (-5729.583) [-5719.448] -- 0:00:01
          19700 -- (-5727.058) [-5724.178] (-5726.005) (-5731.873) * (-5728.781) (-5719.736) [-5725.800] (-5726.582) -- 0:00:00
          18900 -- (-5727.591) (-5742.519) [-5722.949] (-5733.986) * (-5738.555) (-5719.196) [-5727.433] (-5721.550) -- 0:00:01
          19100 -- [-5727.475] (-5732.105) (-5724.896) (-5726.508) * (-5730.487) (-5719.253) [-5733.808] (-5732.199) -- 0:00:01
          18900 -- (-5727.591) (-5742.519) [-5722.949] (-5733.986) * (-5738.555) (-5719.196) [-5727.433] (-5721.550) -- 0:00:01
          19800 -- (-5725.546) (-5723.846) [-5727.279] (-5739.523) * (-5730.304) [-5723.443] (-5725.947) (-5725.391) -- 0:00:00
          19000 -- [-5722.022] (-5728.043) (-5724.555) (-5730.599) * (-5731.933) [-5716.153] (-5735.581) (-5724.384) -- 0:00:01
    
          Average standard deviation of split frequencies: 0.001091
    
          19200 -- [-5722.505] (-5733.322) (-5724.313) (-5728.193) * [-5726.219] (-5723.355) (-5737.119) (-5727.731) -- 0:00:01
          19300 -- (-5721.874) [-5724.792] (-5724.485) (-5728.373) * [-5726.595] (-5727.388) (-5740.025) (-5723.424) -- 0:00:01
          19100 -- [-5727.475] (-5732.105) (-5724.896) (-5726.508) * (-5730.487) (-5719.253) [-5733.808] (-5732.199) -- 0:00:01
          19000 -- [-5722.022] (-5728.043) (-5724.555) (-5730.599) * (-5731.933) [-5716.153] (-5735.581) (-5724.384) -- 0:00:01
    
          Average standard deviation of split frequencies: 0.001091
    
          19900 -- (-5723.804) (-5723.788) [-5721.689] (-5731.084) * (-5726.862) (-5723.756) [-5729.207] (-5728.809) -- 0:00:00
          19400 -- (-5726.046) [-5724.227] (-5730.617) (-5729.921) * (-5730.258) [-5726.591] (-5736.859) (-5726.019) -- 0:00:00
          19200 -- [-5722.505] (-5733.322) (-5724.313) (-5728.193) * [-5726.219] (-5723.355) (-5737.119) (-5727.731) -- 0:00:01
          19100 -- [-5727.475] (-5732.105) (-5724.896) (-5726.508) * (-5730.487) (-5719.253) [-5733.808] (-5732.199) -- 0:00:01
          20000 -- (-5720.752) (-5721.881) (-5721.223) [-5735.204] * (-5726.628) [-5719.923] (-5724.544) (-5728.339) -- 0:00:00
    
          Average standard deviation of split frequencies: 0.001041
    
          Analysis completed in 28 seconds
          Analysis used 27.74 seconds of CPU time
          Likelihood of best state for "cold" chain of run 1 was -5714.62
          Likelihood of best state for "cold" chain of run 2 was -5714.34
    
          Acceptance rates for the moves in the "cold" chain of run 1:
             With prob.   (last 100)   chain accepted proposals by move
                31.5 %     ( 34 %)     Dirichlet(Revmat)
                59.4 %     ( 57 %)     Slider(Revmat)
                16.5 %     ( 17 %)     Dirichlet(Pi)
                25.8 %     ( 34 %)     Slider(Pi)
                34.2 %     ( 39 %)     Multiplier(Alpha)
                66.9 %     ( 65 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.2 %     (  0 %)     ExtTBR(Tau,V)
                 0.2 %     (  1 %)     NNI(Tau,V)
                 0.5 %     (  1 %)     ParsSPR(Tau,V)
                36.9 %     ( 27 %)     Multiplier(V)
                24.1 %     ( 27 %)     Nodeslider(V)
                15.6 %     ( 14 %)     TLMultiplier(V)
    
          Acceptance rates for the moves in the "cold" chain of run 2:
             With prob.   (last 100)   chain accepted proposals by move
                25.1 %     ( 26 %)     Dirichlet(Revmat)
                62.8 %     ( 62 %)     Slider(Revmat)
                14.3 %     ( 15 %)     Dirichlet(Pi)
                20.4 %     ( 20 %)     Slider(Pi)
                37.3 %     ( 35 %)     Multiplier(Alpha)
                69.1 %     ( 66 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.3 %     (  1 %)     ExtTBR(Tau,V)
                 0.4 %     (  0 %)     NNI(Tau,V)
                 0.8 %     (  0 %)     ParsSPR(Tau,V)
                35.7 %     ( 29 %)     Multiplier(V)
                24.8 %     ( 23 %)     Nodeslider(V)
                15.0 %     ( 18 %)     TLMultiplier(V)
    
          Chain swap information for run 1:
    
                     1     2     3     4 
               --------------------------
             1 |        0.63  0.38  0.26 
             2 |  3299        0.60  0.42 
             3 |  3343  3296        0.70 
             4 |  3350  3282  3430       
    
          Chain swap information for run 2:
    
                     1     2     3     4 
               --------------------------
             1 |        0.63  0.42  0.29 
             2 |  3386        0.69  0.47 
             3 |  3323  3335        0.74 
             4 |  3231  3374  3351       
    
          Upper diagonal: Proportion of successful state exchanges between chains
          Lower diagonal: Number of attempted state exchanges between chains
    
          Chain information:
    
            ID -- Heat 
           -----------
             1 -- 1.00  (cold chain)
             2 -- 0.91 
             3 -- 0.83 
             4 -- 0.77 
    
          Heat = 1 / (1 + T * (ID - 1))
             (where T = 0.10 is the temperature and ID is the chain number)
    
          Summarizing parameters in files primates.nex.run1.p and primates.nex.run2.p
          Writing summary statistics to file primates.nex.pstat
          Using relative burnin ('relburnin=yes'), discarding the first 25 % of samples
          19500 -- [-5723.966] (-5721.868) (-5728.441) (-5733.949) * (-5728.097) [-5723.998] (-5735.081) (-5726.068) -- 0:00:00
    
          Below are rough plots of the generation (x-axis) versus the log   
          probability of observing the data (y-axis). You can use these     
          graphs to determine what the burn in for your analysis should be. 
          When the log probability starts to plateau you may be at station- 
          arity. Sample trees and parameters after the log probability      
          plateaus. Of course, this is not a guarantee that you are at sta- 
          tionarity. Also examine the convergence diagnostics provided by   
          the 'sump' and 'sumt' commands for all the parameters in your     
          model. Remember that the burn in is the number of samples to dis- 
          card. There are a total of ngen / samplefreq samples taken during 
          a MCMC analysis.                                                  
    
          Overlay plot for both runs:
          (1 = Run number 1; 2 = Run number 2; * = Both runs)
    
          +------------------------------------------------------------+ -5718.15
          |                    1             2 2       1               |
          |              22     2                  1    21       2     |
          |                   22   1*2     21       21    2 1   1      |
          |               111    11   1  11  1  2   12121   2  *  2    |
          |        1    1  2 21  2 2   2  2   *1      2  211     1111*2|
          |          12 21  21       12 22 12   1 2        2 12    22  |
          |      22 1  1          2     1        21                   1|
          |11  1    2 12                         1                     |
          |  1     2 2          1                  2         21        |
          |                                                            |
          |   2                        1                        2      |
          | 2 12                                                       |
          |       1                                                    |
          |  2  21                                                     |
          |2    1                                                      |
          +------+-----+-----+-----+-----+-----+-----+-----+-----+-----+ -5739.60
          ^                                                            ^
          5000                                                         20000
    
          Overwriting file "primates.nex.lstat"
    
          Estimated marginal likelihoods for runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             (Use the harmonic mean for Bayes factor comparisons of models)
    
             (Values are saved to the file primates.nex.lstat)
    
          Run   Arithmetic mean   Harmonic mean
          --------------------------------------
            1      -5719.74         -5739.95
            2      -5719.61         -5738.38
          --------------------------------------
          TOTAL    -5719.67         -5739.44
          --------------------------------------
    
    
          Model parameter summaries over the runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             Summaries are based on a total of 302 samples from 2 runs.
             Each run produced 201 samples of which 151 samples were included.
             Parameter summaries saved to file "primates.nex.pstat".
          Overwriting file "primates.nex.pstat"
    
                                                95% HPD Interval
                                              --------------------
          Parameter      Mean      Variance     Lower       Upper       Median    min ESS*  avg ESS    PSRF+ 
          --------------------------------------------------------------------------------------------------
          TL          3.085555    0.106790    2.391784    3.624876    3.089970     14.95     32.48    1.003
          r(A<->C)    0.044625    0.000081    0.026277    0.059014    0.044874     13.46     23.45    1.007
          r(A<->G)    0.463943    0.002733    0.375781    0.558146    0.467120      4.14      8.48    0.998
          r(A<->T)    0.038287    0.000093    0.020818    0.055795    0.038043     61.70    106.35    1.005
          r(C<->G)    0.029229    0.000159    0.007271    0.049807    0.028128     53.32     58.41    1.090
          r(C<->T)    0.401640    0.001769    0.327182    0.469599    0.400749      4.89     17.66    1.002
          r(G<->T)    0.022275    0.000500    0.000011    0.060454    0.017545      7.87     15.02    1.044
          pi(A)       0.354934    0.000168    0.334242    0.385890    0.353917     30.54     35.53    1.003
          pi(C)       0.320598    0.000151    0.300353    0.345347    0.320076     10.76     13.80    0.997
          pi(G)       0.082188    0.000050    0.071056    0.097157    0.081435      9.58     12.63    0.998
          pi(T)       0.242281    0.000123    0.220879    0.264470    0.240832     40.83     65.15    1.004
          alpha       0.635318    0.043081    0.388900    1.061202    0.576031     12.80     26.14    0.999
          pinvar      0.152020    0.006365    0.022122    0.297041    0.148084     21.88     27.41    1.003
          --------------------------------------------------------------------------------------------------
          * Convergence diagnostic (ESS = Estimated Sample Size); min and avg values
            correspond to minimal and average ESS among runs. 
            ESS value below 100 may indicate that the parameter is undersampled. 
          + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
            and Rubin, 1992) should approach 1.0 as runs converge.
    
    
       Summarizing trees in files "primates.nex.run1.t" and "primates.nex.run2.t"
       Using relative burnin ('relburnin=yes'), discarding the first 25 % of sampled trees
       Writing statistics to files primates.nex.<parts|tstat|vstat|trprobs|con>
       Examining first file ...
          19300 -- (-5721.874) [-5724.792] (-5724.485) (-5728.373) * [-5726.595] (-5727.388) (-5740.025) (-5723.424) -- 0:00:01
       Found one tree block in file "primates.nex.run1.t" with 201 trees in last block
       Expecting the same number of trees in the last tree block of all files
    
       Tree reading status:
    
       0      10      20      30      40      50      60      70      80      90     100
       v-------v-------v-------v-------v-------v-------v-------v-------v-------v-------v
       *********************************************************************************
    
       Read a total of 402 trees in 2 files (sampling 302 of them)
          (Each file contained 201 trees of which 151 were sampled)
       Overwriting file "primates.nex.parts"
       Overwriting file "primates.nex.tstat"
       Overwriting file "primates.nex.vstat"
       Overwriting file "primates.nex.con.tre"
       Overwriting file "primates.nex.trprobs"
                                                                                       
       General explanation:                                                          
                                                                                       
       In an unrooted tree, a taxon bipartition (split) is specified by removing a   
       branch, thereby dividing the species into those to the left and those to the  
       right of the branch. Here, taxa to one side of the removed branch are denoted 
       '.' and those to the other side are denoted '*'. Specifically, the '.' symbol 
       is used for the taxa on the same side as the outgroup.                        
                                                                                       
       In a rooted or clock tree, the tree is rooted using the model and not by      
       reference to an outgroup. Each bipartition therefore corresponds to a clade,  
       that is, a group that includes all the descendants of a particular branch in  
       the tree.  Taxa that are included in each clade are denoted using '*', and    
       taxa that are not included are denoted using the '.' symbol.                  
                                                                                       
       The output first includes a key to all the bipartitions with frequency larger 
       or equual to (Minpartfreq) in at least one run. Minpartfreq is a parameter to 
       sumt command and currently it is set to 0.10.  This is followed by a table  
       with statistics for the informative bipartitions (those including at least    
       two taxa), sorted from highest to lowest probability. For each bipartition,   
       the table gives the number of times the partition or split was observed in all
       runs (#obs) and the posterior probability of the bipartition (Probab.), which 
       is the same as the split frequency. If several runs are summarized, this is   
       followed by the minimum split frequency (Min(s)), the maximum frequency       
       (Max(s)), and the standard deviation of frequencies (Stddev(s)) across runs.  
       The latter value should approach 0 for all bipartitions as MCMC runs converge.
                                                                                       
       This is followed by a table summarizing branch lengths, node heights (if a    
       clock model was used) and relaxed clock parameters (if a relaxed clock model  
       was used). The mean, variance, and 95 % credible interval are given for each 
       of these parameters. If several runs are summarized, the potential scale      
       reduction factor (PSRF) is also given; it should approach 1 as runs converge. 
       Node heights will take calibration points into account, if such points were   
       used in the analysis.                                                         
                                                                                     
       Note that Stddev may be unreliable if the partition is not present in all     
       runs (the last column indicates the number of runs that sampled the partition 
       if more than one run is summarized). The PSRF is not calculated at all if     
       the partition is not present in all runs.The PSRF is also sensitive to small  
       sample sizes and it should only be considered a rough guide to convergence    
       since some of the assumptions allowing one to interpret it as a true potential
       scale reduction factor are violated in MrBayes.                               
                                                                                     
       List of taxa in bipartitions:                                                 
                                                                                       
          1 -- Tarsius_syrichta
          2 -- Lemur_catta
          3 -- Homo_sapiens
          4 -- Pan
          5 -- Gorilla
          6 -- Pongo
          7 -- Hylobates
          8 -- Macaca_fuscata
          9 -- M_mulatta
         10 -- M_fascicularis
         11 -- M_sylvanus
         12 -- Saimiri_sciureus
    
       Key to taxon bipartitions (saved to file "primates.nex.parts"):
    
       ID -- Partition
       ------------------
        1 -- .***********
        2 -- .*..........
        3 -- ..*.........
        4 -- ...*........
        5 -- ....*.......
        6 -- .....*......
        7 -- ......*.....
        8 -- .......*....
        9 -- ........*...
       10 -- .........*..
       11 -- ..........*.
       12 -- ...........*
       13 -- ..**********
       14 -- .......**...
       15 -- ..***.......
       16 -- ..**........
       17 -- .......****.
       18 -- ..*****.....
       19 -- ..*********.
       20 -- .......***..
       21 -- ..****......
       ------------------
    
       Summary statistics for informative taxon bipartitions
          (saved to file "primates.nex.tstat"):
    
       ID   #obs    Probab.     Sd(s)+      Min(s)      Max(s)   Nruns 
       ----------------------------------------------------------------
       13   302    1.000000    0.000000    1.000000    1.000000    2
       14   302    1.000000    0.000000    1.000000    1.000000    2
       15   302    1.000000    0.000000    1.000000    1.000000    2
       16   302    1.000000    0.000000    1.000000    1.000000    2
       17   302    1.000000    0.000000    1.000000    1.000000    2
       18   302    1.000000    0.000000    1.000000    1.000000    2
       19   302    1.000000    0.000000    1.000000    1.000000    2
       20   301    0.996689    0.004683    0.993377    1.000000    2
       21   301    0.996689    0.004683    0.993377    1.000000    2
       ----------------------------------------------------------------
       + Convergence diagnostic (standard deviation of split frequencies)
         should approach 0.0 as runs converge.
    
    
       Summary statistics for branch and node parameters
          (saved to file "primates.nex.vstat"):
    
                                               95% HPD Interval
                                             --------------------
       Parameter      Mean       Variance     Lower       Upper       Median     PSRF+  Nruns
       --------------------------------------------------------------------------------------
       length[1]     0.513647    0.009474    0.355929    0.745019    0.505779    1.007    2
       length[2]     0.358469    0.004547    0.214182    0.477468    0.358865    0.998    2
       length[3]     0.052630    0.000166    0.033932    0.081204    0.049652    1.026    2
       length[4]     0.060389    0.000134    0.037880    0.080283    0.058846    0.999    2
       length[5]     0.059234    0.000216    0.031964    0.089096    0.058824    1.006    2
       length[6]     0.149955    0.000584    0.105557    0.204468    0.148979    0.998    2
       length[7]     0.178891    0.001015    0.124323    0.242382    0.176846    1.004    2
       length[8]     0.018251    0.000042    0.007738    0.030440    0.017492    1.000    2
       length[9]     0.023514    0.000055    0.010818    0.037358    0.022918    1.009    2
       length[10]    0.057602    0.000143    0.036232    0.080239    0.057312    1.001    2
       length[11]    0.073997    0.000411    0.035494    0.109720    0.074867    1.001    2
       length[12]    0.460928    0.006167    0.319299    0.612673    0.457111    0.999    2
       length[13]    0.292671    0.005399    0.170375    0.450329    0.285487    1.002    2
       length[14]    0.036525    0.000101    0.021322    0.059583    0.035773    1.003    2
       length[15]    0.087771    0.000548    0.047208    0.134095    0.084910    0.998    2
       length[16]    0.031343    0.000163    0.009393    0.056176    0.029770    1.001    2
       length[17]    0.271358    0.002986    0.183774    0.396243    0.266546    0.998    2
       length[18]    0.128498    0.001412    0.056749    0.198840    0.126113    1.026    2
       length[19]    0.123403    0.002179    0.039094    0.213598    0.124869    0.997    2
       length[20]    0.049751    0.000460    0.011570    0.089320    0.047178    0.998    2
       length[21]    0.057042    0.000450    0.018827    0.095637    0.055108    1.005    2
       --------------------------------------------------------------------------------------
       + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
         and Rubin, 1992) should approach 1.0 as runs converge. NA is reported when
         deviation of parameter values within all runs is 0 or when a parameter
         value (a branch length, for instance) is not sampled in all runs.
    
    
       Summary statistics for partitions with frequency >= 0.10 in at least one run:
           Average standard deviation of split frequencies = 0.001041
           Maximum standard deviation of split frequencies = 0.004683
           Average PSRF for parameter values (excluding NA and >10.0) = 1.004
           Maximum PSRF for parameter values = 1.026
    
    
       Clade credibility values:
    
       /---------------------------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |---------------------------------------------------------- Lemur_catta (2)
       |                                                                               
       |                                                 /-------- Homo_sapiens (3)
       |                                        /---100--+                             
       |                                        |        \-------- Pan (4)
       |                                /--100--+                                      
       |                                |       \----------------- Gorilla (5)
       |                        /--100--+                                              
       +                        |       \------------------------- Pongo (6)
       |                /--100--+                                                      
       |                |       \--------------------------------- Hylobates (7)
       |                |                                                              
       |                |                                /-------- Macaca_fuscata (8)
       |       /---100--+                       /---100--+                             
       |       |        |                       |        \-------- M_mulatta (9)
       |       |        |               /--100--+                                      
       |       |        |               |       \----------------- M_fascicularis (10)
       \--100--+        \------100------+                                              
               |                        \------------------------- M_sylvanus (11)
               |                                                                       
               \-------------------------------------------------- Saimiri_sciure~ (12)
                                                                                       
    
       Phylogram (based on average branch lengths):
    
       /-------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |--------------------------- Lemur_catta (2)
       |                                                                               
       |                                                    /---- Homo_sapiens (3)
       |                                                  /-+                          
       |                                                  | \----- Pan (4)
       |                                            /-----+                            
       |                                            |     \----- Gorilla (5)
       |                                        /---+                                  
       +                                        |   \----------- Pongo (6)
       |                              /---------+                                      
       |                              |         \------------- Hylobates (7)
       |                              |                                                
       |                              |                         /-- Macaca_fuscata (8)
       |                     /--------+                       /-+                      
       |                     |        |                       | \-- M_mulatta (9)
       |                     |        |                   /---+                        
       |                     |        |                   |   \---- M_fascicularis (10)
       \---------------------+        \-------------------+                            
                             |                            \------ M_sylvanus (11)
                             |                                                         
                             \---------------------------------- Saimiri_sciure~ (12)
                                                                                       
       |--------------| 0.200 expected changes per site
    
                                                                               Calculating tree probabilities...
    
       Credible sets of trees (3 trees sampled):
          99 % credible set contains 1 tree
    
       Terminating log output
       Exiting mrbayes block
       Reached end of file
    
       Tasks completed, exiting program because mode is noninteractive
       To return control to the command line after completion of file processing, 
       set mode to interactive with 'mb -i <filename>' (i is for interactive)
       or use 'set mode=interactive'
    
          19200 -- [-5722.505] (-5733.322) (-5724.313) (-5728.193) * [-5726.219] (-5723.355) (-5737.119) (-5727.731) -- 0:00:01
          19600 -- (-5725.838) [-5724.349] (-5723.589) (-5731.765) * (-5730.122) (-5722.817) (-5732.089) [-5723.389] -- 0:00:00
          19400 -- (-5726.046) [-5724.227] (-5730.617) (-5729.921) * (-5730.258) [-5726.591] (-5736.859) (-5726.019) -- 0:00:00
          19300 -- (-5721.874) [-5724.792] (-5724.485) (-5728.373) * [-5726.595] (-5727.388) (-5740.025) (-5723.424) -- 0:00:01
          19700 -- (-5727.058) [-5724.178] (-5726.005) (-5731.873) * (-5728.781) (-5719.736) [-5725.800] (-5726.582) -- 0:00:00
          19500 -- [-5723.966] (-5721.868) (-5728.441) (-5733.949) * (-5728.097) [-5723.998] (-5735.081) (-5726.068) -- 0:00:00
          19400 -- (-5726.046) [-5724.227] (-5730.617) (-5729.921) * (-5730.258) [-5726.591] (-5736.859) (-5726.019) -- 0:00:00
          19800 -- (-5725.546) (-5723.846) [-5727.279] (-5739.523) * (-5730.304) [-5723.443] (-5725.947) (-5725.391) -- 0:00:00
          19600 -- (-5725.838) [-5724.349] (-5723.589) (-5731.765) * (-5730.122) (-5722.817) (-5732.089) [-5723.389] -- 0:00:00
          19500 -- [-5723.966] (-5721.868) (-5728.441) (-5733.949) * (-5728.097) [-5723.998] (-5735.081) (-5726.068) -- 0:00:00
          19900 -- (-5723.804) (-5723.788) [-5721.689] (-5731.084) * (-5726.862) (-5723.756) [-5729.207] (-5728.809) -- 0:00:00
          19700 -- (-5727.058) [-5724.178] (-5726.005) (-5731.873) * (-5728.781) (-5719.736) [-5725.800] (-5726.582) -- 0:00:00
          19600 -- (-5725.838) [-5724.349] (-5723.589) (-5731.765) * (-5730.122) (-5722.817) (-5732.089) [-5723.389] -- 0:00:00
          20000 -- (-5720.752) (-5721.881) (-5721.223) [-5735.204] * (-5726.628) [-5719.923] (-5724.544) (-5728.339) -- 0:00:00
    
          Average standard deviation of split frequencies: 0.001041
    
          Analysis completed in 28 seconds
          Analysis used 27.94 seconds of CPU time
          Likelihood of best state for "cold" chain of run 1 was -5714.62
          Likelihood of best state for "cold" chain of run 2 was -5714.34
    
          Acceptance rates for the moves in the "cold" chain of run 1:
             With prob.   (last 100)   chain accepted proposals by move
                31.5 %     ( 34 %)     Dirichlet(Revmat)
                59.4 %     ( 57 %)     Slider(Revmat)
                16.5 %     ( 17 %)     Dirichlet(Pi)
                25.8 %     ( 34 %)     Slider(Pi)
                34.2 %     ( 39 %)     Multiplier(Alpha)
                66.9 %     ( 65 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.2 %     (  0 %)     ExtTBR(Tau,V)
                 0.2 %     (  1 %)     NNI(Tau,V)
                 0.5 %     (  1 %)     ParsSPR(Tau,V)
                36.9 %     ( 27 %)     Multiplier(V)
                24.1 %     ( 27 %)     Nodeslider(V)
                15.6 %     ( 14 %)     TLMultiplier(V)
    
          Acceptance rates for the moves in the "cold" chain of run 2:
             With prob.   (last 100)   chain accepted proposals by move
                25.1 %     ( 26 %)     Dirichlet(Revmat)
                62.8 %     ( 62 %)     Slider(Revmat)
                14.3 %     ( 15 %)     Dirichlet(Pi)
                20.4 %     ( 20 %)     Slider(Pi)
                37.3 %     ( 35 %)     Multiplier(Alpha)
                69.1 %     ( 66 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.3 %     (  1 %)     ExtTBR(Tau,V)
                 0.4 %     (  0 %)     NNI(Tau,V)
                 0.8 %     (  0 %)     ParsSPR(Tau,V)
                35.7 %     ( 29 %)     Multiplier(V)
                24.8 %     ( 23 %)     Nodeslider(V)
                15.0 %     ( 18 %)     TLMultiplier(V)
    
          Chain swap information for run 1:
    
                     1     2     3     4 
               --------------------------
             1 |        0.63  0.38  0.26 
             2 |  3299        0.60  0.42 
             3 |  3343  3296        0.70 
             4 |  3350  3282  3430       
    
          Chain swap information for run 2:
    
                     1     2     3     4 
               --------------------------
             1 |        0.63  0.42  0.29 
             2 |  3386        0.69  0.47 
             3 |  3323  3335        0.74 
             4 |  3231  3374  3351       
    
          Upper diagonal: Proportion of successful state exchanges between chains
          Lower diagonal: Number of attempted state exchanges between chains
    
          Chain information:
    
            ID -- Heat 
           -----------
             1 -- 1.00  (cold chain)
             2 -- 0.91 
             3 -- 0.83 
             4 -- 0.77 
    
          Heat = 1 / (1 + T * (ID - 1))
             (where T = 0.10 is the temperature and ID is the chain number)
    
          Summarizing parameters in files primates.nex.run1.p and primates.nex.run2.p
          Writing summary statistics to file primates.nex.pstat
          Using relative burnin ('relburnin=yes'), discarding the first 25 % of samples
    
          Below are rough plots of the generation (x-axis) versus the log   
          probability of observing the data (y-axis). You can use these     
          graphs to determine what the burn in for your analysis should be. 
          When the log probability starts to plateau you may be at station- 
          arity. Sample trees and parameters after the log probability      
          plateaus. Of course, this is not a guarantee that you are at sta- 
          tionarity. Also examine the convergence diagnostics provided by   
          the 'sump' and 'sumt' commands for all the parameters in your     
          model. Remember that the burn in is the number of samples to dis- 
          card. There are a total of ngen / samplefreq samples taken during 
          a MCMC analysis.                                                  
    
          Overlay plot for both runs:
          (1 = Run number 1; 2 = Run number 2; * = Both runs)
    
          +------------------------------------------------------------+ -5718.15
          |                    1             2 2       1               |
          |              22     2                        19700 -- (-5727.058) [-5724.178] (-5726.005) (-5731.873) * (-5728.781) (-5719.736) [-5725.800] (-5726.582) -- 0:00:00
    1    21       2     |
          |                   22   1*2     21       21    2 1   1      |
          |               111    11   1  11  1  2   12121   2  *  2    |
          |        1    1  2 21  2 2   2  2   *1      2  211     1111*2|
          |          12 21  21       12 22 12   1 2        2 12    22  |
          |      22 1  1          2     1        21                   1|
          |11  1    2 12               19800 --      (-5725.546)   (-5723.846) [-5727.279]   (-5739.523) * (-5730.304) [-5723.443]      (-5725.947) (-5725.391) -- 0:00:00
      1                     |
          |  1     2 2          1                  2         21        |
          |                                                            |
          |   2                        1                        2      |
          | 2 12                                                       |
          |       1                                                    |
          |  2  21                                                     |
          |2    1                                                      |
          +------+-----+-----+-----+-----+-----+-----+-----+-----+-----+ -5739.60
          ^                                                            ^
          5000                                                         20000
    
          Overwriting file "primates.nex.lstat"
    
          Estimated marginal likelihoods for runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             (Use the harmonic mean for Bayes factor comparisons of models)
    
             (Values are saved to the file primates.nex.lstat)
    
          Run   Arithmetic mean   Harmonic mean
          --------------------------------------
            1      -5719.74         -5739.95
            2      -5719.61         -5738.38
          --------------------------------------
          TOTAL    -5719.67         -5739.44
          --------------------------------------
    
    
          Model parameter summaries over the runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             Summaries are based on a total of 302 samples from 2 runs.
             Each run produced 201 samples of which 151 samples were included.
             Parameter summaries saved to file "primates.nex.pstat".
          Overwriting file "primates.nex.pstat"
    
                                                95% HPD Interval
                                              --------------------
          Parameter      Mean      Variance     Lower       Upper       Median    min ESS*  avg ESS    PSRF+ 
          --------------------------------------------------------------------------------------------------
          TL          3.085555    0.106790    2.391784    3.624876    3.089970     14.95     32.48    1.003
          r(A<->C)    0.044625    0.000081    0.026277    0.059014    0.044874     13.46     23.45    1.007
          r(A<->G)    0.463943    0.002733    0.375781    0.558146    0.467120      4.14      8.48    0.998
          r(A<->T)    0.038287    0.000093    0.020818    0.055795    0.038043     61.70    106.35    1.005
          r(C<->G)    0.029229    0.000159    0.007271    0.049807    0.028128     53.32     58.41    1.090
          r(C<->T)    0.401640    0.001769    0.327182    0.469599    0.400749      4.89     17.66    1.002
          r(G<->T)    0.022275    0.000500    0.000011    0.060454    0.017545      7.87     15.02    1.044
          pi(A)       0.354934    0.000168    0.334242    0.385890    0.353917     30.54     35.53    1.003
          pi(C)       0.320598    0.000151    0.300353    0.345347    0.320076     10.76     13.80    0.997
          pi(G)       0.082188    0.000050    0.071056    0.097157    0.081435      9.58     12.63    0.998
          pi(T)       0.242281    0.000123    0.220879    0.264470    0.240832     40.83     65.15    1.004
          alpha       0.635318    0.043081    0.388900    1.061202    0.576031     12.80     26.14    0.999
          pinvar      0.152020    0.006365    0.022122    0.297041    0.148084     21.88     27.41    1.003
          --------------------------------------------------------------------------------------------------
          * Convergence diagnostic (ESS = Estimated Sample Size); min and avg values
            correspond to minimal and average ESS among runs. 
            ESS value below 100 may indicate that the parameter is undersampled. 
          + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
            and Rubin, 1992) should approach 1.0 as runs converge.
    
    
       Summarizing trees in files "primates.nex.run1.t" and "primates.nex.run2.t"
       Using relative burnin ('relburnin=yes'), discarding the first 25 % of sampled trees
       Writing statistics to files primates.nex.<parts|tstat|vstat|trprobs|con>
       Examining first file ...
       Found one tree block in file "primates.nex.run1.t" with 201 trees in last block
       Expecting the same number of trees in the last tree block of all files
    
       Tree reading status:
    
       0      10      20      30      40      50      60      70      80      90     100
       v-------v-------v-------v-------v-------v-------v-------v-------v-------v-------v
       *********************************************************************************
    
       Read a total of 402 trees in 2 files (sampling 302 of them)
          (Each file contained 201 trees of which 151 were sampled)
       Overwriting file "primates.nex.parts"
       Overwriting file "primates.nex.tstat"
       Overwriting file "primates.nex.vstat"
       Overwriting file "primates.nex.con.tre"
       Overwriting file "primates.nex.trprobs"
                                                                                       
       General explanation:                                                          
                                                                                       
       In an unrooted tree, a taxon bipartition (split) is specified by removing a   
       branch, thereby dividing the species into those to the left and those to the  
       right of the branch. Here, taxa to one side of the removed branch are denoted 
       '.' and those to the other side are denoted '*'. Specifically, the '.' symbol 
       is used for the taxa on the same side as the outgroup.                        
                                                                                       
       In a rooted or clock tree, the tree is rooted using the model and not by      
       reference to an outgroup. Each bipartition therefore corresponds to a clade,  
       that is, a group that includes all the descendants of a particular branch in  
       the tree.  Taxa that are included in each clade are denoted using '*', and    
       taxa that are not included are denoted using the '.' symbol.                  
                                                                                       
       The output first includes a key to all the bipartitions with frequency larger 
       or equual to (Minpartfreq) in at least one run. Minpartfreq is a parameter to 
       sumt command and currently it is set to 0.10.  This is followed by a table  
       with statistics for the informative bipartitions (those including at least    
       two taxa), sorted from highest to lowest probability. For each bipartition,   
       the table gives the number of times the partition or split was observed in all
       runs (#obs) and the posterior probability of the bipartition (Probab.), which 
       is the same as the split frequency. If several runs are summarized, this is   
       followed by the minimum split frequency (Min(s)), the maximum frequency       
       (Max(s)), and the standard deviation of frequencies (Stddev(s)) across runs.  
       The latter value should approach 0 for all bipartitions as MCMC runs converge.
                                                                                       
       This is followed by a table summarizing branch lengths, node heights (if a    
       clock model was used) and relaxed clock parameters (if a relaxed clock model  
       was used). The mean, variance, and 95 % credible interval are given for each 
       of these parameters. If several runs are summarized, the potential scale      
       reduction factor (PSRF) is also given; it should approach 1 as runs converge. 
       Node heights will take calibration points into account, if such points were   
       used in the analysis.                                                         
                                                                                     
       Note that Stddev may be unreliable if the partition is not present in all     
       runs (the last column indicates the number of runs that sampled the partition 
       if more than one run is summarized). The PSRF is not calculated at all if     
       the partition is not present in all runs.The PSRF is also sensitive to small  
       sample sizes and it should only be considered a rough guide to convergence    
       since some of the assumptions allowing one to interpret it as a true potential
       scale reduction factor are violated in MrBayes.                               
                                                                                     
       List of taxa in bipartitions:                                                 
                                                                                       
          1 -- Tarsius_syrichta
          2 -- Lemur_catta
          3 -- Homo_sapiens
          4 -- Pan
          5 -- Gorilla
          6 -- Pongo
          7 -- Hylobates
          8 -- Macaca_fuscata
          9 -- M_mulatta
         10 -- M_fascicularis
         11 -- M_sylvanus
         12 -- Saimiri_sciureus
    
       Key to taxon bipartitions (saved to file "primates.nex.parts"):
    
       ID -- Partition
       ------------------
        1 -- .***********
        2 -- .*..........
        3 -- ..*.........
        4 -- ...*........
        5 -- ....*.......
        6 -- .....*......
        7 -- ......*.....
        8 -- .......*....
        9 -- ........*...
       10 -- .........*..
       11 -- ..........*.
       12 -- ...........*
       13 -- ..**********
       14 -- .......**...
       15 -- ..***.......
       16 -- ..**........
       17 -- .......****.
       18 -- ..*****.....
       19 -- ..*********.
       20 -- .......***..
       21 -- ..****......
       ------------------
    
       Summary statistics for informative taxon bipartitions
          (saved to file "primates.nex.tstat"):
    
       ID   #obs    Probab.     Sd(s)+      Min(s)      Max(s)   Nruns 
       ----------------------------------------------------------------
       13   302    1.000000    0.000000    1.000000    1.000000    2
       14   302    1.000000    0.000000    1.000000    1.000000    2
       15   302    1.000000    0.000000    1.000000    1.000000    2
       16   302    1.000000    0.000000    1.000000    1.000000    2
       17   302    1.000000    0.000000    1.000000    1.000000    2
       18   302    1.000000    0.000000    1.000000    1.000000    2
       19   302    1.000000    0.000000    1.000000    1.000000    2
       20   301    0.996689    0.004683    0.993377    1.000000    2
       21   301    0.996689    0.004683    0.993377    1.000000    2
       ----------------------------------------------------------------
       + Convergence diagnostic (standard deviation of split frequencies)
         should approach 0.0 as runs converge.
    
    
       Summary statistics for branch and node parameters
          (saved to file "primates.nex.vstat"):
    
                                               95% HPD Interval
                                             --------------------
       Parameter      Mean       Variance     Lower       Upper       Median     PSRF+  Nruns
       --------------------------------------------------------------------------------------
       length[1]     0.513647    0.009474    0.355929    0.745019    0.505779    1.007    2
       length[2]     0.358469    0.004547    0.214182    0.477468    0.358865    0.998    2
       length[3]     0.052630    0.000166    0.033932    0.081204    0.049652    1.026    2
       length[4]     0.060389    0.000134    0.037880    0.080283    0.058846    0.999    2
       length[5]     0.059234    0.000216    0.031964    0.089096    0.058824    1.006    2
       length[6]     0.149955    0.000584    0.105557    0.204468    0.148979    0.998    2
       length[7]     0.178891    0.001015    0.124323    0.242382    0.176846    1.004    2
       length[8]     0.018251    0.000042    0.007738    0.030440    0.017492    1.000    2
       length[9]     0.023514    0.000055    0.010818    0.037358    0.022918    1.009    2
       length[10]    0.057602    0.000143    0.036232    0.080239    0.057312    1.001    2
       length[11]    0.073997    0.000411    0.035494    0.109720    0.074867    1.001    2
       length[12]    0.460928    0.006167    0.319299    0.612673    0.457111    0.999    2
       length[13]    0.292671    0.005399    0.170375    0.450329    0.285487    1.002    2
       length[14]    0.036525    0.000101    0.021322    0.059583    0.035773    1.003    2
       length[15]    0.087771    0.000548    0.047208    0.134095    0.084910    0.998    2
       length[16]    0.031343    0.000163    0.009393    0.056176    0.029770    1.001    2
       length[17]    0.271358    0.002986    0.183774    0.396243    0.266546    0.998    2
       length[18]    0.128498    0.001412    0.056749    0.198840    0.126113    1.026    2
       length[19]    0.123403    0.002179    0.039094    0.213598    0.124869    0.997    2
       length[20]    0.049751    0.000460    0.011570    0.089320    0.047178    0.998    2
       length[21]    0.057042    0.000450    0.018827    0.095637    0.055108    1.005    2
       --------------------------------------------------------------------------------------
       + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
         and Rubin, 1992) should approach 1.0 as runs converge. NA is reported when
         deviation of parameter values within all runs is 0 or when a parameter
         value (a branch length, for instance) is not sampled in all runs.
    
    
       Summary statistics for partitions with frequency >= 0.10 in at least one run:
           Average standard deviation of split frequencies = 0.001041
           Maximum standard deviation of split frequencies = 0.004683
           Average PSRF for parameter values (excluding NA and >10.0) = 1.004
           Maximum PSRF for parameter values = 1.026
    
    
       Clade credibility values:
    
       /---------------------------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |---------------------------------------------------------- Lemur_catta (2)
       |                                                                               
       |                                                 /-------- Homo_sapiens (3)
       |                                        /---100--+                             
       |                                        |        \-------- Pan (4)
       |                                /--100--+                                      
       |                                |       \----------------- Gorilla (5)
       |                        /--100--+                                              
       +                        |       \------------------------- Pongo (6)
       |                /--100--+                                                      
       |                |       \--------------------------------- Hylobates (7)
       |                |                                                              
       |                |                                /-------- Macaca_fuscata (8)
       |       /---100--+                       /---100--+                             
       |       |        |                       |        \-------- M_mulatta (9)
       |       |        |               /--100--+                                      
       |       |        |               |       \----------------- M_fascicularis (10)
       \--100--+        \------100------+                                              
               |                        \------------------------- M_sylvanus (11)
               |                                                                       
               \-------------------------------------------------- Saimiri_sciure~ (12)
                                                                                       
    
       Phylogram (based on average branch lengths):
    
       /-------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |--------------------------- Lemur_catta (2)
       |                                                                               
       |                                                    /---- Homo_sapiens (3)
       |                                                  /-+                          
       |                                                  | \----- Pan (4)
       |                                            /-----+                            
       |                                            |     \----- Gorilla (5)
       |                                        /---+                                  
       +                                        |   \----------- Pongo (6)
       |                              /---------+                                      
       |                              |         \------------- Hylobates (7)
       |                              |                                                
       |                              |                         /-- Macaca_fuscata (8)
       |                     /--------+                       /-+                      
       |                     |        |                       | \-- M_mulatta (9)
       |                     |        |                   /---+                        
       |                     |        |                   |   \---- M_fascicularis (10)
       \---------------------+        \-------------------+                            
                             |                            \------ M_sylvanus (11)
                             |                                                         
                             \---------------------------------- Saimiri_sciure~ (12)
                                                                                       
       |--------------| 0.200 expected changes per site
    
                                                                               Calculating tree probabilities...
    
       Credible sets of trees (3 trees sampled):
          99 % credible set contains 1 tree
    
       Terminating log output
       Exiting mrbayes block
       Reached end of file
    
       Tasks completed, exiting program because mode is noninteractive
       To return control to the command line after completion of file processing, 
       set mode to interactive with 'mb -i <filename>' (i is for interactive)
       or use 'set mode=interactive'
    
          19800 -- (-5725.546) (-5723.846) [-5727.279] (-5739.523) * (-5730.304) [-5723.443] (-5725.947) (-5725.391) -- 0:00:00
          19900 -- (-5723.804) (-5723.788) [-5721.689] (-5731.084) * (-5726.862) (-5723.756) [-5729.207] (-5728.809) -- 0:00:00
          19900 -- (-5723.804) (-5723.788) [-5721.689] (-5731.084) * (-5726.862) (-5723.756) [-5729.207] (-5728.809) -- 0:00:00
          20000 -- (-5720.752) (-5721.881) (-5721.223) [-5735.204] * (-5726.628) [-5719.923] (-5724.544) (-5728.339) -- 0:00:00
    
          Average standard deviation of split frequencies: 0.001041
    
          Analysis completed in 29 seconds
          Analysis used 28.13 seconds of CPU time
          Likelihood of best state for "cold" chain of run 1 was -5714.62
          Likelihood of best state for "cold" chain of run 2 was -5714.34
    
          Acceptance rates for the moves in the "cold" chain of run 1:
             With prob.   (last 100)   chain accepted proposals by move
                31.5 %     ( 34 %)     Dirichlet(Revmat)
                59.4 %     ( 57 %)     Slider(Revmat)
                16.5 %     ( 17 %)     Dirichlet(Pi)
                25.8 %     ( 34 %)     Slider(Pi)
                34.2 %     ( 39 %)     Multiplier(Alpha)
                66.9 %     ( 65 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.2 %     (  0 %)     ExtTBR(Tau,V)
                 0.2 %     (  1 %)     NNI(Tau,V)
                 0.5 %     (  1 %)     ParsSPR(Tau,V)
                36.9 %     ( 27 %)     Multiplier(V)
                24.1 %     ( 27 %)     Nodeslider(V)
                15.6 %     ( 14 %)     TLMultiplier(V)
    
          Acceptance rates for the moves in the "cold" chain of run 2:
             With prob.   (last 100)   chain accepted proposals by move
                25.1 %     ( 26 %)     Dirichlet(Revmat)
                62.8 %     ( 62 %)     Slider(Revmat)
                14.3 %     ( 15 %)     Dirichlet(Pi)
                20.4 %     ( 20 %)     Slider(Pi)
                37.3 %     ( 35 %)     Multiplier(Alpha)
                69.1 %     ( 66 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.3 %     (  1 %)     ExtTBR(Tau,V)
                 0.4 %     (  0 %)     NNI(Tau,V)
                 0.8 %     (  0 %)     ParsSPR(Tau,V)
                35.7 %     ( 29 %)     Multiplier(V)
                24.8 %     ( 23 %)     Nodeslider(V)
                15.0 %     ( 18 %)     TLMultiplier(V)
    
          Chain swap information for run 1:
    
                     1     2     3     4 
               --------------------------
             1 |        0.63  0.38  0.26 
             2 |  3299        0.60  0.42 
             3 |  3343  3296        0.70 
             4 |  3350  3282  3430       
    
          Chain swap information for run 2:
    
                     1     2     3     4 
               --------------------------
             1 |        0.63  0.42  0.29 
             2 |  3386        0.69  0.47 
             3 |  3323  3335        0.74 
             4 |  3231  3374  3351       
    
          Upper diagonal: Proportion of successful state exchanges between chains
          Lower diagonal: Number of attempted state exchanges between chains
    
          Chain information:
    
            ID -- Heat 
           -----------
             1 -- 1.00  (cold chain)
             2 -- 0.91 
             3 -- 0.83 
             4 -- 0.77 
    
          Heat = 1 / (1 + T * (ID - 1))
             (where T = 0.10 is the temperature and ID is the chain number)
    
          Summarizing parameters in files primates.nex.run1.p and primates.nex.run2.p
          Writing summary statistics to file primates.nex.pstat
          Using relative burnin ('relburnin=yes'), discarding the first 25 % of samples
    
          Below are rough plots of the generation (x-axis) versus the log   
          probability of observing the data (y-axis). You can use these     
          graphs to determine what the burn in for your analysis should be. 
          When the log probability starts to plateau you may be at station- 
          arity. Sample trees and parameters after the log probability      
          plateaus. Of course, this is not a guarantee that you are at sta- 
          tionarity. Also examine the convergence diagnostics provided by   
          the 'sump' and 'sumt' commands for all the parameters in your     
          model. Remember that the burn in is the number of samples to dis- 
          card. There are a total of ngen / samplefreq samples taken during 
          a MCMC analysis.                                                  
    
          Overlay plot for both runs:
          (1 = Run number 1; 2 = Run number 2; * = Both runs)
    
          +------------------------------------------------------------+ -5718.15
          |                    1             2 2       1               |
          |              22     2                  1    21       2     |
          |                   22   1*2     21       21    2 1   1      |
          |               111    11   1  11  1  2   12121   2  *  2    |
          |        1    1  2 21  2 2   2  2   *1      2  211     1111*2|
          |          12 21  21       12 22 12   1 2        2 12    22  |
          |      22 1  1          2     1        21                   1|
          |11  1    2 12                         1                     |
          |  1     2 2          1                  2         21        |
          |                                                            |
          |   2                        1                        2      |
          | 2 12                                                       |
          |       1                                                    |
          |  2  21                                                     |
          |2    1                                                      |
          +------+-----+-----+-----+-----+-----+-----+-----+-----+-----+ -5739.60
          ^                                                            ^
          5000                                                         20000
    
          Overwriting file "primates.nex.lstat"
    
          Estimated marginal likelihoods for runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             (Use the harmonic mean for Bayes factor comparisons of models)
    
             (Values are saved to the file primates.nex.lstat)
    
          Run   Arithmetic mean   Harmonic mean
          --------------------------------------
            1      -5719.74         -5739.95
            2      -5719.61         -5738.38
          --------------------------------------
          TOTAL    -5719.67         -5739.44
          --------------------------------------
    
    
          Model parameter summaries over the runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             Summaries are based on a total of 302 samples from 2 runs.
             Each run produced 201 samples of which 151 samples were included.
             Parameter summaries saved to file "primates.nex.pstat".
          Overwriting file "primates.nex.pstat"
    
                                                95% HPD Interval
                                              --------------------
          Parameter      Mean      Variance     Lower       Upper       Median    min ESS*  avg ESS    PSRF+ 
          --------------------------------------------------------------------------------------------------
          TL          3.085555    0.106790    2.391784    3.624876    3.089970     14.95     32.48    1.003
          r(A<->C)    0.044625    0.000081    0.026277    0.059014    0.044874     13.46     23.45    1.007
          r(A<->G)    0.463943    0.002733    0.375781    0.558146    0.467120      4.14      8.48    0.998
          r(A<->T)    0.038287    0.000093    0.020818    0.055795    0.038043     61.70    106.35    1.005
          r(C<->G)    0.029229    0.000159    0.007271    0.049807    0.028128     53.32     58.41    1.090
          r(C<->T)    0.401640    0.001769    0.327182    0.469599    0.400749      4.89     17.66    1.002
          r(G<->T)    0.022275    0.000500    0.000011    0.060454    0.017545      7.87     15.02    1.044
          pi(A)       0.354934    0.000168    0.334242    0.385890    0.353917     30.54     35.53    1.003
          pi(C)       0.320598    0.000151    0.300353    0.345347    0.320076     10.76     13.80    0.997
          pi(G)       0.082188    0.000050    0.071056    0.097157    0.081435      9.58     12.63    0.998
          pi(T)       0.242281    0.000123    0.220879    0.264470    0.240832     40.83     65.15    1.004
          alpha       0.635318    0.043081    0.388900    1.061202    0.576031     12.80     26.14    0.999
          pinvar      0.152020    0.006365    0.022122    0.297041    0.148084     21.88     27.41    1.003
          --------------------------------------------------------------------------------------------------
          * Convergence diagnostic (ESS = Estimated Sample Size); min and avg values
            correspond to minimal and average ESS among runs. 
            ESS value below 100 may indicate that the parameter is undersampled. 
          + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
            and Rubin, 1992) should approach 1.0 as runs converge.
    
    
       Summarizing trees in files "primates.nex.run1.t" and "primates.nex.run2.t"
       Using relative burnin ('relburnin=yes'), discarding the first 25 % of sampled trees
       Writing statistics to files primates.nex.<parts|tstat|vstat|trprobs|con>
       Examining first file ...
       Found one tree block in file "primates.nex.run1.t" with 201 trees in last block
       Expecting the same number of trees in the last tree block of all files
    
       Tree reading status:
    
       0      10      20      30      40      50      60      70      80      90     100
       v-------v-------v-------v-------v-------v-------v-------v-------v-------v-------v
       ***********      20000 -- (-5720.752) (-5721.881) (-5721.223) [-5735.204] * *(-5726.628) [-5719.923] (-5724.544) (-5728.339) -- 0:00:00
    
    *      Average standard deviation of split frequencies: 0.001041
    **
          Analysis completed in 29 seconds
          Analysis used 28.29 seconds of CPU time
          Likelihood of best state for "cold" chain of run 1 was -5714.62
          Likelihood of best state for "cold" chain of run 2 was -5714.34
    
          Acceptance rates for the moves in the "cold" chain of run 1:
             With prob.   (last 100)   chain accepted proposals by move
                31.5 %     ( 34 %)     Dirichlet(Revmat)
                59.4 %     ( 57 %)     Slider(Revmat)
    *            16.5 %     ( 17 %)     Dirichlet(Pi)
                25.8 %     ( 34 %)     Slider(Pi)
                34.2 %     ( 39 %)     Multiplier(Alpha)
                66.9 %     ( 65 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.2 %     (  0 %)     ExtTBR(Tau,V)
                 0.2 %     (  1 %)     NNI(Tau,V)
                 0.5 %     (  1 %)     ParsSPR(Tau,V)
                36.9 %     ( 27 %)     Multiplier(V)
                24.1 %     ( 27 %)     Nodeslider(V)
                15.6 %     ( 14 %)     TLMultiplier(V)
    
          Acceptance rates for the moves in the "cold" chain of run 2:
             With prob.   (last 100)   chain accepted proposals by move
                25.1 %     ( 26 %)     Dirichlet(Revmat)
                62.8 %     ( 62 %)     Slider(Revmat)
                14.3 %     ( 15 %)     Dirichlet(Pi)
                20.4 %     ( 20 %)     Slider(Pi)
                37.3 %     ( 35 %)     Multiplier(Alpha)
                69.1 %     ( 66 %)     Slider(Pinvar)
                 0.2 %     (  0 %)     ExtSPR(Tau,V)
                 0.3 %     (  1 %)     ExtTBR(Tau,V)
                 0.4 %     (  0 %)     NNI(Tau,V)
                 0.8 %     (  0 %)     ParsSPR(Tau,V)
                35.7 %     ( 29 %)     Multiplier(V)
                24.8 %     ( 23 %)     Nodeslider(V)
                15.0 %     ( 18 %)     TLMultiplier(V)
    
          Chain swap information for run 1:
    
                     1     2 *    3     4 
               --------------------------
             1 |        0.63  0.38  0.26 
             2 |  3299        0.60  0.42 
             3 |  3343  3296        0.70 
             4 |  3350  3282  3430       
    
          Chain swap information for run 2:
    
                     1     2     3     4 
               --------------------------*
             1 |        0.63  0.42  0.29 
             2 |  3386        0.69  0.47 
             3 |  3323  3335        0.74 
             4 |  3231  3374  3351 *      
    
          Upper diagonal: Proportion of successful state exchanges between chains
          Lower diagonal: Number of attempted state exchanges between chains
    
          Chain information:
    
            ID -- Heat 
           -----------
             1 -- 1.00  (cold chain)
             2 -- 0.91 
             3 -- 0.83 
             4 -- 0.77 
    
          Heat = 1 / (1 + T * (ID - 1))
             (where T = 0.10 is the temperature and ID is the chain number)
    
    **      Summarizing parameters in files primates.nex.run1.p and primates.nex.run2.p
          Writing summary statistics to file primates.nex.pstat
          Using relative burnin ('relburnin=yes'), discarding the first 25 % of samples
    **********************************
          Below are rough plots of the generation (x-axis) versus the log   
          probability of observing the data (y-axis). You can use these     
          graphs to determine what the burn in for your analysis should be. 
          When the log probability starts to plateau you may be at station- 
          arity. Sample trees and parameters after the log probability      
          plateaus. Of course, this is not a guarantee that you are at sta- 
          tionarity. Also examine the convergence diagnostics provided by   
          the 'sump' and 'sumt' commands for all the parameters in your     
          model. Remember that the burn in is the number of samples to dis- 
          card. There are a total of ngen / samplefreq samples taken during 
          a MCMC analysis.                                                  
    
          Overlay plot for both runs:
          (1 = Run number 1; 2 = Run number 2; * = Both runs)
    
          +---------------------------*---------------------------------+ -5718.15
          |                    1             2 2       1               |
          |   *           22     2                  1    21       2     |
          |                   22   1*2     21       21    2 1   1    *  |
          |               111    11   1  11  1  2   12121   2  *  2    |
          |        1    1  2 21  2 2   2  *2   *1      2  211     1111*2|
          |          12 21  21       12 22 12   1 2        2 12    22  |
          |      *22 1  1          2     1        21                   1|
          |11  1    2 12                         1                     |
          |*  1     2 2          1                  2         21        |
          |                                   *                         |
          |   2                        1                        2      |
          | 2* 12                                                       |
          |       1                               *                     |
          |  2  21                                                     |
          |2    1                         *                             |
          +------+-----+-----+-----+-----+-----+-----+-----+-----+-----+ -5739.60
          ^                     *                                       ^
          5000                                                         20000
    
          Overwriting file "primates.nex.lstat"
    *
          Estimated marginal likelihoods for runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             (Use the harmonic mean for Bayes factor comparisons of models)
    
             (Values are saved to the file primates.nex.lstat)
    
          Run   Arithmetic mean   Harmonic mean
          --------------------------------------
            1      -5719.74         -5739.95
            2      -5719.61         -5738.38
          --------------------------------------
          TOTAL    -5719.67         -5739.44
          --------------------------------------
    
    
          Model parameter summaries over the runs sampled in files
             "primates.nex.run1.p" and "primates.nex.run2.p":
             Summaries are based on a total of 302 samples from 2 runs.
             Each run produced 201 samples of which 151 samples were included.
             Parameter summaries saved to file "primates.nex.pstat".
          Overwriting file "primates.nex.pstat"
    
                                                95% HPD Interval
                                              --------------------
          Parameter      Mean      Variance     Lower       Upper       Median    min ESS*  avg ESS    PSRF+ 
          --*------------------------------------------------------------------------------------------------
          TL          3.085555    0.106790    2.391784    3.624876    3.089970*     14.95     32.48    1.003
          r(A<->C)    0.044625    0.000081    0.026277    0.059014    0.044874     13.46     23.45    1.007
          r(A<->G)    0.463943    0.002733    0.375781    0.558146    0.467120      4.14      8.48    0.998
          r(A<->T)    0.038287    0.000093    0.020818    0.055795    0.038043     61.70    106.35    1.005
          r(C<->G)    0.029229    0.000159    0.007271    0.049807    0.028128     53.32     58.41    1.090
    *      r(C<->T)    0.401640    0.001769    0.327182    0.469599    0.400749      4.89     17.66    1.002
          r(G<->T)    0.022275    0.000500    0.000011    0.060454    0.017545      7.87     15.02    1.044
          pi(A)       0.354934    0.000168    0.334242    0.385890    0.353917     30.54     35.53    1.003
    *      pi(C)       0.320598    0.000151    0.300353    0.345347    0.320076     10.76     13.80    0.997
          pi(G)       0.082188    0.000050    0.071056    0.097157    0.081435      9.58     12.63    0.998
          pi(T)       0.242281    0.000123    0.220879    0.264470    0.240832     40.83     65.15    1.004
          alpha       0.635318    0.043081    0.388900    1.061202    0.576031*     12.80     26.14    0.999
          pinvar      0.152020    0.006365    0.022122    0.297041    0.148084     21.88     27.41    1.003
          --------------------------------------------------------------------------------------------------
          * Convergence diagnostic (ESS = Estimated Sample Size); min and avg values
            correspond to minimal and average ESS among runs. 
            ESS value below 100 may indicate that the parameter is undersampled. 
          + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
            and Rubin, 1992) should approach 1.0 as runs converge.
    
    
       Summarizing trees in files "primates.nex.run1.t" and "primates.nex.run2.t"
       Using relative burnin ('relburnin=yes'), discarding the first 25 % of sampled trees
       Writing statistics to files primates.nex.<parts|tstat|vstat|trprobs|con>
       Examining first file ...
    *********
    
       Read a total of 402 trees in 2 files (sampling 302 of them)
          (Each file contained 201 trees of which 151 were sampled)
       Overwriting file "primates.nex.parts"
       Overwriting file "primates.nex.tstat"
       Overwriting file "primates.nex.vstat"
       Overwriting file "primates.nex.con.tre"
       Overwriting file "primates.nex.trprobs"
                                                                                       
       General explanation:                                                          
                                                                                       
       In an unrooted tree, a taxon bipartition (split) is specified by removing a   
       branch, thereby dividing the species into those to the left and those to the  
       right of the branch. Here, taxa to one side of the removed branch are denoted 
       '.' and those to the other side are denoted '*'. Specifically, the '.' symbol 
       is used for the taxa on the same side as the outgroup.                        
                                                                                       
       In a rooted or clock tree, the tree is rooted using the model and not by      
       reference to an outgroup. Each bipartition therefore corresponds to a clade,  
       that is, a group that includes all the descendants of a particular branch in  
       the tree.  Taxa that are included in each clade are denoted using '*', and    
       taxa that are not included are denoted using the '.' symbol.                  
                                                                                       
       The output first includes a key to all the bipartitions with frequency larger 
       or equual to (Minpartfreq) in at least one run. Minpartfreq is a parameter to 
       sumt command and currently it is set to 0.10.  This is followed by a table  
       with statistics for the informative bipartitions (those including at least    
       two taxa), sorted from highest to lowest probability. For each bipartition,   
       the table gives the number of times the partition or split was observed in all
       runs (#obs) and the posterior probability of the bipartition (Probab.), which 
       is the same as the split frequency. If several runs are summarized, this is   
       followed by the minimum split frequency (Min(s)), the maximum frequency       
       (Max(s)), and the standard deviation of frequencies (Stddev(s)) across runs.  
       The latter value should approach 0 for all bipartitions as MCMC runs converge.
                                                                                       
       This is followed by a table summarizing branch lengths, node heights (if a    
       clock model was used) and relaxed clock parameters (if a relaxed clock model  
       was used). The mean, variance, and 95 % credible interval are given for each 
       of these parameters. If several runs are summarized, the potential scale      
       reduction factor (PSRF) is also given; it should approach 1 as runs converge. 
       Node heights will take calibration points into account, if such points were   
       used in the analysis.                                                         
                                                                                     
       Note that Stddev may be unreliable if the partition is not present in all     
       runs (the last column indicates the number of runs that sampled the partition 
       if more than one run is summarized). The PSRF is not calculated at all if     
       the partition is not present in all runs.The PSRF is also sensitive to small  
       sample sizes and it should only be considered a rough guide to convergence    
       since some of the assumptions allowing one to interpret it as a true potential
       scale reduction factor are violated in MrBayes.                               
                                                                                     
       List of taxa in bipartitions:                                                 
                                                                                       
          1 -- Tarsius_syrichta
          2 -- Lemur_catta
          3 -- Homo_sapiens
          4 -- Pan
          5 -- Gorilla
          6 -- Pongo
          7 -- Hylobates
          8 -- Macaca_fuscata
          9 -- M_mulatta
         10 -- M_fascicularis
         11 -- M_sylvanus
         12 -- Saimiri_sciureus
    
       Key to taxon bipartitions (saved to file "primates.nex.parts"):
    
       ID -- Partition
       ------------------
        1 -- .***********
        2 -- .*..........
        3 -- ..*.........
        4 -- ...*........
        5 -- ....*.......
        6 -- .....*......
        7 -- ......*.....
        8 -- .......*....
        9 -- ........*...
       10 -- .........*..
       11 -- ..........*.
       12 -- ...........*
       13 -- ..**********
       14 -- .......**...
       15 -- ..***.......
       16 -- ..**........
       17 -- .......****.
       18 -- ..*****.....
       19 -- ..*********.
       20 -- .......***..
       21 -- ..****......
       ------------------
    
       Summary statistics for informative taxon bipartitions
          (saved to file "primates.nex.tstat"):
    
       ID   #obs    Probab.     Sd(s)+      Min(s)      Max(s)   Nruns 
       ----------------------------------------------------------------
       13   302    1.000000    0.000000    1.000000    1.000000    2
       14   302    1.000000    0.000000    1.000000    1.000000    2
       15   302    1.000000    0.000000    1.000000    1.000000    2
       16   302    1.000000    0.000000    1.000000    1.000000    2
       17   302    1.000000    0.000000    1.000000    1.000000    2
       18   302    1.000000    0.000000    1.000000    1.000000    2
       19   302    1.000000    0.000000    1.000000    1.000000    2
       20   301    0.996689    0.004683    0.993377    1.000000    2
       21   301    0.996689    0.004683    0.993377    1.000000    2
       ----------------------------------------------------------------
       + Convergence diagnostic (standard deviation of split frequencies)
         should approach 0.0 as runs converge.
    
    
       Summary statistics for branch and node parameters
          (saved to file "primates.nex.vstat"):
    
                                               95% HPD Interval
                                             --------------------
       Parameter      Mean       Variance     Lower       Upper       Median     PSRF+  Nruns
       -----------------------------------------------------------   Found one tree block in file "primates.nex.run1.t" with 201 trees in last block
    ---   Expecting the same number of trees in the last tree block of all files
    ----
       Tree reading status:
    
    ----   0      10      20      30      40      50      60      70      80      90     100
       v-------v-------v-------v-------v-------v-------v-------v-------v-------v-------v
       *----------------
       length[1]     0.513647    0.009474    0.355929    0.745019    0.505779    1.007    2
       length[2]     0.358469    0.004547    0.214182    0.477468    0.358865    0.998    2
    *   length[3]     0.052630    0.000166    0.033932    0.081204    0.049652    1.026    2
       length[4]     0.060389    0.000134    0.037880    0.080283    0.058846    0.999    2
       length[5]     0.059234    0.000216    0.031964    0.089096    0.058824*    1.006    2
       length[6]     0.149955    0.000584    0.105557    0.204468    0.148979    0.998    2
       length[7]     0.178891    0.001015    0.124323    0.242382    0.176846    1.004    2*
       length[8]     0.018251    0.000042    0.007738    0.030440    0.017492    1.000    2
       length[9]     0.023514    0.000055    0.010818    0.037358    0.022918    1.009    2
    *   length[10]    0.057602    0.000143    0.036232    0.080239    0.057312    1.001    2
       length[11]    0.073997    0.000411    0.035494    0.109720    0.074867    1.001    2
       length[12]  *  0.460928    0.006167    0.319299    0.612673    0.457111    0.999    2
       length[13]    0.292671    0.005399    0.170375    0.450329    0.285487    1.002    2
       length[14]    0.036525    0.000101    0.021322    0.059583    0.035773    1.003    2
    *   length[15]    0.087771    0.000548    0.047208    0.134095    0.084910    0.998    2
       length[16]    0.031343    0.000163    0.009393    0.056176    0.029770    1.001    2
    *   length[17]    0.271358    0.002986    0.183774    0.396243    0.266546    0.998    2
       length[18]    0.128498    0.001412    0.056749    0.198840    0.126113    1.026    2
       length[19]  *  0.123403    0.002179    0.039094    0.213598    0.124869    0.997    2
       length[20]    0.049751    0.000460    0.011570    0.089320    0.047178    0.998    2
       length[21]    0.057042    0.000450    0.018827    0.095637    0.055108    1.005    2*
       --------------------------------------------------------*------------------------------
       + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
         and Rubin, 1992) should approach 1.0 as runs converge. NA is reported when
         deviation of parameter values within all runs is 0 or when a parameter
         value (a branch length, for instance) is not sampled in all runs.
    
    
       Summary statistics for partitions with frequency >= 0.10 in at least one run:
           Average standard deviation of split frequencies = 0.001041
           Maximum standard deviation of split frequencies = 0.004683
           Average PSRF for parameter values (excluding NA and >10.0) = 1.004
           Maximum PSRF for parameter values = 1.026
    
    ***
       Clade credibility values:
    
       /---------------------------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |---------------------------------------------------------- Lemur_catta (2)
       |                                                                               
       |                                                 /-------- Homo_sapiens (3)
       |                                        /---100--+                             
       |                                        |        \-------- Pan (4)
       |                                /--100--+                                      
       |                                |       \----------------- Gorilla (5)
       |                        /--100--+                                              
       +                        |       \------------------------- Pongo (6)
       |                /--100--+                                                      
       |                |       \--------------------------------- Hylobates (7)
       |                |                                                              
       |                |                                /-------- Macaca_fuscata (8)
       |       /---100--+                       /---100--+                             
       |       |        |                       |        \-------- M_mulatta (9)
       |       |        |               /--100--+                                      
       |       |        |               |       \----------------- M_fascicularis (10)
       \--100--+        \------100------+                                              
               |                        \------------------------- M_sylvanus (11)
               |                                                                       
               \-------------------------------------------------- Saimiri_sciure~ (12)
                                                                                       
    *
       Phylogram (based on average branch lengths):
    
       /-------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |--------------------------- Lemur_catta (2)
       |                                                                               
       |                                                    /---- Homo_sapiens (3)
       |                                                  /-+                          
       |                                                  | \----- Pan (4)
       |                                            /-----+                            
       |                                            |     \----- Gorilla (5)
       |                                        /---+                                  
       +                                        |   \----------- Pongo (6)
       |                              /---------+                                      
       |                              |         \------------- Hylobates (7)
       |                              |                                                
       |                              |                         /-- Macaca_fuscata (8)
       |                     /--------+                       /-+                      
       |                     |        |                       | \-- M_mulatta (9)
       |                     |        |                   /---+                        
       |                     |        |                   |   \---- M_fascicularis (10)
       \---------------------+        \-------------------+                            
                             |                            \------ M_sylvanus (11)
                             |                                                         
                             \---------------------------------- Saimiri_sciure~ (12)
                                                                                       
       |--------------| 0.200 expected changes per site
    
                      *                                                      ***   Calculating tree probabilities...
    
    *   Credible sets of trees (3 trees sampled):
          99 % credible set contains 1 tree
    
       Terminating log output
       Exiting mrbayes block
       Reached end of file
    
       Tasks completed, exiting program because mode is noninteractive
       To return control to the command line after completion of file processing, 
       set mode to interactive with 'mb -i <filename>' (i is for interactive)
       or use 'set mode=interactive'
    
    *************************************************************
    
       Read a total of 402 trees in 2 files (sampling 302 of them)
          (Each file contained 201 trees of which 151 were sampled)
       Overwriting file "primates.nex.parts"
       Overwriting file "primates.nex.tstat"
       Overwriting file "primates.nex.vstat"
       Overwriting file "primates.nex.con.tre"
       Overwriting file "primates.nex.trprobs"
                                                                                       
       General explanation:                                                          
                                                                                       
       In an unrooted tree, a taxon bipartition (split) is specified by removing a   
       branch, thereby dividing the species into those to the left and those to the  
       right of the branch. Here, taxa to one side of the removed branch are denoted 
       '.' and those to the other side are denoted '*'. Specifically, the '.' symbol 
       is used for the taxa on the same side as the outgroup.                        
                                                                                       
       In a rooted or clock tree, the tree is rooted using the model and not by      
       reference to an outgroup. Each bipartition therefore corresponds to a clade,  
       that is, a group that includes all the descendants of a particular branch in  
       the tree.  Taxa that are included in each clade are denoted using '*', and    
       taxa that are not included are denoted using the '.' symbol.                  
                                                                                       
       The output first includes a key to all the bipartitions with frequency larger 
       or equual to (Minpartfreq) in at least one run. Minpartfreq is a parameter to 
       sumt command and currently it is set to 0.10.  This is followed by a table  
       with statistics for the informative bipartitions (those including at least    
       two taxa), sorted from highest to lowest probability. For each bipartition,   
       the table gives the number of times the partition or split was observed in all
       runs (#obs) and the posterior probability of the bipartition (Probab.), which 
       is the same as the split frequency. If several runs are summarized, this is   
       followed by the minimum split frequency (Min(s)), the maximum frequency       
       (Max(s)), and the standard deviation of frequencies (Stddev(s)) across runs.  
       The latter value should approach 0 for all bipartitions as MCMC runs converge.
                                                                                       
       This is followed by a table summarizing branch lengths, node heights (if a    
       clock model was used) and relaxed clock parameters (if a relaxed clock model  
       was used). The mean, variance, and 95 % credible interval are given for each 
       of these parameters. If several runs are summarized, the potential scale      
       reduction factor (PSRF) is also given; it should approach 1 as runs converge. 
       Node heights will take calibration points into account, if such points were   
       used in the analysis.                                                         
                                                                                     
       Note that Stddev may be unreliable if the partition is not present in all     
       runs (the last column indicates the number of runs that sampled the partition 
       if more than one run is summarized). The PSRF is not calculated at all if     
       the partition is not present in all runs.The PSRF is also sensitive to small  
       sample sizes and it should only be considered a rough guide to convergence    
       since some of the assumptions allowing one to interpret it as a true potential
       scale reduction factor are violated in MrBayes.                               
                                                                                     
       List of taxa in bipartitions:                                                 
                                                                                       
          1 -- Tarsius_syrichta
          2 -- Lemur_catta
          3 -- Homo_sapiens
          4 -- Pan
          5 -- Gorilla
          6 -- Pongo
          7 -- Hylobates
          8 -- Macaca_fuscata
          9 -- M_mulatta
         10 -- M_fascicularis
         11 -- M_sylvanus
         12 -- Saimiri_sciureus
    
       Key to taxon bipartitions (saved to file "primates.nex.parts"):
    
       ID -- Partition
       ------------------
        1 -- .***********
        2 -- .*..........
        3 -- ..*.........
        4 -- ...*........
        5 -- ....*.......
        6 -- .....*......
        7 -- ......*.....
        8 -- .......*....
        9 -- ........*...
       10 -- .........*..
       11 -- ..........*.
       12 -- ...........*
       13 -- ..**********
       14 -- .......**...
       15 -- ..***.......
       16 -- ..**........
       17 -- .......****.
       18 -- ..*****.....
       19 -- ..*********.
       20 -- .......***..
       21 -- ..****......
       ------------------
    
       Summary statistics for informative taxon bipartitions
          (saved to file "primates.nex.tstat"):
    
       ID   #obs    Probab.     Sd(s)+      Min(s)      Max(s)   Nruns 
       ----------------------------------------------------------------
       13   302    1.000000    0.000000    1.000000    1.000000    2
       14   302    1.000000    0.000000    1.000000    1.000000    2
       15   302    1.000000    0.000000    1.000000    1.000000    2
       16   302    1.000000    0.000000    1.000000    1.000000    2
       17   302    1.000000    0.000000    1.000000    1.000000    2
       18   302    1.000000    0.000000    1.000000    1.000000    2
       19   302    1.000000    0.000000    1.000000    1.000000    2
       20   301    0.996689    0.004683    0.993377    1.000000    2
       21   301    0.996689    0.004683    0.993377    1.000000    2
       ----------------------------------------------------------------
       + Convergence diagnostic (standard deviation of split frequencies)
         should approach 0.0 as runs converge.
    
    
       Summary statistics for branch and node parameters
          (saved to file "primates.nex.vstat"):
    
                                               95% HPD Interval
                                             --------------------
       Parameter      Mean       Variance     Lower       Upper       Median     PSRF+  Nruns
       --------------------------------------------------------------------------------------
       length[1]     0.513647    0.009474    0.355929    0.745019    0.505779    1.007    2
       length[2]     0.358469    0.004547    0.214182    0.477468    0.358865    0.998    2
       length[3]     0.052630    0.000166    0.033932    0.081204    0.049652    1.026    2
       length[4]     0.060389    0.000134    0.037880    0.080283    0.058846    0.999    2
       length[5]     0.059234    0.000216    0.031964    0.089096    0.058824    1.006    2
       length[6]     0.149955    0.000584    0.105557    0.204468    0.148979    0.998    2
       length[7]     0.178891    0.001015    0.124323    0.242382    0.176846    1.004    2
       length[8]     0.018251    0.000042    0.007738    0.030440    0.017492    1.000    2
       length[9]     0.023514    0.000055    0.010818    0.037358    0.022918    1.009    2
       length[10]    0.057602    0.000143    0.036232    0.080239    0.057312    1.001    2
       length[11]    0.073997    0.000411    0.035494    0.109720    0.074867    1.001    2
       length[12]    0.460928    0.006167    0.319299    0.612673    0.457111    0.999    2
       length[13]    0.292671    0.005399    0.170375    0.450329    0.285487    1.002    2
       length[14]    0.036525    0.000101    0.021322    0.059583    0.035773    1.003    2
       length[15]    0.087771    0.000548    0.047208    0.134095    0.084910    0.998    2
       length[16]    0.031343    0.000163    0.009393    0.056176    0.029770    1.001    2
       length[17]    0.271358    0.002986    0.183774    0.396243    0.266546    0.998    2
       length[18]    0.128498    0.001412    0.056749    0.198840    0.126113    1.026    2
       length[19]    0.123403    0.002179    0.039094    0.213598    0.124869    0.997    2
       length[20]    0.049751    0.000460    0.011570    0.089320    0.047178    0.998    2
       length[21]    0.057042    0.000450    0.018827    0.095637    0.055108    1.005    2
       --------------------------------------------------------------------------------------
       + Convergence diagnostic (PSRF = Potential Scale Reduction Factor; Gelman
         and Rubin, 1992) should approach 1.0 as runs converge. NA is reported when
         deviation of parameter values within all runs is 0 or when a parameter
         value (a branch length, for instance) is not sampled in all runs.
    
    
       Summary statistics for partitions with frequency >= 0.10 in at least one run:
           Average standard deviation of split frequencies = 0.001041
           Maximum standard deviation of split frequencies = 0.004683
           Average PSRF for parameter values (excluding NA and >10.0) = 1.004
           Maximum PSRF for parameter values = 1.026
    
    
       Clade credibility values:
    
       /---------------------------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |---------------------------------------------------------- Lemur_catta (2)
       |                                                                               
       |                                                 /-------- Homo_sapiens (3)
       |                                        /---100--+                             
       |                                        |        \-------- Pan (4)
       |                                /--100--+                                      
       |                                |       \----------------- Gorilla (5)
       |                        /--100--+                                              
       +                        |       \------------------------- Pongo (6)
       |                /--100--+                                                      
       |                |       \--------------------------------- Hylobates (7)
       |                |                                                              
       |                |                                /-------- Macaca_fuscata (8)
       |       /---100--+                       /---100--+                             
       |       |        |                       |        \-------- M_mulatta (9)
       |       |        |               /--100--+                                      
       |       |        |               |       \----------------- M_fascicularis (10)
       \--100--+        \------100------+                                              
               |                        \------------------------- M_sylvanus (11)
               |                                                                       
               \-------------------------------------------------- Saimiri_sciure~ (12)
                                                                                       
    
       Phylogram (based on average branch lengths):
    
       /-------------------------------------- Tarsius_syrichta (1)
       |                                                                               
       |--------------------------- Lemur_catta (2)
       |                                                                               
       |                                                    /---- Homo_sapiens (3)
       |                                                  /-+                          
       |                                                  | \----- Pan (4)
       |                                            /-----+                            
       |                                            |     \----- Gorilla (5)
       |                                        /---+                                  
       +                                        |   \----------- Pongo (6)
       |                              /---------+                                      
       |                              |         \------------- Hylobates (7)
       |                              |                                                
       |                              |                         /-- Macaca_fuscata (8)
       |                     /--------+                       /-+                      
       |                     |        |                       | \-- M_mulatta (9)
       |                     |        |                   /---+                        
       |                     |        |                   |   \---- M_fascicularis (10)
       \---------------------+        \-------------------+                            
                             |                            \------ M_sylvanus (11)
                             |                                                         
                             \---------------------------------- Saimiri_sciure~ (12)
                                                                                       
       |--------------| 0.200 expected changes per site
    
                                                                               Calculating tree probabilities...
    
       Credible sets of trees (3 trees sampled):
          99 % credible set contains 1 tree
    
       Terminating log output
       Exiting mrbayes block
       Reached end of file
    
       Tasks completed, exiting program because mode is noninteractive
       To return control to the command line after completion of file processing, 
       set mode to interactive with 'mb -i <filename>' (i is for interactive)
       or use 'set mode=interactive'
    
    
    real	0m33.499s
    user	2m1.980s
    sys	0m1.879s



```bash
cd ~/
pwd
```

    /home/rcastro



```bash

```
