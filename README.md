## HELP SOS

Lista completa con todos los subcomandos disponibles
```ssh
	git help
	git help -a
	git help -g
	git help glossary
```

## BASIC CONFIGURATION

Configurar Nombre que salen en los commits
```ssh
	git config --global user.name "<name or alias>"
```
Configurar Email
```ssh	
	git config --global user.email <email>
```
Marco de colores para los comando
```ssh
	git config --global color.ui true
```

Configurar EMACS como editor
```ssh
	git config --global core.editor emacs
```

## GIT AUTHOR

Mostrar qué revisión y autor modificó por última vez cada línea de un archivo
```ssh
	git blame
```
```ssh
	[-c] [-b] [-l] [-t] [-f] [-n] [-s] [-e] [-p] [-w] [-M] [-C] [-C] [-C]
	[--incremental] [--root] [-L <range>] [-S <revs-file>] [--since=<date>]
	[--ignore-rev <rev>] [--ignore-revs-file <file>]
	[--progress] [--abbrev=<n>] 
	[<rev> | --contents <file> | --reverse <rev>..<rev>]
	[--] <file>
```

## COMMENCE REPOSITORY

Iniciamos GIT en la carpeta donde esta el proyecto
```ssh
	git init
```
Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>    url => https://github.com/user/repository.git
```
Añadimos todos los archivos para el commit
```ssh
	git add .
```
Hacemos el primer commit
```ssh
	git commit -m "Texto que identifique por que se hizo el commit"
```
subimos al repositorio
```ssh
	git push origin master
```

## GIT CLONE

Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>   url => https://github.com/user/repository.git
```
Dentro de la carpeta que genera, comprobar la URL del repositorio:
```ssh
	git remote -v
```
Antes de realizar modificaciones agregar la URL del repositorio original del proyecto:
```ssh
	git remote add upstream https://github.com/user/original-repo(Fork)
```
Comprobar:
```ssh
	git remote -v
```
## GIT STATUS

Comprobar:
```ssh
	git status
	git status -s
```

## GIT ADD

Añadimos el archivo para el commit
```ssh
	git add [“.” , “file”, “folder/”, ….]
```
Añadimos todos los archivos para el commit omitiendo los nuevos
```ssh
	git add --all 
```
Añadimos todos los archivos con la extensión especificada
```ssh
	git add *.txt
```
Añadimos todos los archivos dentro de un directorio y de una extensión especifica
```ssh
	git add docs/*.txt
```
Añadimos todos los archivos dentro de un directorios
```ssh
	git add docs/
```

## GIT COMMIT

Cargar en el HEAD los cambios realizados
```ssh
	git commit -m "message"
```
Agregar y Cargar en el HEAD los cambios realizados
```ssh
	git commit -a -m "message"
```
De haber conflictos los muestra
```ssh
	git commit -a 
```
Agregar al ultimo commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje
```ssh
	git commit --amend -m "Texto que identifique por que se hizo el commit"
```
Ver los commits realizados
```ssh
	git log --oneline
	git log --graph 
	git log --all 
	git log --decorate
```
Renombrar un commit errado
```ssh
	git commit –amend
	:i E  esc,  :i E esc, :wq
```

## GIT DELETE

Eliminar un archivo del repositorio
```ssh
	git rm “file”
```

## GIT SET

Cambio de nombre
```ssh
	git mv “titleFile_1”  “titleFile_2”
```

## GIT PULL

Antes de empezar a trabajar, obtener los últimos cambios del Repositorio Original:
```ssh
	git pull -r upstream master 
```

## GIT PUSH

Subimos al repositorio
```ssh
	git push <origin> <branch>
```
Subimos un tag
```ssh
	git push --tags
```
## GIT LOG

Muestra los logs de los commits
```ssh
	git log
```
Muestras los cambios en los commits
```ssh
	git log --oneline --stat
```
Muestra graficos de los commits
```ssh
	git log --oneline --graph
```

## GIT DIFF

Muestra los cambios realizados a un archivo
```ssh
	git diff
	git diff --staged
```

## GIT HEAD

