# Log del ejercicio 1

## Paso 1 - Crear un repositorio en GitHub y clónalo en tu equipo
```
$ git clone https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git
Cloning into 'Pract-GIT-IA-3_M.A.Ferrero'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.
```

## Paso 2 - Crear un archivo git-nuestro.md con el contenido.
```
$ vi git-nuestro.md
$ cat git-nuestro.md
Git nuestro que estas en los repos
Comprimidos sean tus commits
Venga a nosotros tu log
En el local como en el remote
Danos hoy nuestro pull de cada día
Perdona nuestros conflictos
Como también perdonamos los de otros geeks
No nos dejes caer en detached HEAD
y líbranos de SVN
git commit--amend

```

## Paso 3 - Añadir git-nuestro.md al staging area
```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        git-nuestro.md

nothing added to commit but untracked files present (use "git add" to track)

$ git add git-nuestro.md
warning: in the working copy of 'git-nuestro.md', LF will be replaced by CRLF the next time Git touches it

```

## Paso 4 - Mover lo que hay en el staging area al repositorio
```
$ git commit -m "Paso 4 - Mover fichero git-nuestro.md a repositorio"
[main 2a133cc] Paso 4 - Mover fichero git-nuestro.md a repositorio
 1 file changed, 10 insertions(+)
 create mode 100644 git-nuestro.md

```

## Paso 5 - Crear una rama llamada "styled"
```
$ git reflog
9725b1c (HEAD -> main) HEAD@{0}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{1}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

$ git branch styled

$ git branch
* main
  styled

```

## Paso 6 - Listar las ramas que ha en el repositorio
```
$ git branch
* main
  styled

```

## Paso 7 - Moverse a la rama styled
```
$ git checkout styled
Switched to branch 'styled'

$ git reflog
9725b1c (HEAD -> styled, main) HEAD@{0}: checkout: moving from main to styled
9725b1c (HEAD -> styled, main) HEAD@{1}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{2}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

```

## Paso 8 - Comprobar que se esta en la rama correcta
```
$ git status
On branch styled
nothing to commit, working tree clean

$ git branch
  main
* styled

```

## Paso 9 - Modificar el archivo git-nuestro.md

```
$ vi git-nuestro.md

$ cat git-nuestro.md
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`


$ git status
On branch styled
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        git-nuestro

nothing added to commit but untracked files present (use "git add" to track)

```
## Paso 10 - Añadir los cambios al staging area y luego pasarlos al repositorio

```
$ git add git-nuestro.md
warning: in the working copy of 'git-nuestro.md', LF will be replaced by CRLF the next time Git touches it

vaeli@Elistan-1 MINGW64 ~/Documents/IA-Keepcoding/IA-Modulos/Curso_GIT/Pract-GIT-IA-3_M.A.Ferrero (styled)
$ git commit -m "Paso 10 - Mover fichero git-nuestro.md a repositorio"
[styled f048e59] Paso 10 - Mover fichero git-nuestro.md a repositorio
 1 file changed, 9 insertions(+), 9 deletions(-)

$ git reflog
f048e59 (HEAD -> styled) HEAD@{0}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (main) HEAD@{1}: checkout: moving from main to styled
9725b1c (main) HEAD@{2}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{3}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

```

## Paso Paso 11 -  Deshacer el último commit (perdiendo los cambios realizados en el working copy)

```
$ cat git-nuestro.md
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`

$ git reset --hard HEAD~1
HEAD is now at 9725b1c Paso 4 - Mover fichero git-nuestro.md a repositorio

$ cat git-nuestro.md
Git nuestro que estas en los repos
Comprimidos sean tus commits
Venga a nosotros tu log
En el local como en el remote
Danos hoy nuestro pull de cada día
Perdona nuestros conflictos
Como también perdonamos los de otros geeks
No nos dejes caer en detached HEAD
y líbranos de SVN
git commit--amend

$ git reflog
9725b1c (HEAD -> styled, main) HEAD@{0}: reset: moving to HEAD~1
f048e59 HEAD@{1}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (HEAD -> styled, main) HEAD@{2}: checkout: moving from main to styled
9725b1c (HEAD -> styled, main) HEAD@{3}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{4}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


```

## Paso 12 -  Rehacer el último commit (el que acabamos de deshacer)
```
$vi git-nuestro.md

$ git status
On branch styled
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")

$ git add git-nuestro.md

$ git commit -m "Paso 12 - Realizar cambio en git-nuestro.md y realizar commit."
[styled 3b77153] Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
 1 file changed, 9 insertions(+), 9 deletions(-)

$ git reflog
3b77153 (HEAD -> styled) HEAD@{0}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (main) HEAD@{1}: reset: moving to HEAD~1
f048e59 HEAD@{2}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (main) HEAD@{3}: checkout: moving from main to styled
9725b1c (main) HEAD@{4}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{5}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


```

## Paso 13 -  Hacer un merge con 'main' (styled absorve a main)
```
$ git reflog
3b77153 (HEAD -> styled) HEAD@{0}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (main) HEAD@{1}: reset: moving to HEAD~1
f048e59 HEAD@{2}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (main) HEAD@{3}: checkout: moving from main to styled
9725b1c (main) HEAD@{4}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{5}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

$ git merge main

$ git reflog
3b77153 (HEAD -> styled) HEAD@{0}: checkout: moving from main to styled
9725b1c (main) HEAD@{1}: checkout: moving from styled to main
3b77153 (HEAD -> styled) HEAD@{2}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (main) HEAD@{3}: reset: moving to HEAD~1
f048e59 HEAD@{4}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (main) HEAD@{5}: checkout: moving from main to styled
9725b1c (main) HEAD@{6}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{7}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

```

## Paso 14 - Volver a la rama main 
```
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)


$ cat git-nuestro.md
Git nuestro que estas en los repos
Comprimidos sean tus commits
Venga a nosotros tu log
En el local como en el remote
Danos hoy nuestro pull de cada día
Perdona nuestros conflictos
Como también perdonamos los de otros geeks
No nos dejes caer en detached HEAD
y líbranos de SVN
git commit--amend

```

## Paso 15 - Crear una nueva rama llamada "htmlify" 
```
$ git branch htmlify

$ git branch
  htmlify
* main
  styled


```

## Paso 16 - Cambiar a la rama htmlify
```
$ git checkout htmlify
Switched to branch 'htmlify'

```

## Paso 17 - Modificar el archivo git-nuestro.md 
```
$ vi git-nuestro.md

$ cat git-nuestro.md
<p><em>Git</em> nuestro que estas en los repos<br />
Comprimidos sean tus <em>commits</em><br />
Venga a nosotros tu <em>log</em><br />
En el local como en el <em>remote</em><br />
Danos hoy nuestro <em>pull</em> de cada día<br />
Perdona nuestros <em>conflictos</em><br />
Como también perdonamos los de otros geeks<br />
No nos dejes caer en <em>detached HEAD</em><br />
y líbranos de <em>SVN</em><br />
<code>git commit--amend</code></p>

```

