# LABORATORIO DE GIT

Este laboratorio tiene como objetivo practicar los comandos básicos de Git.

## 1. Crear un repositorio en local

Entro a la carpeta donde voy a crear el repositorio:
```console
June@DESKTOP-4ABLAGV MINGW64 ~
$ cd repositorios
```
Creo la carpeta:
```console
June@DESKTOP-4ABLAGV MINGW64 ~/repositorios
$ mkdir lab1
```
Entro a la carpeta:
```console
June@DESKTOP-4ABLAGV MINGW64 ~/repositorios
$ cd lab1
```
Incializo el repositorio:
```console
June@DESKTOP-4ABLAGV MINGW64 ~/repositorios/lab1
$ git init
Initialized empty Git repository in C:/Users/June/Repositorios/lab1/.git/
```

## 2. Subir el repositorio a GitHub

Crea un nuevo repositorio en GitHub.

https://github.com/junearranz/lab1.git

SSH: git@github.com:junearranz/lab1.git

Añado un archivo README.md en VS.Code.


```console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (master)
$ git init
Reinitialized existing Git repository in C:/Users/June/Repositorios/lab1/.git/
```
```console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (master)
$ git add .
```
```console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (master)
$ git commit -m "Primer commit"
[master (root-commit) 997bd7a] Primer commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
```
``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (master)
$ git remote add origin git@github.com:junearranz/lab1.git
```
```console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (master)
$ git push origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 212 bytes | 212.00 KiB/s, done.        
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)       
To github.com:junearranz/lab1.git
 * [new branch]      master -> master
 ```
 
 VS Code me ha creado por defecto la rama master, y GitHub también, cambio en GitHub el nombre de la rama 
 principal a main, y luego lo modifico en VS Code:
 
 ``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (master)
$ git branch -m master main

June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$
````

## 3. Hacer un commit y un push

Crea un archivo en la carpeta del repositorio. Creamos index.html en VSCode.

Añade el archivo al staging.
Crea un commit con un mensaje descriptivo.
Sube los cambios al repositorio en GitHub.

```console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git add .
```
```console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git commit -m "añadimos archivo index.html"
[main 3e4b83b] añadimos archivo index.html
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 index.html
```
```console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git push origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 260 bytes | 260.00 KiB/s, done.        
Total 2 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)       
remote: 
remote: Create a pull request for 'main' on GitHub by visiting:     
remote:      https://github.com/junearranz/lab1/pull/new/main       
remote:
To github.com:junearranz/lab1.git
 * [new branch]      main -> main
```

## 4. Crear una rama

Reviso el estado del proyecto:

``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git status
On branch main
nothing to commit, working tree clean
```
Crea una rama nueva llamada "development".

``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git branch development
```

Cambia a la nueva rama.
``` console

June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git checkout development
Switched to branch 'development'

June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (development)      
$
```

Realiza algunos cambios en el archivo que creaste. Añado un título al archivo .html

Añade y haz un commit con los cambios en la rama "development".
``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (development)      
$ git add .

June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (development)      
$ git commit -m "cambiamos el título del .html"
[development 7681dc9] cambiamos el título del .html
 1 file changed, 10 insertions(+)
```
Sube los cambios a Github.
``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (development)      
$ git push origin development
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 465 bytes | 465.00 KiB/s, done.        
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)       
remote: 
remote: Create a pull request for 'development' on GitHub by visiting:
remote:      https://github.com/junearranz/lab1/pull/new/developmen 
remote:
To github.com:junearranz/lab1.git
 * [new branch]      development -> development
```

## 5. Hacer un merge

Vuelve a la rama "main".
``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (development)
$ git checkout main
Switched to branch 'main'

June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ 
```

Haz un merge de la rama "development" a la rama "main".
``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git merge development
Updating 3e4b83b..7681dc9
Fast-forward
 index.html | 10 ++++++++++
 1 file changed, 10 insertions(+)
```
``` console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git status
On branch main
nothing to commit, working tree clean
```

Haz un push de los cambios al repositorio en GitHub.
```console
June@DESKTOP-4ABLAGV MINGW64 ~/Repositorios/lab1 (main)
$ git push origin main
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To github.com:junearranz/lab1.git
   3e4b83b..7681dc9  main -> main
```


## Autores ✨

* **June Arranz** - [junearranz](https://github.com/junearranz)
