# Estadística bayesiana con PyMC

Este repositorio contiene una serie de Jupyter _notebooks_ que sirven para aprender sobre estadística bayesiana utilizando PyMC. Aunque el material cubre algunos conceptos básicos de estadística bayesiana, se asume que los lectores ya tienen un conocimiento previo, al menos básico, de esta área. No es necesario tener experiencia previa con PyMC ni con otras librerías relacionadas, como PyTensor, ArviZ, o xarray.

Bajo la carpeta `notebooks` se puede encontrar el siguiente material:

* `00_repaso_bayes.ipynb`: Es un repaso de conceptos elementales de estadística bayesiana que no hace uso de PyMC.
* `01_introduccion_pymc.ipynb`: Muestra la resolución paso a paso de problemas de inferencia básicos utilizando PyMC.
* `02_regresion_simple.ipynb`: Uso de PyMC para modelos de regresión con un predictor.
* `03_regresion_multiple.ipynb`: Uso de PyMC para modelos de regresión con más de un predictor.
* `04_siguientes_pasos.ipynb`: Contiene una serie de recursos que son útiles para continuar aprendiendo.

En todas las _notebooks_ se encuentran ejercicios que permiten poner en práctica los conceptos aprendidos.  

## Cómo usar el material

### Google Colab

Simplemente copiarse el material en una carpeta de Google Drive y trabajar con las notebooks usando Google Colab. Al principio de las _notebooks_ hay una celda de código que se debe correr para instalar una versión más nueva de PyMC que la que se encuentra disponible por defecto. Los conjuntos de datos pueden ser leídos localmente, para lo cuál hay que subirlos a Colab, o bien se pueden leer directamente desde GitHub. Esto se controla con la variable `local`. Por ejemplo, en la _notebook_ `02_regresion_simple.ipynb` se encuentra:

```python
local = True
if local:
    url_heights = "../datos/heights.txt"
else:
    url_heights = "https://raw.githubusercontent.com/tomicapretto/introduccion_pymc/main/datos/heights.txt"

df_heights = pd.read_table(url_heights, sep=" ")
```

Cuando `local` sea `True`, los datos se leerán localmente desde la ruta que indiquemos. Cuando `local` sea `False`, los datos se leerán directamente desde GitHub.

### Localmente

Para usar este material localmente se recomienda utilizar el ambiente de Conda que se define en `environment.yml`, llamado `pymc-env`. Para crear el ambiente hay que [tener instalado Anaconda](https://docs.anaconda.com/anaconda/install/), y luego ejecutar lo siguiente en una terminal:

```bash
conda env create -f environment.yml
```

Para que la creación del ambiente sea más rápida se puede utilizar [Mamba](https://mamba.readthedocs.io/en/latest/index.html). Para eso:

```bash
conda install mamba                  # instalar mamba 
mamba env create -f environment.yml  # crear ambiente usando mamba
```

Una vez creado el ambiente, se puede activar ejecutando:

```bash
conda activate pymc-env
```

Luego se puede abrir Jupyter Notebook mediante la terminal, ejecutando `jupyter notebook,` o se puede usar un entorno como Visual Studio Code que trabaja con ambientes de Conda.

[Este video](https://www.youtube.com/watch?v=85lD7o0BGVs) explica como instalar Anaconda y Visual Studio Code en Windows y puede resultar útil.

## Agradecimientos

Este material existe gracias a aquellos que dedican al menos parte de su tiempo al desarrollo de proyectos de código abierto como PyMC y ArviZ. También se agradece a Osvaldo Martin y Josefina Lacasa por comentarios que hicieron en versiones preliminares del tutorial, y a Nacho Evangelista por todo lo que desarrollamos en conjunto para nuestro curso en la Universidad Nacional de Rosario, que fue una valiosa fuente de inspiración, ejemplos y ejercicios. Finalmente, se agradece a la comunidad de [Bayes Plurinacional](https://bayesplurinacional.org/), que ha sido fuente de motivación para dedicarle tiempo al desarrollo de este repositorio.