## Paso 18 - Hacer un commit

```
$ git status
On branch htmlify
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")

$ git add git-nuestro.md

$ git commit -m "Paso 18 - Commit en rama htmlify de git-nuestro.md"
[htmlify b13ba77] Paso 18 - Commit en rama htmlify de git-nuestro.md
 1 file changed, 10 insertions(+), 10 deletions(-)


$ git reflog
b13ba77 (HEAD -> htmlify) HEAD@{0}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c (main) HEAD@{1}: checkout: moving from main to htmlify
9725b1c (main) HEAD@{2}: checkout: moving from styled to main
3b77153 (styled) HEAD@{3}: checkout: moving from main to styled
9725b1c (main) HEAD@{4}: checkout: moving from styled to main
3b77153 (styled) HEAD@{5}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (main) HEAD@{6}: reset: moving to HEAD~1
f048e59 HEAD@{7}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (main) HEAD@{8}: checkout: moving from main to styled
9725b1c (main) HEAD@{9}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{10}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


```

## Paso 19 - Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)
```
$ git checkout styled
Switched to branch 'styled'

$ git merge htmlify
Auto-merging git-nuestro.md
CONFLICT (content): Merge conflict in git-nuestro.md
Automatic merge failed; fix conflicts and then commit the result.

```

## Paso 20 - Si hay conflictos, deberemos reolverlos quedandonos con el contenido de la rama "styled"
```
$ cat git-nuestro.md
<<<<<<< HEAD
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`
=======
<p><em>Git</em> nuestro que estas en los repos<br />
Comprimidos sean tus <em>commits</em><br />
Venga a nosotros tu <em>log</em><br />
En el local como en el <em>remote</em><br />
Danos hoy nuestro <em>pull</em> de cada día<br />
Perdona nuestros <em>conflictos</em><br />
Como también perdonamos los de otros geeks<br />
No nos dejes caer en <em>detached HEAD</em><br />
y líbranos de <em>SVN</em><br />
<code>git commit--amend</code></p>
>>>>>>> htmlify


vaeli@Elistan-1 MINGW64 ~/Documents/IA-Keepcoding/IA-Modulos/Curso_GIT/Pract-GIT-IA-3_M.A.Ferrero (styled|MERGING)
$ vi git-nuestro.md

$ cat git-nuestro.md
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`


$ git status
On branch styled
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")


$ git add git-nuestro.md

$ git commit -m "Paso 20 - Resuelto conflictos quedandonos con rama Style."
[styled c8ac061] Paso 20 - Resuelto conflictos quedandonos con rama Style.

$ git reflog
c8ac061 (HEAD -> styled) HEAD@{0}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{1}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{2}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c (main) HEAD@{3}: checkout: moving from main to htmlify
9725b1c (main) HEAD@{4}: checkout: moving from styled to main
3b77153 HEAD@{5}: checkout: moving from main to styled
9725b1c (main) HEAD@{6}: checkout: moving from styled to main
3b77153 HEAD@{7}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (main) HEAD@{8}: reset: moving to HEAD~1
f048e59 HEAD@{9}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (main) HEAD@{10}: checkout: moving from main to styled
9725b1c (main) HEAD@{11}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{12}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

```


## Paso 21 - Desde “main”, hacer un merge con “styled”

```
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)


$ git merge styled
Updating 9725b1c..c8ac061
Fast-forward
 git-nuestro.md | 18 +++++++++---------
 1 file changed, 9 insertions(+), 9 deletions(-)

$ git reflog
c8ac061 (HEAD -> main, styled) HEAD@{0}: merge styled: Fast-forward
9725b1c HEAD@{1}: checkout: moving from styled to main
c8ac061 (HEAD -> main, styled) HEAD@{2}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{3}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{4}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{5}: checkout: moving from main to htmlify
9725b1c HEAD@{6}: checkout: moving from styled to main
3b77153 HEAD@{7}: checkout: moving from main to styled
9725b1c HEAD@{8}: checkout: moving from styled to main
3b77153 HEAD@{9}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{10}: reset: moving to HEAD~1
f048e59 HEAD@{11}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{12}: checkout: moving from main to styled
9725b1c HEAD@{13}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{14}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


```

## Paso 22 - Crear una rama "title" y cambiarse a esa rama
```
$ git branch title

$ git branch
  htmlify
* main
  styled
  title

$ git checkout title
Switched to branch 'title'

```

## Paso 23 - Añadir un título (a tu gusto) al archivo git-nuestro.md y hacer un commit
```
$vi git-nuestro.md

$ cat git-nuestro.md
PRECATIO NECESSARIA
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`

```

## Paso 24 - Volver a la rama main
```
$ git checkout main
M       git-nuestro.md
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

$ git reflog
c8ac061 (HEAD -> main, title, styled) HEAD@{0}: checkout: moving from title to main
c8ac061 (HEAD -> main, title, styled) HEAD@{1}: checkout: moving from main to title
c8ac061 (HEAD -> main, title, styled) HEAD@{2}: merge styled: Fast-forward
9725b1c HEAD@{3}: checkout: moving from styled to main
c8ac061 (HEAD -> main, title, styled) HEAD@{4}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{5}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{6}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{7}: checkout: moving from main to htmlify
9725b1c HEAD@{8}: checkout: moving from styled to main
3b77153 HEAD@{9}: checkout: moving from main to styled
9725b1c HEAD@{10}: checkout: moving from styled to main
3b77153 HEAD@{11}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{12}: reset: moving to HEAD~1
f048e59 HEAD@{13}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{14}: checkout: moving from main to styled
9725b1c HEAD@{15}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{16}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

```

## Paso 25 - Dibujar el diagrama
```
$ git log --graph
*   commit c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb (HEAD -> main, title, styled)
|\  Merge: 3b77153 b13ba77
| | Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| | Date:   Sun Jan 26 11:22:10 2025 +0100
| |
| |     Paso 20 - Resuelto conflictos quedandonos con rama Style.
| |
| * commit b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 (htmlify)
| | Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| | Date:   Sun Jan 26 11:15:52 2025 +0100
| |
| |     Paso 18 - Commit en rama htmlify de git-nuestro.md
| |
* | commit 3b771530e67627f6fbc740ce413f90f9aadb5b14
|/  Author: Miguel A. Ferrero <vael.ibero@gmail.com>
|   Date:   Sun Jan 26 10:04:33 2025 +0100
|
|       Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
|
* commit 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec
| Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| Date:   Sun Jan 26 09:56:57 2025 +0100
|
|     Paso 4 - Mover fichero git-nuestro.md a repositorio
|
* commit aac70fa55dc28b744ec1696577f755f046b3b30e (origin/main, origin/HEAD)
  Author: Miguel Ángel Ferrero Fernández <134866811+vaelibero@users.noreply.github.com>
  Date:   Fri Jan 24 19:18:15 2025 +0100

      Initial commit


