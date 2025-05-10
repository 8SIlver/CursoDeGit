

# Git/GitHub 
(Apuntes de las clases)

### **CLASE 1**
**Aprendiendo**
>-Git  .- Es un control de versiones
-Repositorio = carpeta donde se almacena las versiones de un proyect:
           repoLocal - repoRemoto

**Comandos**
```
git init (proyecto con git)
git --help (todos los comandos)
```
**Consejos**
-El mejor consejo: Hagan proyectos ayuda mucho a la formacion 
-Aprovechen sus cuentas institucionales

### **CLASE 2**
**Aprendiendo**
>-Estados en Git:
     Modified (archivo modificado), 
     Staged   (confirmacion cambios guardado, preparado para repositorio local), 
     Commited (comentario y listo esta en repo.Local)
     finalmente hemos hecho un COMMIT=fotoDeCambio(s)     
 (archivo traqueado = se le esta haciendo seguimiento de modificaciones)
 -HEAD .- Donde estas en un mapa, solo puedes estar en uno, y ese es head=cabeza=estasAqui,
          es un puntero
 -Rama .-  Es un camino paralelo del codigo, es un puntero, se usa para avanzar en otra cosa y esto lo hace no   lineal, esto da paso al desarrollo colaborativo, trabajan en ramas y al finalizar se unen al main  
 Ojo: Una rama es un puntero que apunta a un commit.

**Comandos**

```
git status (estado de archivos, modificados)
git add nameArchivo otroArchivo ... (pasamos a estado Staged)
git add . (todo arch modificado pasa a Staged)
git restore --staged nameArchivo (eliminar arch de Staged a modified)
git commit -m "mensaje" (para hacer commit)
git commit --amend -m "mensaje" (reemplaza un commit hecho)
git log (ver toda la repo/commit hechos)
git log --online (lo mismo que git log pero mas resumido)
git log --help (buscar comando, algo especifico de repo)
ArchivoConName= .gitignore (dentro de este pones nameArch, para no traquear/seguimiento)
git checkout codigoAch (cambiar donde estoy, HEAD)
git switch - (nos cambiamos de rama, HEAD)
git branch nameRama (crea una rama)
git branch (muestra ramas que existen)
git switch nameRama (cambiarme de rama, HEAD)
git switch -c nameRama (crea una rama y se mueve a esa rama, HEAD)
&& (para concatenar comandos)

```
**Consejos**
NULL

