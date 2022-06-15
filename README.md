# LinkedIn scraping

Este código esta hecho para extraer el número de resultados de serie de busquedas de vacantes de trabajo en LinkedIn. El repositorio original es de [Luke Barousse](https://github.com/lukebarousse/Job_Analysis) pero tenia algunos problemas al correrse y fue adaptado para traer en especifico el campo del "Número de resultados" para cada busqueda en LinkedIn.

Este repositorio es el utilizado para obtener los resultados en este [video de Youtube](https://www.youtube.com/watch?v=_VRO7JUEEKg) que publiqué.


# Aviso

Aviso: Hacer webscraping de LinkedIn sin su permiso está prohibido y pueden bloquear tu usuario si se detectan demasiados llamados a LinkedIn en un periodo de tiempo corto.

[Política de LinkedIn](https://www.linkedin.com/robots.txt)

# Funcionamiento del código
El Jupyter notebook [LinkedIn.ipynb](./LinkedIn.ipynb) tiene dos celdas las cuales se encargan de recibir una lista de busquedas de vacantes laborales  y paises a realizar en LinkedIn. Con Selenium se ingresa a tu perfil de LinkedIn y genera una busqueda por cada palabra clave y pais que se indicó. 
Guarda la información en un archivo csv que tiene un registro por cada combinación de pais/busqueda.


# Requerimientos
* Descargar los drivers de Chrome correspondientes a la version de Google Chrome que tienes en el sistema
* Crear un archivo llamado .env con tu usuario y contraseña de LinkedIn para que el robot pueda ingresar
* Tener instalado todas las paqueterias del requirements.txt

# Pasos
## Instalar todas las paqueterias requeridas
```
pip install -r requirements.txt
```
## Crear archivo llamado .env el cual contenga usuario y contraseña de perfil de LinkedIn
```
LINKEDIN_USERNAME=email.address@mail.com
LINKEDIN_PASSWORD=password
```
## Identificar la version de chrome driver que necesitas 
* Dentro de Chrome obtener la versión de Chrome *Menú-Ajustes-Sobre Chrome*
* Descargar ek chromedriver que corresponde a la version de Chrome instalada en [esta liga](https://chromedriver.chromium.org/downloads)
* Colocar el driver en el directorio raiz de este repo

## Realizar ajustes de paises y palabras a utilizar en la busqueda 
Las variables a modificar son las siguientes:
```
search_keywords # Lista de busquedas a realizar

search_location # Diccionario con lista de paises a realizar la busqueda, esas claves se pueden obtener haciendo una busqueda en Linkedin para un pais y viendo la URL para la clave

search_remote # busca vacantes que sean remoto si es true

```
## Correr todas las celdas dentro del archivo principal [LinkedIn.ipynb](LinkedIn.ipynb) 
Al terminar el código se tendra un archivo csv en la carpeta de output