$ git log --graph --decorate --pretty=oneline
*   c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb (HEAD -> main, title, styled) Paso 20 - Resuelto conflictos quedandonos con rama Style.
|\
| * b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 (htmlify) Paso 18 - Commit en rama htmlify de git-nuestro.md
* | 3b771530e67627f6fbc740ce413f90f9aadb5b14 Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
|/
* 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec Paso 4 - Mover fichero git-nuestro.md a repositorio
* aac70fa55dc28b744ec1696577f755f046b3b30e (origin/main, origin/HEAD) Initial commit

```

## Paso 26 - Hacer un merge “no fast-forward” de “title” en “main” (main absorbe a title) 
```
$ git merge --no-ff title
Already up to date.



```

## Paso 27 - Deshacer el merge sin perder los cambios del working copy.
```
$ git reflog
c8ac061 (HEAD -> main, title, styled) HEAD@{0}: checkout: moving from main to main
c8ac061 (HEAD -> main, title, styled) HEAD@{1}: checkout: moving from title to main
c8ac061 (HEAD -> main, title, styled) HEAD@{2}: checkout: moving from main to title
c8ac061 (HEAD -> main, title, styled) HEAD@{3}: merge styled: Fast-forward
9725b1c HEAD@{4}: checkout: moving from styled to main
c8ac061 (HEAD -> main, title, styled) HEAD@{5}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{6}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{7}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{8}: checkout: moving from main to htmlify
9725b1c HEAD@{9}: checkout: moving from styled to main
3b77153 HEAD@{10}: checkout: moving from main to styled
9725b1c HEAD@{11}: checkout: moving from styled to main
3b77153 HEAD@{12}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{13}: reset: moving to HEAD~1
f048e59 HEAD@{14}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{15}: checkout: moving from main to styled
9725b1c HEAD@{16}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{17}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

$ git log --graph --decorate --pretty=oneline
*   c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb (HEAD -> main, title, styled) Paso 20 - Resuelto conflictos quedandonos con rama Style.
|\
| * b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 (htmlify) Paso 18 - Commit en rama htmlify de git-nuestro.md
* | 3b771530e67627f6fbc740ce413f90f9aadb5b14 Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
|/
* 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec Paso 4 - Mover fichero git-nuestro.md a repositorio
* aac70fa55dc28b744ec1696577f755f046b3b30e (origin/main, origin/HEAD) Initial commit

$ git reset HEAD~1
Unstaged changes after reset:
M       git-nuestro.md

$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")



```

## Paso 28 - Descartar los cambios (Entendemos que es descartar los cambios en el working directory)
```
$ git restore git-nuestro.md

$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

$ cat git-nuestro.md
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`

```

## Paso 29 - Eliminar la rama title
```
$ git branch -d title
error: the branch 'title' is not fully merged
hint: If you are sure you want to delete it, run 'git branch -D title'
hint: Disable this message with "git config advice.forceDeleteBranch false"

$ git reflog
3b77153 (HEAD -> main) HEAD@{0}: reset: moving to HEAD~1
c8ac061 (title, styled) HEAD@{1}: checkout: moving from main to main
c8ac061 (title, styled) HEAD@{2}: checkout: moving from title to main
c8ac061 (title, styled) HEAD@{3}: checkout: moving from main to title
c8ac061 (title, styled) HEAD@{4}: merge styled: Fast-forward
9725b1c HEAD@{5}: checkout: moving from styled to main
c8ac061 (title, styled) HEAD@{6}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 (HEAD -> main) HEAD@{7}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{8}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{9}: checkout: moving from main to htmlify
9725b1c HEAD@{10}: checkout: moving from styled to main
3b77153 (HEAD -> main) HEAD@{11}: checkout: moving from main to styled
9725b1c HEAD@{12}: checkout: moving from styled to main
3b77153 (HEAD -> main) HEAD@{13}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{14}: reset: moving to HEAD~1
f048e59 HEAD@{15}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{16}: checkout: moving from main to styled
9725b1c HEAD@{17}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{18}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

$ git branch -D title
Deleted branch title (was c8ac061).

$ git reflog
3b77153 (HEAD -> main) HEAD@{0}: reset: moving to HEAD~1
c8ac061 (styled) HEAD@{1}: checkout: moving from main to main
c8ac061 (styled) HEAD@{2}: checkout: moving from title to main
c8ac061 (styled) HEAD@{3}: checkout: moving from main to title
c8ac061 (styled) HEAD@{4}: merge styled: Fast-forward
9725b1c HEAD@{5}: checkout: moving from styled to main
c8ac061 (styled) HEAD@{6}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 (HEAD -> main) HEAD@{7}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{8}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{9}: checkout: moving from main to htmlify
9725b1c HEAD@{10}: checkout: moving from styled to main
3b77153 (HEAD -> main) HEAD@{11}: checkout: moving from main to styled
9725b1c HEAD@{12}: checkout: moving from styled to main
3b77153 (HEAD -> main) HEAD@{13}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{14}: reset: moving to HEAD~1
f048e59 HEAD@{15}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{16}: checkout: moving from main to styled
9725b1c HEAD@{17}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{18}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git
```

## Paso 30 - Rehacer el merge que hemos hecho.
```
$ git reset --hard  HEAD@{4}
HEAD is now at c8ac061 Paso 20 - Resuelto conflictos quedandonos con rama Style.

$ git branch
  htmlify
* main
  styled

$ cat git-nuestro.md
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`

$ git reflog
c8ac061 (HEAD -> main, styled) HEAD@{0}: reset: moving to HEAD@{4}
3b77153 HEAD@{1}: reset: moving to HEAD~1
c8ac061 (HEAD -> main, styled) HEAD@{2}: checkout: moving from main to main
c8ac061 (HEAD -> main, styled) HEAD@{3}: checkout: moving from title to main
c8ac061 (HEAD -> main, styled) HEAD@{4}: checkout: moving from main to title
c8ac061 (HEAD -> main, styled) HEAD@{5}: merge styled: Fast-forward
9725b1c HEAD@{6}: checkout: moving from styled to main
c8ac061 (HEAD -> main, styled) HEAD@{7}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{8}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{9}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{10}: checkout: moving from main to htmlify
9725b1c HEAD@{11}: checkout: moving from styled to main
3b77153 HEAD@{12}: checkout: moving from main to styled
9725b1c HEAD@{13}: checkout: moving from styled to main
3b77153 HEAD@{14}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{15}: reset: moving to HEAD~1
f048e59 HEAD@{16}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{17}: checkout: moving from main to styled
9725b1c HEAD@{18}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{19}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

$ cat git-nuestro.md
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`

$vi git-nuestro.md

$ git branch title

$ git checkout title

$ cat git-nuestro.md
PRECATIO NECESSARIA
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`

$ git status
On branch title
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   git-nuestro.md

no changes added to commit (use "git add" and/or "git commit -a")

$ git commit -m "Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main."
[title 035cd90] Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
 1 file changed, 1 insertion(+)