### **CLASE 3**
**Aprendiendo**
>(fast-forward = fusionar ramas,mueve puntero de la que estamos a la rama que estamos mergeando)
-Fusionar ramas .- Dos ramas se comparan linea por linea y se unen,y se genera un commit automatico,
puede haber conflictos, en general sucede cuando estas trabajando en un mismo archivo. Tambien se puede eliminar una rama.
![](https://guias.donweb.com/wp-content/uploads/2021/12/como-usar-ramas-en-git.jpg)

**Comandos**

```
git rm --cached nameArch (para ignorar una archivo, para archPrivados)
git merge nameRama (fusion entre ramas, y hace commitAutomatico)
git merge --abort (desace el merge, util cuando hay conflictos)
git branch -D nameRama (elimina la rama)
git branch -a (para ver todas las ramas incluso las de la nube)
git rebase (similar al merge,pero trae cambios eliminaAnteriores commits y vuelve en uno)
git diff (para ver un conflictos)
```

**Consejos**
NULL

### **CLASE 4**
**Aprendiendo**
>-GitHub .- Software en la nube que esta integrado con git. Se utiliza para gestionar, trabajar colaborativamente, entre otras; con  repositorios de Git
![](https://i.ytimg.com/vi/LuWAw-RBPys/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLChK2dT_zt0r3S0TUKJfqvSiEbz3A)
>-Repositorios remotos .- Repos hospedados en un servidor, punto de sincronizacion de repos locales    
Observacion: Un repoLocal puede enlazarse a varios reposRemotos     
-Llave SSH = firma .- Se usa para autentificarse de forma segura, entre tu compu y un servidor, evita escribir usuario y contrasña cada vez, es muy segura.   
  Clonar un Repositorio .- Podemos descargar un repo remoto a nuestro escritorio
-Push/Pull/PullRequest .-
  *Escribir en un repoRemoto .- Podemos trabajar localmente y subir un commit al repoRemoto, Push=Empujar
  Crear ramaRemota .- Hacemos una rama local y luego la subimos a la RepoRemota
  Eliminar ramasRemota .- se lo puede hacer desde gitHub, actualizar/eliminar la referencia que hay en Repolocal de que aun existe dicha rama
  *Traer cambios de repoRemoto a local .- Util en trabajo colaborativo ya que traes cambios que alguien a subido Pull=Jalar.
  *PullRequest/PR .- Solicitud para fusionar una rama con otra en un repo, en gitHub en este caso, y alguien revisa el codigo antes de integrarlo. Esto puedes hacerlo desde gitHub por facilidad.
Observacion: Tanto el push como el pull puenden dar conflictos, similare a cuando hacemos merge..., porque en si son como fusiones pero en repoRemotos.

**Comandos**

```
git remote add origin enlaceRepoRemoto (sincronizar un repoLocal a uno remoto, puede ser alReves)
git remote (muestra el nameRepoRemoto)
git clone enlaceRepo (para clonar un repo, debes estar en el escritorio para que se clone ahì)
git push aliasRepoRemoto/origin ramaQueSubiremos (para subir arch/cambios/rama a un RepoRemoto)
git remote prume aliasRepoRemoto/origin (elimina referencia de una ramaRemota que se elimino)
git fetch (para actualizar referencas de que ramas existen en RepoRemoto)
git pull --set-upstream  origin ramaRemota (enlasa/traeCambios de ramaRemota con la local donde estas)
git pull --all (trae todos los cambios de remoto, a su recpectiva rama...)

git pull origin ramaRemotaTraer (traer cambios de RepoRemoto, antes hacer git fetch)
git remote -v (para saber alias y url de ReposRemotos)
git switch nameRamaRemota (para movernos a ramaRemota)
```
**Consejos**
NULL
### **CLASE 5**
**Aprendiendo**
>-Git Flow .- Estrategia de trabajo de git, define modelo estructurado 'ramas especializadas' para gestionar desarollo de software. Principales ramas: 
  RamasPrincipales   Main, codigo en produccion.           
                     Develop, codigo en desarrollo.
  RamasSoporte       Feature/nombre, Para nuevas funcionalidades.
                     Release/numero, Preparar una nueva version estable.
                     Hotfix/nombre,  Para arreglar errores de produccion.
-GitHub Flow .- Estrategia de trabajo agil pensada para desarrollo continuo y frecuente, alternativa mas simple a git flow, solo tiene ramas de trabajo a integrarase a main por medio de P.R. 
-Filosofia para toma de desiciones en fusiones: 
    Ship .- Fusionar sin revision, desicion pequeña,dentro de tu responsabilidad.
    Show .- Discusion tras fusion, desicion que puede tener impacto, pero no necesita aprobacion.  
    Ask  .- Hace Discusion/feedback/P.R.,antes de fusionar.

**Comandos**
```
NULL (Todo lo visto se hizo en la interfaz de gitHub)
```

**Consejos**
-el mejor consejo: Agan proyectos ayuda mucho a la formacion 
-Aprovechen sus cuentas institucionales

### **CLASE 6**
**Aprendiendo**
>-Buenas practicas en git .- Es un estandar y es importante cuando trabajas en equipo
1. cada cuanto hacer un commit, pues a menudo,que sea modular sigue la idea rastros con migas de pan.
![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiMqPQUxaZV_WnRb9ysTlme7xQNyVHLyz3uSF-YOUalwNE9a5mODjHB-WQxNm2ESblmLbwuHVpiMpdrNY2YmM_nh_GS63LlVUdgD19Y362RFmtHB7MZMAQ1q1GT1R11jH2W7MVhRWGxTc9U/s1600/0+%25283%2529.jpg)
>2. Escribe buenos commits .- Usa verbo imperativo, escribe en minuscula!, se claro/conciso/preciso, no uses reglas de puntuacion, que sea modular, usa preficos como: feat, fix, perf, build, ci, docs, refactor, style, test, segun el que estes haciendo...                                          
3. Escribe un buen nombre de rama .- Dicho nombre debe estar relacionado con lo que se esta haciendo en la rama y de ser claro/consistente, usa IDs de JIRA u otro...
Conclusion: Git es commits y ramas entonces debes manejar buenas practicas en commits y ramas

**Comandos**
```
NULL (hacer buenos commit y ramas)

```

**Consejos**
Ingles importante (como siempre)

### **CLASE 7**
**Aprendiendo**
>-Desacer cambios .- Sucede por diferentes razones, un error en algo,para retroceder, etc.
Hay 2 tipos:
      Comados destructivos, afecta a historial de los comits.
      No destructivos, trabajan sobre el historial de los commits sin afectarlo.
Y tenemos 3 comandos para esto:
'Destructivos'
Ej. git reset hay 2: 
      soft, elimina el commit pero mantine cambios que e hecho en ese commit
      hard, lo mismo que el anterio, pero los cambios los elimina/descarta
'No destructivos'       
Ej. git revert, revierte cambios que hizo un commit, y crea uno nuevo con los cambios revertidos 
Ej. git checkout, permite recuperar codigo especifico de commits   

**Comandos**

```
git reset codCommit (borra commitsDelante pero mantiene cambios en archivos no en staging)
git reset --soft codCommit (borra commitsDelante pero, mantine los cambios en staging)
git reset --hard codCommit (borra commitsDelante y sus cambios )
git revert codCommit (desace lo hecho en codCommit,osea va al anterior de ese, y hace commit de eso)
git revert abort (para abordar el anterios comando, usado cuando salen conflictos)
git checkout (recueperar codigo que no queria eliminar)
gi show codCommit (muestra lo que se hizo en este commit )
git reflog && git reset (para volver si eliminamos todos los commits)
```

**Consejos**
NULL

### **CLASE 8**
**Aprendiendo**
>-Hooks, Alias y trucos de Git
Hook .- Es un scrip que se ejecuta automaticamente, cuando ocurren ciertos eventos en un repo. estos se encuentran en la capeta de .git/hooks/ del repo, y permite automatizar tareas. 
Hay unos tipos por ejemplo:
    los del lado del cliente .- pre-commit , pre-push, post-commit, commit-msg, y otros qeu tu puedes crear...
    los del lado del servidor .- pre-receive, update, post-receive,...
Alias .- Es una forma de crear un comando personalizado o atajo para comandos largos o complejos, permite hacer uno mas corto en lugar del completo. Ej. git status /a/ git st
Esto se hace agregando un alias a la configuracion de Git:
git config --global alias.st alias.st status
Trucos de Git : Guarda tus cambios temporalmente - git stash   
                Aplicar cambios de commits en especifico - git cherry <SHA>
                Detectar que commit introdujo el bug - git bisect
                Rercupera un archivo en concreto de otra rama o commit - git checkout <SHA> <archivo>        
                entre otros
                           .
                           .
                           .

**Comandos**
```
git config --global alias.st alias.st status (para hacer alias de comandos)
```

**Consejos**
NULL


