# Respuestas de la practica del curso de git. #

*Lo olvide y supongo que es entrega fallida, pero por si acaso.*

## ¿Qué comando utilizaste en el paso 11? ¿Por qué? ##
Utilicé el siguiente comando:

```
$ git reset --hard HEAD~1
HEAD is now at 3ccd99f Paso 4 - Mover fichero git-nuestro.md a repositorio
```
Utilice este comando por que mueve el puntero HEAD al commit anterior y por tanto deshace el último commit.


## ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué? ##
Utilice el comando `$ git commit -m "Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.`.


## El merge del paso 13, ¿Causó algún conflicto? ¿Por qué? ##
No, en mi caso no hubo conflicto

## El merge del paso 19, ¿Causó algún conflicto? ¿Por qué? ##
Si, hubo conflicto.

```
$ git merge htmlify
Auto-merging git-nuestro.md
CONFLICT (content): Merge conflict in git-nuestro.md
Automatic merge failed; fix conflicts and then commit the result.
```

En este caso, la rázón que se vio cuando abrimos el archivo es que la misma linea del fichero tenía versiones diferentes entre las ramas styled y htmlify. Nos quedamos con los cambios de la versión styled.


## El merge del paso 21, ¿Causó algún conflicto? ¿Por qué? ##
No, no tenía ningun conflicto. Esto es así por que el fichero de la rama styled no tenía diferncias con el de la rama main del que provénia.


## ¿Qué comando o comandos utilizaste en el paso 25? ##
Utilicé los siguientes comandos:

```
git log --graph
git log --graph --decorate --pretty=oneline

```

## El merge del paso 26, ¿Podría ser fast forward? ¿Por qué? ##
En mi opinión podría serlo, por que proviene del branch main, y podría haberse seguido de manera lineal desde el main. Es mas que nada una evolución del branch main.


## ¿Qué comando o comandos utilizaste en el paso 27? ##
Utilice los siguientes comandos:

```git reset HEAD~1```

Para que pudiera conservar los cambios realizados en el working copy, ya que la opción hard, destruiría los cambios.


## ¿Qué comando o comandos utilizaste en el paso 28? ##
Al tener que descartar los cambios anteriores, utilice la opción para restaurar el fichero al estado anterior son title.

```git restore git-nuestro.md```


## ¿Qué comando o comandos utilizaste en el paso 29? ##
```git branch -D title```, ya que al descartar los cambios, el merge no se había completado correctamente y tenía que forzar el borrado de la rama.


## ¿Qué comando o comandos utilizaste en el paso 30? ##
Utilice los siguientes comandos:

```$ git reset --hard  HEAD@{4}```
```$ cat git-nuestro.md```
```$ git reflog```
```$ cat git-nuestro.md```
```$ vi git-nuestro.md```
```$ git branch title```
```$ git checkout title```
```$ cat git-nuestro.md```
```$ git status```
```$ git commit -m "Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main."```
```$ git reflog```
```$ git checkout mainv```
```$ git merge --no-ff title```
```$ git reflog```

## ¿Qué comando o comandos usaste en el paso 32? ##
Utilice los siguientes comandos:

```$ git reflog```
```$ git checkout 9725b1c```
```$ cat git-nuestro.md```



## ¿Qué comando o comandos usaste en el punto 33? ##
Utilice los siguientes comandos:

```$ git reflog```: Para ver la información de las acciones del git

```$ git checkout  HEAD@{5}```: Para moverme al paso en el que habíamos puesto el titulo
```$ git status```



## Apendice - Salida completa de la práctica ##
He dejado en el fichero logOK-ejercicio1.txt la salida de comandos realizada por si hubierá alguna duda o problema.