$ git reflog
035cd90 (HEAD -> title) HEAD@{0}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 (styled, main) HEAD@{1}: checkout: moving from main to title
c8ac061 (styled, main) HEAD@{2}: reset: moving to HEAD@{4}
3b77153 HEAD@{3}: reset: moving to HEAD~1
c8ac061 (styled, main) HEAD@{4}: checkout: moving from main to main
c8ac061 (styled, main) HEAD@{5}: checkout: moving from title to main
c8ac061 (styled, main) HEAD@{6}: checkout: moving from main to title
c8ac061 (styled, main) HEAD@{7}: merge styled: Fast-forward
9725b1c HEAD@{8}: checkout: moving from styled to main
c8ac061 (styled, main) HEAD@{9}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{10}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{11}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{12}: checkout: moving from main to htmlify
9725b1c HEAD@{13}: checkout: moving from styled to main
3b77153 HEAD@{14}: checkout: moving from main to styled
9725b1c HEAD@{15}: checkout: moving from styled to main
3b77153 HEAD@{16}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{17}: reset: moving to HEAD~1
f048e59 HEAD@{18}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{19}: checkout: moving from main to styled
9725b1c HEAD@{20}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{21}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

$ git merge --no-ff title
Merge made by the 'ort' strategy.
 git-nuestro.md | 1 +
 1 file changed, 1 insertion(+)


$ git reflog
0b4ab3e (HEAD -> main) HEAD@{0}: merge title: Merge made by the 'ort' strategy.
c8ac061 (styled) HEAD@{1}: checkout: moving from title to main
035cd90 (title) HEAD@{2}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 (styled) HEAD@{3}: checkout: moving from main to title
c8ac061 (styled) HEAD@{4}: reset: moving to HEAD@{4}
3b77153 HEAD@{5}: reset: moving to HEAD~1
c8ac061 (styled) HEAD@{6}: checkout: moving from main to main
c8ac061 (styled) HEAD@{7}: checkout: moving from title to main
c8ac061 (styled) HEAD@{8}: checkout: moving from main to title
c8ac061 (styled) HEAD@{9}: merge styled: Fast-forward
9725b1c HEAD@{10}: checkout: moving from styled to main
c8ac061 (styled) HEAD@{11}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{12}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{13}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{14}: checkout: moving from main to htmlify
9725b1c HEAD@{15}: checkout: moving from styled to main
3b77153 HEAD@{16}: checkout: moving from main to styled
9725b1c HEAD@{17}: checkout: moving from styled to main
3b77153 HEAD@{18}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{19}: reset: moving to HEAD~1
f048e59 HEAD@{20}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{21}: checkout: moving from main to styled
9725b1c HEAD@{22}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{23}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


```

## Paso 31 - Volver al main y eliminar el resto de ramas.
```
$ git branch -d htmlify
Deleted branch htmlify (was b13ba77).

$ git branch -d styled
Deleted branch styled (was c8ac061).

$ git branch -d title
Deleted branch title (was 035cd90).

```

## Paso 32 - Volver al commit inicial cuando se creo el poema.
```
$ git reflog
0b4ab3e (HEAD -> main) HEAD@{0}: merge title: Merge made by the 'ort' strategy.
c8ac061 (styled) HEAD@{1}: checkout: moving from title to main
035cd90 (title) HEAD@{2}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 (styled) HEAD@{3}: checkout: moving from main to title
c8ac061 (styled) HEAD@{4}: reset: moving to HEAD@{4}
3b77153 HEAD@{5}: reset: moving to HEAD~1
c8ac061 (styled) HEAD@{6}: checkout: moving from main to main
c8ac061 (styled) HEAD@{7}: checkout: moving from title to main
c8ac061 (styled) HEAD@{8}: checkout: moving from main to title
c8ac061 (styled) HEAD@{9}: merge styled: Fast-forward
9725b1c HEAD@{10}: checkout: moving from styled to main
c8ac061 (styled) HEAD@{11}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{12}: checkout: moving from htmlify to styled
b13ba77 (htmlify) HEAD@{13}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{14}: checkout: moving from main to htmlify
9725b1c HEAD@{15}: checkout: moving from styled to main
3b77153 HEAD@{16}: checkout: moving from main to styled
9725b1c HEAD@{17}: checkout: moving from styled to main
3b77153 HEAD@{18}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{19}: reset: moving to HEAD~1
f048e59 HEAD@{20}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{21}: checkout: moving from main to styled
9725b1c HEAD@{22}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{23}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


$ git checkout 9725b1c
Note: switching to '9725b1c'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 9725b1c Paso 4 - Mover fichero git-nuestro.md a repositorio

$ cat git-nuestro.md
Git nuestro que estas en los repos
Comprimidos sean tus commits
Venga a nosotros tu log
En el local como en el remote
Danos hoy nuestro pull de cada día
Perdona nuestros conflictos
Como también perdonamos los de otros geeks
No nos dejes caer en detached HEAD
y líbranos de SVN
git commit--amend

```

## Paso 33 - Volver al estado final cuando se creó el poema
```
$ git reflog
0b4ab3e (HEAD -> main) HEAD@{0}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to main
9725b1c HEAD@{1}: checkout: moving from main to 9725b1c
0b4ab3e (HEAD -> main) HEAD@{2}: checkout: moving from aac70fa55dc28b744ec1696577f755f046b3b30e to main
aac70fa (origin/main, origin/HEAD) HEAD@{3}: checkout: moving from main to aac70fa
0b4ab3e (HEAD -> main) HEAD@{4}: merge title: Merge made by the 'ort' strategy.
c8ac061 HEAD@{5}: checkout: moving from title to main
035cd90 HEAD@{6}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 HEAD@{7}: checkout: moving from main to title
c8ac061 HEAD@{8}: reset: moving to HEAD@{4}
3b77153 HEAD@{9}: reset: moving to HEAD~1
c8ac061 HEAD@{10}: checkout: moving from main to main
c8ac061 HEAD@{11}: checkout: moving from title to main
c8ac061 HEAD@{12}: checkout: moving from main to title
c8ac061 HEAD@{13}: merge styled: Fast-forward
9725b1c HEAD@{14}: checkout: moving from styled to main
c8ac061 HEAD@{15}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{16}: checkout: moving from htmlify to styled
b13ba77 HEAD@{17}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{18}: checkout: moving from main to htmlify
9725b1c HEAD@{19}: checkout: moving from styled to main
3b77153 HEAD@{20}: checkout: moving from main to styled
9725b1c HEAD@{21}: checkout: moving from styled to main
3b77153 HEAD@{22}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{23}: reset: moving to HEAD~1
f048e59 HEAD@{24}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{25}: checkout: moving from main to styled
9725b1c HEAD@{26}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{27}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


$ git checkout  HEAD@{5}
Note: switching to 'HEAD@{5}'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at c8ac061 Paso 20 - Resuelto conflictos quedandonos con rama Style.

$ git status
HEAD detached at c8ac061
nothing to commit, working tree clean

