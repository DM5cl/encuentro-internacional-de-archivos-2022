## ReadMe

Esta es la página del proyecto de edición del libro que recoge las ponencias dadas en el marco del primer congreso de archivos latinoamericanos. 

El siguiente tutorial fue diseñado para clonar el proyecto en un entorno local y reproducir los pasos de una configuración mínima del entorno de producción, desde la instalación de dependencias hasta la implementación de los distintos formatos de salida (web, epub, pdf, azw3).

Para editar el texto, se puede utilizar cualquier editor de texto, aunque es mejor utilizar uh entorno de desarrollo (como VS Code o Atom. 

## Configuración local

### 1. Instalar dependencias:

#### 1.1 Git
ir a [página de descargas](https://git-scm.com/downloads) y seguir las instrucciones según el sistema operativo 

#### 1.2 Node 
Descargar e instalar la versión LTS [en esta página](https://nodejs.org/download/release/v14.18.1/).

#### 1.3 Quire
Descargar e instalar Quire. Instrucciones en [ésta página](https://quire.getty.edu/docs-v0/install-uninstall/#macos-installation)

#### 1.4 PrinceXML
Descargar princeXML en [ésta página]([http://www.princexml.com/download/](http://www.princexml.com/download/))

#### 1.5 Pandoc
Descargar [aquí](https://pandoc.org/installing.html)

#### 1.6 Crear cuenta en Github.com
Ir [aquí](https://github.com)

### 2. Configuración del repositorio local

Una vez instalado y configurado el software,será necesario descargar los repositorios que contienen los archivos del proyecto:

1. Navegar con el terminal a la ubicación deseada en el computador y clonar el repositorio remoto con: 
```git clone https://github.com/lavoraginelab/encuentro_internacional_de_archivos.git```
2. Una vez el repositorio se halla descargado, ir a la carpeta:
   ```cd encuentro_internacional_de_archivos```
3. E iniciar git:
   ```git init```
4. A continuación, poner todos los archivos bajo control de versiones:
   ```git add .```
5. Y confirmar los cambios:
   ```git commit -m "configurar repo"```
### 3.  crear repositorio en github y sincronizar con repositorio local
1. Crear una cuenta en GitHub y una vez creada, crear una organización (en este caso, para albergar el proyecto). 
2. Crear repositorio :
   -> `new` 
   -> llenar el campo ‘Repository name’ (digamos  ‘encuentro_internacional_de_archivos_de_arte’)
   -> `create repository`
3. Se abrirá la siguiente pantalla:
 ![[github_config.png]]
4. (seguimos las instrucciones marcadas en rojo  (`pushing a local repository from command line`):
5.  Ir al terminal abierto en la carpeta `encuentro_internacional_de_archivos` ) y escribir las siguientes instrucciones: 
6. Para sincronizar el repositorio local y el repositorio remoto: `git remote add origin https://github.com/nastarovia/encuentro_internacional_de_archivos_de_arte.git`
7. Y para subir el repositorio local a github: `git push -u origin main`
8. De aquí en adelante, cada vez que se corrija algo en el archivo la secuencia de comandos debería ser:
	1. `git add .`  > para añadir los cambios a git
	2. `git commit -m "nuevo cambio" ` > para confirmar 
	3. `git push` > para subir los cambios a GitHub

### 4. Actualizar archivos y generar el sitio actualizado, incluyendo el PDF, y los archivos de libro electrónico:

1. Nos aseguramos de que quire está instalado y funcionando: 
   `quire -V` (la salida del comando debería ser: `v0.20.2`)
2. Instalamos y actualizamos dependencias:
   `quire install`
3. generamos los archivos de libro electrónico y el sitio web y lo subimos a Github
   `bin/deploy.sh`
4. Una vez github pages termine de procesar los archivos, el sitio web debería estar disponible en: `https://<nombre-de-la-organizacion>.github.io/encuentro_internacional_de_archivos_de_arte/`

### Notas

#### 1
Un problema común es el tamaño de los archivos. Github sólo admite archivos de hasta 100mb. Si Github rechazara la conexión, hay dos formas de solucionarlo:

1. Utilizar [Git LFS](https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage) (Large File Storage)
2. Subir los archivos de descargas directamente a GitHub previamente optimizados (hay una serie de herramientas online que optimizan archivos pdf o azw)

#### 2
La versión de Quire en la que se basa esta guía es la v0.20.2


