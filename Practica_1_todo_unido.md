### 0.3 Uso básico

**Los tres estados de Git**

![Tres estados de Git](https://git-scm.com/figures/18333fig0106-tn.png)

**Comandos básicos I**

Iniciar repositorio en un directorio:

**`git init`**

Agregar cambios al area de *staging*:

**`git add`**

Validar cambios en el repositorio:

**`git commit -m "Mensaje"`**

Hacer los dos pasos anteriores en uno:

**`git commit -am "Mensaje"`**

Historial de commits:

**`git log`**

**Comandos básicos II**

Ayuda del listado anterior:

**`git help log`**

Listar los 5 commits más recientes:

**`git log -n 5`**

Listar los commits desde una fecha:

**`git log --since=2018-09-18`**

Ver cambios en el directorio:

**`git status`**

**Comandos básicos III**

ver diferencia entre ficheros en el directorio y el repositorio de git:

**`git diff`**

Ver diferencia entre ficheros en el *staging* y el repositorio:

**`git diff --staged`**

Eliminar archivos:


**`git rm archivo`**

**`git commit -m "Mensaje"`**

Mover o renombrar archivos:

**`git mv antiguo archivo`**

**`git commit -m "Mensaje"`**

**Comandos básicos IV**

Deshacer cambios con git:

**`git checkout -- nombre_fichero`**

Retirar archivos del *staging*:

**`git reset HEAD nombre_fichero`**

Completar último commit:

**`git commit --amend -m "Mensaje"`**

Recuperar version de un fichero de commit antiguo:

**`git checkout <id_commit>`**

Revertir un commit:

**`git revert <id_commit>`**

**Comandos básicos V**

Deshacer múltiples cambios en el repositorio:

~~~
git reset --soft <id_commit>
git reset --mixed <id_commit>
git reset --hard <id_commit>
~~~

Listar archivos que git no controla:

**`git clean -n`**

Eliminar archivos que git no controla:

**`git clean -f`**

Ignorar archivos en el repositorio: .gitignore

**Camandos básicos VI**

Listar el contenido del repositorio de git:

~~~
git ls-tree master
git ls-tree master^^^
git ls-tree master~3
~~~

Log en una línea:

**`git log --oneline`**

Log con los tres últimos commits en una línea:

**`git log --oneline -3`**

Para más opciones consultar documentación de git.

**Comandos básicos VII**

Examinar el contenido de un commit:

**`git show <id>`**

Comparar un commit con el actual:

**`git diff <id> nombre_archivo`**

Comparar dos commits:

**`git diff id..id nombre_archivo`**
**Comandos básicos VII**

Examinar el contenido de un commit:

**`git show <id>`**

Comparar un commit con el actual:

**`git diff <id> nombre_archivo`**

Comparar dos commits:

**`git diff id..id nombre_archivo`**

# 0.4  Ramas

## Ramas o Branches

Es la forma para separar la línea actual de desarrollo con respeccto a la principal. Normalmente representan versionds del software que posteriormente son integradas a la línea principal.

![imagen ramas git](https://uialberto.files.wordpress.com/2016/11/gitflowui.png)

## Comandos Ramas I

Ver listado de ramas:

**`git branch`**

Crear una rama:

**`git branch nombre_rama`**

Cambiarnos a una rama:

**`git checkout nombre_rama`**

Crear una rama y moverse en un paso:

**`git checkout -b nombre_rama`**

Comparar ramas:

**`git diff nombre_rama1..nombre_rama2`**

## Comandos Ramas II

Ver ramas idénticas a la actual:

**`git branch --merged`**

Renombrar ramas:

**`git branch rama_antigua rama_nueva`**

Eliminar ramas:

**`git branch -d nombre_rama`**

**`git branch -D nombre_rama`**

Integrar ramas a la actual:

**`git merge nombre_rama`**

Resolver conflictos entre ramas:

**`git merge --abort`**

## Comandos Ramas III

Almacenar cambios temporales:

**`git stash save "Mensaje"`**

Listar cambios:

**`git stash list`**

Ver contenido de un cambio temporal:

**`git stash show -p nombre_stash`**

Eliminar un cambio temporal:

**`git stash drop nombre_stash`**

Aplicar cambio del stash:

**`git stash apply nombre_stash`**

**`git stash pop nombre_stash`**

### 0.5 Git Hub

**GitHub no es Git**

![Foto de diferencia](https://www.jsys.co/wp-content/uploads/2017/03/git-github.jpg)

**Comandos GitHub I**

Añadir repositorio remoto:

**`git remote add origin url`**

Ver repositorio remotos:

**`git remote -v`**

Eliminar repositorio remoto:

**`git remote rm origin`**

Añadir cambios del repositorio local remoto:

**`git push -u origin master`**

Áñadir cambios del repositorio remoto al local:

**`git pull`**

**Comandos GitHub II**

Ver branches remotos

**`git branch -r`**

Ver todos los branches

**`git branch -a`**

Clonar un repositorio remoto:

**`git clone url`**

**Dar seguimiento a branches remotos**

* LOCAL -> REMOTO

1. Cambios en el repositorio local.

2. Commit de los cambios

3. Añadir cambios a repositorios remoto:

**`git push`**

* REMOTO -> LOCAL

* Sincronización y unión:

**`git fetch origin`**

**`git merge origin/master`**

* En un solo paso:

**`git pull`**

**Operaciones con branches remotos**

* Creación:

1. Crear branch local.

2. Hacer cambios en dicho branch.

3. Hacer commit.

4. Copiar el branch al repositorio remoto:

**`git push -u origin branch_remoto`**

* Copia:

**`git checkout -b local remoto`**

* Eliminación:

**`git push origin --delete branch_remoto`**