```

## Paso 34 -  Crear los siguientes tags: inicial: en el primer commit | styled: modificación del paso 10 | htmlify: Modificación del paso 17-18 |  title: modificación del paso 30
```
$ git reflog
c8ac061 (HEAD) HEAD@{0}: checkout: moving from main to HEAD@{5}
0b4ab3e (main) HEAD@{1}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to main
9725b1c HEAD@{2}: checkout: moving from main to 9725b1c
0b4ab3e (main) HEAD@{3}: checkout: moving from aac70fa55dc28b744ec1696577f755f046b3b30e to main
aac70fa (origin/main, origin/HEAD) HEAD@{4}: checkout: moving from main to aac70fa
0b4ab3e (main) HEAD@{5}: merge title: Merge made by the 'ort' strategy.
c8ac061 (HEAD) HEAD@{6}: checkout: moving from title to main
035cd90 HEAD@{7}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 (HEAD) HEAD@{8}: checkout: moving from main to title
c8ac061 (HEAD) HEAD@{9}: reset: moving to HEAD@{4}
3b77153 HEAD@{10}: reset: moving to HEAD~1
c8ac061 (HEAD) HEAD@{11}: checkout: moving from main to main
c8ac061 (HEAD) HEAD@{12}: checkout: moving from title to main
c8ac061 (HEAD) HEAD@{13}: checkout: moving from main to title
c8ac061 (HEAD) HEAD@{14}: merge styled: Fast-forward
9725b1c HEAD@{15}: checkout: moving from styled to main
c8ac061 (HEAD) HEAD@{16}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{17}: checkout: moving from htmlify to styled
b13ba77 HEAD@{18}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c HEAD@{19}: checkout: moving from main to htmlify
9725b1c HEAD@{20}: checkout: moving from styled to main
3b77153 HEAD@{21}: checkout: moving from main to styled
9725b1c HEAD@{22}: checkout: moving from styled to main
3b77153 HEAD@{23}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c HEAD@{24}: reset: moving to HEAD~1
f048e59 HEAD@{25}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c HEAD@{26}: checkout: moving from main to styled
9725b1c HEAD@{27}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{28}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

$ git checkout 9725b1c
Previous HEAD position was c8ac061 Paso 20 - Resuelto conflictos quedandonos con rama Style.
HEAD is now at 9725b1c Paso 4 - Mover fichero git-nuestro.md a repositorio

$ git tag inicial

$ git checkout f048e59
Previous HEAD position was 9725b1c Paso 4 - Mover fichero git-nuestro.md a repositorio
HEAD is now at f048e59 Paso 10 - Mover fichero git-nuestro.md a repositorio

$ git tag styled

$ git reflog
9725b1c (HEAD, tag: inicial) HEAD@{0}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 HEAD@{1}: checkout: moving from f048e5914203650e53497714492bed6984ade778 to HEAD@{18}
f048e59 (tag: styled) HEAD@{2}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to f048e59
9725b1c (HEAD, tag: inicial) HEAD@{3}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 HEAD@{4}: checkout: moving from main to HEAD@{5}
0b4ab3e (main) HEAD@{5}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to main
9725b1c (HEAD, tag: inicial) HEAD@{6}: checkout: moving from main to 9725b1c
0b4ab3e (main) HEAD@{7}: checkout: moving from aac70fa55dc28b744ec1696577f755f046b3b30e to main
aac70fa (origin/main, origin/HEAD) HEAD@{8}: checkout: moving from main to aac70fa
0b4ab3e (main) HEAD@{9}: merge title: Merge made by the 'ort' strategy.
c8ac061 HEAD@{10}: checkout: moving from title to main
035cd90 HEAD@{11}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 HEAD@{12}: checkout: moving from main to title
c8ac061 HEAD@{13}: reset: moving to HEAD@{4}
3b77153 HEAD@{14}: reset: moving to HEAD~1
c8ac061 HEAD@{15}: checkout: moving from main to main
c8ac061 HEAD@{16}: checkout: moving from title to main
c8ac061 HEAD@{17}: checkout: moving from main to title
c8ac061 HEAD@{18}: merge styled: Fast-forward
9725b1c (HEAD, tag: inicial) HEAD@{19}: checkout: moving from styled to main
c8ac061 HEAD@{20}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{21}: checkout: moving from htmlify to styled
b13ba77 HEAD@{22}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c (HEAD, tag: inicial) HEAD@{23}: checkout: moving from main to htmlify
9725b1c (HEAD, tag: inicial) HEAD@{24}: checkout: moving from styled to main
3b77153 HEAD@{25}: checkout: moving from main to styled
9725b1c (HEAD, tag: inicial) HEAD@{26}: checkout: moving from styled to main
3b77153 HEAD@{27}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (HEAD, tag: inicial) HEAD@{28}: reset: moving to HEAD~1
f048e59 (tag: styled) HEAD@{29}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (HEAD, tag: inicial) HEAD@{30}: checkout: moving from main to styled
9725b1c (HEAD, tag: inicial) HEAD@{31}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{32}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


$ git checkout HEAD@{22}
Previous HEAD position was 9725b1c Paso 4 - Mover fichero git-nuestro.md a repositorio
HEAD is now at b13ba77 Paso 18 - Commit en rama htmlify de git-nuestro.md

$ cat git-nuestro.md
<p><em>Git</em> nuestro que estas en los repos<br />
Comprimidos sean tus <em>commits</em><br />
Venga a nosotros tu <em>log</em><br />
En el local como en el <em>remote</em><br />
Danos hoy nuestro <em>pull</em> de cada día<br />
Perdona nuestros <em>conflictos</em><br />
Como también perdonamos los de otros geeks<br />
No nos dejes caer en <em>detached HEAD</em><br />
y líbranos de <em>SVN</em><br />
<code>git commit--amend</code></p>


$ git tag htmlify