Saca un archivo del commit
```ssh
	git reset HEAD <archivo>
```
Devuelve el ultimo commit que se hizo y pone los cambios en staging
```ssh
	git reset --soft HEAD^
```
Devuelve el ultimo commit y todos los cambios
```ssh
	git reset --hard HEAD^
```
Devuelve los 2 ultimo commit y todos los cambios
```ssh
	git reset --hard HEAD^^
```
Rollback merge/commit
```ssh
	git log
	git reset --hard <commit_sha>
```

## GIT REMOTE

Agregar repositorio remoto
```ssh
	git remote add origin <url>
```
Cambiar de remote
```ssh
	git remote set-url origin <url>
```
Remover repositorio
```ssh
	git remote rm <name/origin>
```
Muestra lista repositorios
```ssh
	git remote -v
```
Muestra los branches remotos
```ssh	
	git remote show origin
```
Limpiar todos los branches eliminados
```ssh
	git remote prune origin 
```
## GIT BRANCH

Crea un branch
```ssh
	git branch <nameBranch>
```
Lista los branches
```ssh
	git branch
```
Comando -d elimina el branch y lo une al master
```ssh
	git branch -d <nameBranch>
```
Elimina sin preguntar
```ssh
	git branch -D <nameBranch>
```

Crear una rama usando la opción "checkout" de git:
```ssh
	git checkout -b <nameBranch>
```
Renombrar rama
```ssh
	git branch -m [actual_branch] [new_branch]
```
## GIT MELTDOWN

Crea un branch
```ssh
	git merge
```

## GIT TAG

Muestra una lista de todos los tags
```ssh
	git tag
```
Crea un nuevo tags
```ssh
	git tag -a <v#.#.#> -m "message"
```
Enviar tags
```ssh
	git push --tags
```

## GIT REBASE

Los rebase se usan cuando trabajamos con branches esto hace que los branches se pongan al día con el master sin afectar al mismo

Une el branch actual con el mastar, esto no se puede ver como un merge
```ssh
	git rebase
```
Cuando se produce un conflicto no das las siguientes opciones:

cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso
```ssh	
	git rebase --continue 
```
Omite el conflicto y sigue su camino
```ssh
	git rebase --skip
```
Devuelve todo al principio del rebase
```ssh
	git reabse --abort
```
Para hacer un rebase a un branch en especifico
```ssh	
	git rebase <nameBranch>
```

## PULL REQUEST

Hacer click en "Compare & Pull Request"

Escribir cambios del Pull Request.

Si todo está bien, enviar con el botón "Send Pull Request".

Esperar a que el duelo del repositorio lo revise, acepte y mezcle en la rama correspondiente.

## OTROS COMANDOS

Volver a una version anterior
```ssh
	git reset --hard <sha1-commit-id>
```

Lista un estado actual del repositorio con lista de archivos modificados o agregados
```ssh
	git status
```
Quita del HEAD un archivo y le pone el estado de no trabajado
```ssh
	git checkout -- <file>
```
Crea un branch en base a uno online
```ssh
	git checkout -b newlocalbranchname origin/branch-name
```
Busca los cambios nuevos y actualiza el repositorio
```ssh
	git pull origin <nameBranch>
```
Cambiar de branch
```ssh
	git checkout <nameBranch/tagname>
```
Une el branch actual con el especificado
```ssh
	git merge <nameBranch>
```
Verifica cambios en el repositorio online con el local
```ssh
	git fetch
```
Borrar un archivo del repositorio
```ssh
	git rm <archivo> 
```

## FORK

Descargar remote de un fork
```ssh
	git remote add upstream <url>
```

Merge con master de un fork
```ssh
	git fetch upstream
	git merge upstream/master
```

## SEMANTIC COMMIT MESSAGES
```ssh
	Format: <type>(<scope>): <subject>
```

```
	feat: (new feature for the user, not a new feature for build script)
	fix: (bug fix for the user, not a fix to a build script)
	docs: (changes to the documentation)
	style: (formatting, missing semi colons, etc; no production code change)
	refactor: (refactoring production code, eg. renaming a variable)
	test: (adding missing tests, refactoring tests; no production code change)
	chore: (updating grunt tasks etc; no production code change)
```

## GIT FLOW

```ssh
	git flow init

	git flow feature start feature_branch

	git flow feature finish feature_branch

	git flow release start 0.1.0

	git flow release finish '0.1.0'

	git flow hotfix start hotfix_branch

	git flow hotfix finish hotfix_branch
```