vaeli@Elistan-1 MINGW64 ~/Documents/IA-Keepcoding/IA-Modulos/Curso_GIT/Pract-GIT-IA-3_M.A.Ferrero ((htmlify))
$ git reflog
b13ba77 (HEAD, tag: htmlify) HEAD@{0}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to HEAD@{22}
9725b1c (tag: inicial) HEAD@{1}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 HEAD@{2}: checkout: moving from f048e5914203650e53497714492bed6984ade778 to HEAD@{18}
f048e59 (tag: styled) HEAD@{3}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to f048e59
9725b1c (tag: inicial) HEAD@{4}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 HEAD@{5}: checkout: moving from main to HEAD@{5}
0b4ab3e (main) HEAD@{6}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to main
9725b1c (tag: inicial) HEAD@{7}: checkout: moving from main to 9725b1c
0b4ab3e (main) HEAD@{8}: checkout: moving from aac70fa55dc28b744ec1696577f755f046b3b30e to main
aac70fa (origin/main, origin/HEAD) HEAD@{9}: checkout: moving from main to aac70fa
0b4ab3e (main) HEAD@{10}: merge title: Merge made by the 'ort' strategy.
c8ac061 HEAD@{11}: checkout: moving from title to main
035cd90 HEAD@{12}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 HEAD@{13}: checkout: moving from main to title
c8ac061 HEAD@{14}: reset: moving to HEAD@{4}
3b77153 HEAD@{15}: reset: moving to HEAD~1
c8ac061 HEAD@{16}: checkout: moving from main to main
c8ac061 HEAD@{17}: checkout: moving from title to main
c8ac061 HEAD@{18}: checkout: moving from main to title
c8ac061 HEAD@{19}: merge styled: Fast-forward
9725b1c (tag: inicial) HEAD@{20}: checkout: moving from styled to main
c8ac061 HEAD@{21}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{22}: checkout: moving from htmlify to styled
b13ba77 (HEAD, tag: htmlify) HEAD@{23}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c (tag: inicial) HEAD@{24}: checkout: moving from main to htmlify
9725b1c (tag: inicial) HEAD@{25}: checkout: moving from styled to main
3b77153 HEAD@{26}: checkout: moving from main to styled
9725b1c (tag: inicial) HEAD@{27}: checkout: moving from styled to main
3b77153 HEAD@{28}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (tag: inicial) HEAD@{29}: reset: moving to HEAD~1
f048e59 (tag: styled) HEAD@{30}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (tag: inicial) HEAD@{31}: checkout: moving from main to styled
9725b1c (tag: inicial) HEAD@{32}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{33}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


$ git checkout HEAD@{12}
Previous HEAD position was b13ba77 Paso 18 - Commit en rama htmlify de git-nuestro.md
HEAD is now at 035cd90 Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.

vaeli@Elistan-1 MINGW64 ~/Documents/IA-Keepcoding/IA-Modulos/Curso_GIT/Pract-GIT-IA-3_M.A.Ferrero ((035cd90...))
$ cat git-nuestro.md
PRECATIO NECESSARIA
*Git* nuestro que estás en los repos
Comprimidos sean tus *commits*
Venga a nosotros tu *log*
En el local como en el *remote*
Danos hoy nuestro *pull* de cada día
Perdona nuestros *conflictos*
Como también perdonamos los de otros geeks
No nos dejes caer en *detached HEAD*
y líbranos de *SVN*
`git commit--amend`

$ git tag title

$ git tag
htmlify
inicial
styled
title



```

## Paso 35 - ir al tag htmlify

```
$ git checkout htmlify
Previous HEAD position was 035cd90 Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
HEAD is now at b13ba77 Paso 18 - Commit en rama htmlify de git-nuestro.md

$ cat git-nuestro.md
<p><em>Git</em> nuestro que estas en los repos<br />
Comprimidos sean tus <em>commits</em><br />
Venga a nosotros tu <em>log</em><br />
En el local como en el <em>remote</em><br />
Danos hoy nuestro <em>pull</em> de cada día<br />
Perdona nuestros <em>conflictos</em><br />
Como también perdonamos los de otros geeks<br />
No nos dejes caer en <em>detached HEAD</em><br />
y líbranos de <em>SVN</em><br />
<code>git commit--amend</code></p>
```

## Paso 36 - Vuelve a la rama main
```
$ git checkout main
Previous HEAD position was b13ba77 Paso 18 - Commit en rama htmlify de git-nuestro.md
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 6 commits.
  (use "git push" to publish your local commits)


```

## Paso 37 - Sube a GitHub todas las ramas y todos los tags (Solo nos queda una rama y 4 tags, por que al eliminar las ramas no las hemos vuelto a crear, procedemos a recrearlas)
```


$ git reset --hard  HEAD@{37}
HEAD is now at 9725b1c Paso 4 - Mover fichero git-nuestro.md a repositorio


$ git branch styled

$ git reflog
0b4ab3e (HEAD -> main) HEAD@{0}: checkout: moving from f048e5914203650e53497714492bed6984ade778 to main
f048e59 (tag: styled) HEAD@{1}: checkout: moving from main to styled
0b4ab3e (HEAD -> main) HEAD@{2}: checkout: moving from b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 to main
b13ba77 (tag: htmlify) HEAD@{3}: checkout: moving from 035cd904ccad8cb8f378cc43fe513ea3fd8e14fc to htmlify
035cd90 (tag: title) HEAD@{4}: checkout: moving from b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 to HEAD@{12}
b13ba77 (tag: htmlify) HEAD@{5}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to HEAD@{22}
9725b1c (tag: inicial) HEAD@{6}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 HEAD@{7}: checkout: moving from f048e5914203650e53497714492bed6984ade778 to HEAD@{18}
f048e59 (tag: styled) HEAD@{8}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to f048e59
9725b1c (tag: inicial) HEAD@{9}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 HEAD@{10}: checkout: moving from main to HEAD@{5}
0b4ab3e (HEAD -> main) HEAD@{11}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to main
9725b1c (tag: inicial) HEAD@{12}: checkout: moving from main to 9725b1c
0b4ab3e (HEAD -> main) HEAD@{13}: checkout: moving from aac70fa55dc28b744ec1696577f755f046b3b30e to main
aac70fa (origin/main, origin/HEAD) HEAD@{14}: checkout: moving from main to aac70fa
0b4ab3e (HEAD -> main) HEAD@{15}: merge title: Merge made by the 'ort' strategy.
c8ac061 HEAD@{16}: checkout: moving from title to main
035cd90 (tag: title) HEAD@{17}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 HEAD@{18}: checkout: moving from main to title
c8ac061 HEAD@{19}: reset: moving to HEAD@{4}
3b77153 HEAD@{20}: reset: moving to HEAD~1
c8ac061 HEAD@{21}: checkout: moving from main to main
c8ac061 HEAD@{22}: checkout: moving from title to main
c8ac061 HEAD@{23}: checkout: moving from main to title
c8ac061 HEAD@{24}: merge styled: Fast-forward
9725b1c (tag: inicial) HEAD@{25}: checkout: moving from styled to main
c8ac061 HEAD@{26}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{27}: checkout: moving from htmlify to styled
b13ba77 (tag: htmlify) HEAD@{28}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c (tag: inicial) HEAD@{29}: checkout: moving from main to htmlify
9725b1c (tag: inicial) HEAD@{30}: checkout: moving from styled to main
3b77153 HEAD@{31}: checkout: moving from main to styled
9725b1c (tag: inicial) HEAD@{32}: checkout: moving from styled to main
3b77153 HEAD@{33}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (tag: inicial) HEAD@{34}: reset: moving to HEAD~1
f048e59 (tag: styled) HEAD@{35}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (tag: inicial) HEAD@{36}: checkout: moving from main to styled
9725b1c (tag: inicial) HEAD@{37}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{38}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git


$ git reflog
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{0}: checkout: moving from main to main
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{1}: reset: moving to HEAD@{37}
0b4ab3e HEAD@{2}: checkout: moving from f048e5914203650e53497714492bed6984ade778 to main
f048e59 (tag: styled) HEAD@{3}: checkout: moving from main to styled
0b4ab3e HEAD@{4}: checkout: moving from b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 to main
b13ba77 (tag: htmlify) HEAD@{5}: checkout: moving from 035cd904ccad8cb8f378cc43fe513ea3fd8e14fc to htmlify
035cd90 (tag: title) HEAD@{6}: checkout: moving from b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 to HEAD@{12}
b13ba77 (tag: htmlify) HEAD@{7}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to HEAD@{22}
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{8}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 HEAD@{9}: checkout: moving from f048e5914203650e53497714492bed6984ade778 to HEAD@{18}
f048e59 (tag: styled) HEAD@{10}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to f048e59
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{11}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 HEAD@{12}: checkout: moving from main to HEAD@{5}
0b4ab3e HEAD@{13}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to main
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{14}: checkout: moving from main to 9725b1c
0b4ab3e HEAD@{15}: checkout: moving from aac70fa55dc28b744ec1696577f755f046b3b30e to main
aac70fa (origin/main, origin/HEAD) HEAD@{16}: checkout: moving from main to aac70fa
0b4ab3e HEAD@{17}: merge title: Merge made by the 'ort' strategy.
c8ac061 HEAD@{18}: checkout: moving from title to main
035cd90 (tag: title) HEAD@{19}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 HEAD@{20}: checkout: moving from main to title
c8ac061 HEAD@{21}: reset: moving to HEAD@{4}
3b77153 HEAD@{22}: reset: moving to HEAD~1
c8ac061 HEAD@{23}: checkout: moving from main to main
c8ac061 HEAD@{24}: checkout: moving from title to main
c8ac061 HEAD@{25}: checkout: moving from main to title
c8ac061 HEAD@{26}: merge styled: Fast-forward
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{27}: checkout: moving from styled to main
c8ac061 HEAD@{28}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{29}: checkout: moving from htmlify to styled
b13ba77 (tag: htmlify) HEAD@{30}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{31}: checkout: moving from main to htmlify
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{32}: checkout: moving from styled to main
3b77153 HEAD@{33}: checkout: moving from main to styled
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{34}: checkout: moving from styled to main
3b77153 HEAD@{35}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{36}: reset: moving to HEAD~1
f048e59 (tag: styled) HEAD@{37}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{38}: checkout: moving from main to styled
9725b1c (HEAD -> main, tag: inicial, styled) HEAD@{39}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{40}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

$ git reset --hard 0b4ab3e
HEAD is now at 0b4ab3e Merge branch 'title' - Rehaciendo por segunda vez desde main.

$ git branch
* main
  styled

$ git reset --hard HEAD@{33}
HEAD is now at 9725b1c Paso 4 - Mover fichero git-nuestro.md a repositorio

$ git branch htmlify

$ git reset --hard 0b4ab3e
HEAD is now at 0b4ab3e Merge branch 'title' - Rehaciendo por segunda vez desde main.

$ git branch
  htmlify
* main
  styled

$ git status
On branch main
Your branch is ahead of 'origin/main' by 6 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

$ git log --graph
*   commit 0b4ab3e0a0585b0a58b175136785b6699cee2216 (HEAD -> main)
|\  Merge: c8ac061 035cd90
| | Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| | Date:   Sun Jan 26 12:00:20 2025 +0100
| |
| |     Merge branch 'title' - Rehaciendo por segunda vez desde main.
| |
| * commit 035cd904ccad8cb8f378cc43fe513ea3fd8e14fc (tag: title)
|/  Author: Miguel A. Ferrero <vael.ibero@gmail.com>
|   Date:   Sun Jan 26 11:58:52 2025 +0100
|
|       Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
|
*   commit c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb
|\  Merge: 3b77153 b13ba77
| | Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| | Date:   Sun Jan 26 11:22:10 2025 +0100
| |
| |     Paso 20 - Resuelto conflictos quedandonos con rama Style.
| |
| * commit b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 (tag: htmlify)
| | Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| | Date:   Sun Jan 26 11:15:52 2025 +0100
| |
| |     Paso 18 - Commit en rama htmlify de git-nuestro.md
| |
* | commit 3b771530e67627f6fbc740ce413f90f9aadb5b14
|/  Author: Miguel A. Ferrero <vael.ibero@gmail.com>
|   Date:   Sun Jan 26 10:04:33 2025 +0100
|
|       Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
|
* commit 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec (tag: inicial, styled, htmlify)
| Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| Date:   Sun Jan 26 09:56:57 2025 +0100
|
|     Paso 4 - Mover fichero git-nuestro.md a repositorio
|
* commit aac70fa55dc28b744ec1696577f755f046b3b30e (origin/main, origin/HEAD)
  Author: Miguel Ángel Ferrero Fernández <134866811+vaelibero@users.noreply.github.com>
  Date:   Fri Jan 24 19:18:15 2025 +0100

      Initial commit

$ git branch
  htmlify
* main
  styled

$ git reset --hard HEAD@{29}
HEAD is now at c8ac061 Paso 20 - Resuelto conflictos quedandonos con rama Style.

$ git branch title

$ git reset --hard 0b4ab3e
HEAD is now at 0b4ab3e Merge branch 'title' - Rehaciendo por segunda vez desde main.

$ git branch
  htmlify
* main
  styled
  title


$ git reflog
0b4ab3e (HEAD -> main) HEAD@{0}: reset: moving to 0b4ab3e
c8ac061 (title) HEAD@{1}: reset: moving to HEAD@{29}
0b4ab3e (HEAD -> main) HEAD@{2}: reset: moving to 0b4ab3e
9725b1c (tag: inicial, styled, htmlify) HEAD@{3}: reset: moving to HEAD@{33}
0b4ab3e (HEAD -> main) HEAD@{4}: reset: moving to 0b4ab3e
9725b1c (tag: inicial, styled, htmlify) HEAD@{5}: checkout: moving from main to main
9725b1c (tag: inicial, styled, htmlify) HEAD@{6}: reset: moving to HEAD@{37}
0b4ab3e (HEAD -> main) HEAD@{7}: checkout: moving from f048e5914203650e53497714492bed6984ade778 to main
f048e59 (tag: styled) HEAD@{8}: checkout: moving from main to styled
0b4ab3e (HEAD -> main) HEAD@{9}: checkout: moving from b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 to main
b13ba77 (tag: htmlify) HEAD@{10}: checkout: moving from 035cd904ccad8cb8f378cc43fe513ea3fd8e14fc to htmlify
035cd90 (tag: title) HEAD@{11}: checkout: moving from b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 to HEAD@{12}
b13ba77 (tag: htmlify) HEAD@{12}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to HEAD@{22}
9725b1c (tag: inicial, styled, htmlify) HEAD@{13}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 (title) HEAD@{14}: checkout: moving from f048e5914203650e53497714492bed6984ade778 to HEAD@{18}
f048e59 (tag: styled) HEAD@{15}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to f048e59
9725b1c (tag: inicial, styled, htmlify) HEAD@{16}: checkout: moving from c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb to 9725b1c
c8ac061 (title) HEAD@{17}: checkout: moving from main to HEAD@{5}
0b4ab3e (HEAD -> main) HEAD@{18}: checkout: moving from 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec to main
9725b1c (tag: inicial, styled, htmlify) HEAD@{19}: checkout: moving from main to 9725b1c
0b4ab3e (HEAD -> main) HEAD@{20}: checkout: moving from aac70fa55dc28b744ec1696577f755f046b3b30e to main
aac70fa (origin/main, origin/HEAD) HEAD@{21}: checkout: moving from main to aac70fa
0b4ab3e (HEAD -> main) HEAD@{22}: merge title: Merge made by the 'ort' strategy.
c8ac061 (title) HEAD@{23}: checkout: moving from title to main
035cd90 (tag: title) HEAD@{24}: commit: Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
c8ac061 (title) HEAD@{25}: checkout: moving from main to title
c8ac061 (title) HEAD@{26}: reset: moving to HEAD@{4}
3b77153 HEAD@{27}: reset: moving to HEAD~1
c8ac061 (title) HEAD@{28}: checkout: moving from main to main
c8ac061 (title) HEAD@{29}: checkout: moving from title to main
c8ac061 (title) HEAD@{30}: checkout: moving from main to title
c8ac061 (title) HEAD@{31}: merge styled: Fast-forward
9725b1c (tag: inicial, styled, htmlify) HEAD@{32}: checkout: moving from styled to main
c8ac061 (title) HEAD@{33}: commit (merge): Paso 20 - Resuelto conflictos quedandonos con rama Style.
3b77153 HEAD@{34}: checkout: moving from htmlify to styled
b13ba77 (tag: htmlify) HEAD@{35}: commit: Paso 18 - Commit en rama htmlify de git-nuestro.md
9725b1c (tag: inicial, styled, htmlify) HEAD@{36}: checkout: moving from main to htmlify
9725b1c (tag: inicial, styled, htmlify) HEAD@{37}: checkout: moving from styled to main
3b77153 HEAD@{38}: checkout: moving from main to styled
9725b1c (tag: inicial, styled, htmlify) HEAD@{39}: checkout: moving from styled to main
3b77153 HEAD@{40}: commit: Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
9725b1c (tag: inicial, styled, htmlify) HEAD@{41}: reset: moving to HEAD~1
f048e59 (tag: styled) HEAD@{42}: commit: Paso 10 - Mover fichero git-nuestro.md a repositorio
9725b1c (tag: inicial, styled, htmlify) HEAD@{43}: checkout: moving from main to styled
9725b1c (tag: inicial, styled, htmlify) HEAD@{44}: commit: Paso 4 - Mover fichero git-nuestro.md a repositorio
aac70fa (origin/main, origin/HEAD) HEAD@{45}: clone: from https://github.com/vaelibero/Pract-GIT-IA-3_M.A.Ferrero.git

$ git tag
htmlify
inicial
styled
title

$ git log --graph
*   commit 0b4ab3e0a0585b0a58b175136785b6699cee2216 (HEAD -> main)
|\  Merge: c8ac061 035cd90
| | Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| | Date:   Sun Jan 26 12:00:20 2025 +0100
| |
| |     Merge branch 'title' - Rehaciendo por segunda vez desde main.
| |
| * commit 035cd904ccad8cb8f378cc43fe513ea3fd8e14fc (tag: title)
|/  Author: Miguel A. Ferrero <vael.ibero@gmail.com>
|   Date:   Sun Jan 26 11:58:52 2025 +0100
|
|       Paso 30 Añadiendo title, preceso de rehacer el merge --no-ff con main.
|
*   commit c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb (title)
|\  Merge: 3b77153 b13ba77
| | Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| | Date:   Sun Jan 26 11:22:10 2025 +0100
| |
| |     Paso 20 - Resuelto conflictos quedandonos con rama Style.
| |
| * commit b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 (tag: htmlify)
| | Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| | Date:   Sun Jan 26 11:15:52 2025 +0100
| |
| |     Paso 18 - Commit en rama htmlify de git-nuestro.md
| |
* | commit 3b771530e67627f6fbc740ce413f90f9aadb5b14
|/  Author: Miguel A. Ferrero <vael.ibero@gmail.com>
|   Date:   Sun Jan 26 10:04:33 2025 +0100
|
|       Paso 12 - Realizar cambio en git-nuestro.md y realizar commit.
|
* commit 9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec (tag: inicial, styled, htmlify)
| Author: Miguel A. Ferrero <vael.ibero@gmail.com>
| Date:   Sun Jan 26 09:56:57 2025 +0100
|
|     Paso 4 - Mover fichero git-nuestro.md a repositorio
|
* commit aac70fa55dc28b744ec1696577f755f046b3b30e (origin/main, origin/HEAD)
  Author: Miguel Ángel Ferrero Fernández <134866811+vaelibero@users.noreply.github.com>
  Date:   Fri Jan 24 19:18:15 2025 +0100

      Initial commit



```

* Me da error por que las ramas interfieren con el nombre de los tags.
```
$ git show-ref
9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec refs/heads/htmlify
0b4ab3e0a0585b0a58b175136785b6699cee2216 refs/heads/main
9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec refs/heads/styled
c8ac06122c7a1ca8f0c0c8ae6d11f56b8fe96dfb refs/heads/title
0b4ab3e0a0585b0a58b175136785b6699cee2216 refs/remotes/origin/HEAD
0b4ab3e0a0585b0a58b175136785b6699cee2216 refs/remotes/origin/main
b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 refs/tags/htmlify
9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec refs/tags/inicial
f048e5914203650e53497714492bed6984ade778 refs/tags/styled
035cd904ccad8cb8f378cc43fe513ea3fd8e14fc refs/tags/title


$ git branch
  htmlify
* main
  styled
  title


$ git branch -d htmlify
Deleted branch htmlify (was 9725b1c).


$ git branch -d styled
Deleted branch styled (was 9725b1c).


$ git branch -d title
Deleted branch title (was c8ac061).


$ git show-ref
0b4ab3e0a0585b0a58b175136785b6699cee2216 refs/heads/main
0b4ab3e0a0585b0a58b175136785b6699cee2216 refs/remotes/origin/HEAD
0b4ab3e0a0585b0a58b175136785b6699cee2216 refs/remotes/origin/main
b13ba774c7bcd9ca0d0ca28a6cc1473942b38f60 refs/tags/htmlify
9725b1c4cad0a3b2cfdf1b1b261ef2bfa5896aec refs/tags/inicial
f048e5914203650e53497714492bed6984ade778 refs/tags/styled
035cd904ccad8cb8f378cc43fe513ea3fd8e14fc refs/tags/title



```


## Paso 
```

```

## Paso 
```

```

## Paso 
```

```

## Paso 
```

```

## Paso 
```

```

