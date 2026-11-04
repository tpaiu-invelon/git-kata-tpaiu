## Misión 0 — El campo de entrenamiento
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata$ git clone https\://github.com/tpaiu-invelon/git-kata-tpaiu.git

Clonando en 'git-kata-tpaiu'...

remote: Enumerating objects: 3, done.

remote: Counting objects: 100% (3/3), done.

remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)

Recibiendo objetos: 100% (3/3), listo.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata$ cd git-kata-tpaiu/

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git config user.name "tpaiu-invelon"

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git config user.email "tpaiu\@invelon.com"

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ cat > menu.md <<'EOF'

\# Menú del día



\## Primero

\- Sopa



\## Segundo

\- Pollo



\## Postre

\- Fruta

EOF

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$



tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git add menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -m "Add base menu"

[main 01e3b43] Add base menu

 1 file changed, 10 insertions(+)

 create mode 100644 menu.md



tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git add menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -m "Add base menu"

[main 01e3b43] Add base menu

 1 file changed, 10 insertions(+)

 create mode 100644 menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git push

Username for 'https\://github.com': tpaiu-invelon

Password for 'https\://tpaiu-invelon\@github.com': 

Enumerando objetos: 4, listo.

Contando objetos: 100% (4/4), listo.

Compresión delta usando hasta 12 hilos

Comprimiendo objetos: 100% (3/3), listo.

Escribiendo objetos: 100% (3/3), 332 bytes | 332.00 KiB/s, listo.

Total 3 (delta 0), reusados 0 (delta 0), pack-reusados 0

To https\://github.com/tpaiu-invelon/git-kata-tpaiu.git

   ec45db7..01e3b43  main -> main

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 

```



Solución Para poder conectar mi terminal de Linux con el repositorio remoto de GitHub y realizar un \`git push\` correctamente, he seguido estos pasos para autenticarme utilizando un \*\*Personal Access Token (Classic)\*\*.



\---



1\. Inicié sesión en mi cuenta de [GitHub.com]\(https\://github.com).

2\. Hice clic en la foto de mi perfil (arriba a la derecha) y entré en \*\*Settings\*\*.

3\. En el menú de la izquierda, bajé al final y seleccioné \*\*Developer Settings\*\*.

4\. Fui a \*\*Personal access tokens\*\* > \*\*Tokens (classic)\*\*.

5\. Hice clic en \*\*Generate new token\*\* y elegí \*\*Generate new token (classic)\*\*.

6\. Le asigné la siguiente configuración:

   - \*\*Note (Nombre):\*\* \`Terminal_linux\`

   - \*\*Expiration:\*\* \`30 días\`

   - \*\*Scopes:\*\* Marqué todas las casillas.

7\. Hice clic al final en \*\*Generate token\*\* para crearlo.

8\. \*\*Copié el token generado\*\* de inmediato para no perderlo.

9\. Abrí la terminal de Linux dentro de mi proyecto.



10\. Ejecuté el comando de subida:

git push origin main





¿Qué diferencia hay entre git add y git commit? ¿Y entre commit y push?

    \*\*git add\*\*: Pasa los cambios del Working Directory al Staging Area. Es decir, selecciona qué archivos o líneas van a formar parte del "paquete".



    \*\*git commit\*\*: Toma todo lo que está en el Staging Area, le pone un mensaje explicatorio y crea una foto permanente dentro de tu Local Repository.



¿Qué es el "staging area" y por qué existe un paso intermedio?



El \*\*Staging Area\*\* (o área de preparación) es un paso intermedio en Git entre los archivos editados y el repositorio local.



Existe por dos razones principales:

    \*\*Agrupar cambios\*\*. permite elegir exactamente qué archivos o líneas de código incluir en un commit, separando tareas distintas aunque las hayas programado al mismo tiempo.



    \*\*Servir de borrador\*\*: Te da un espacio para revisar y confirmar los cambios  antes de guardarlos permanentemente, evitando guardar errores o archivos basura.













##  Misión 1 — Ramas y commits sucios (a propósito)


```bash
iberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ nano menu.md 

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -am "wip"

[main 706e5e4] wip

 1 file changed, 1 insertion(+), 1 deletion(-)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ nano menu.md 

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -am "fix"

[main 5d012f0] fix

 1 file changed, 1 insertion(+)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ nano menu.md 

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -am "asdf"

[main cd251ce] asdf

 1 file changed, 1 insertion(+), 1 deletion(-)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ nano menu.md 

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -am "otra vez"

[main b0c1ccf] otra vez

 1 file changed, 1 insertion(+)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

b0c1ccf (HEAD -> main) otra vez

cd251ce asdf

5d012f0 fix

706e5e4 wip

01e3b43 (origin/main, origin/HEAD) Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 
```


Para arreglarlo lo que he hecho es lo siguiente 
```bash

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git branch feature/1-primeros-platos

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git reset --hard origin/main

HEAD está ahora en 01e3b43 Add base menu

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

01e3b43 (HEAD -> main, origin/main, origin/HEAD) Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch feature/1-primeros-platos
```

Cambiado a rama 'feature/1-primeros-platos'
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

b0c1ccf (HEAD -> feature/1-primeros-platos) otra vez

cd251ce asdf

5d012f0 fix

706e5e4 wip

01e3b43 (origin/main, origin/HEAD, main) Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git rebase -i main

[HEAD desacoplado 8362dc2] Add primeros platos al menú arreglado

 Date: Tue Nov 3 10:09:33 2026 +0100

 1 file changed, 3 insertions(+), 1 deletion(-)

Rebase aplicado satisfactoriamente y actualizado refs/heads/feature/1-primeros-platos.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

8362dc2 (HEAD -> feature/1-primeros-platos) Add primeros platos al menú arreglado

01e3b43 (origin/main, origin/HEAD, main) Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 
```


¿Qué le dice ese historial a alguien que revise tu PR?



Se realizaron todos los commits en el main  antes de crear la rama feature/1-primeros-platos



 ¿Son lo mismo git switch -c y git checkout -b?  ¿Cuál es más moderno?

`git switch`: únicamente para moverse entre ramas o crearlas.

`git restore`: únicamente para deshacer cambios en archivos.



Según el gemini  **`git switch`** se introdujo en **Git 2.23 (año 2019)** para separar las responsabilidades del antiguo comando `git checkout`.





##  Misión 2 — amend: arreglar el último commit


```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git add menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit --amend -m "Add pumpkin cream to starters"

[feature/1-primeros-platos 01f562e] Add pumpkin cream to starters

 Date: Tue Nov 3 10:09:33 2026 +0100

 1 file changed, 4 insertions(+), 1 deletion(-)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

01f562e (HEAD -> feature/1-primeros-platos) Add pumpkin cream to starters

01e3b43 (origin/main, origin/HEAD, main) Add base menu

ec45db7 Initial commit
```


¿Apareció un commit nuevo o cambió el que ya había?

Cambio el commit que había  Add primeros platos al menú arreglado por  Add pumpkin cream to starters

Compara el hash del último commit antes y después del amend. ¿Es el mismo?

No es el mismo el hash actual es 01f562e y el anterior era 8362dc2

⚠️ **Pregunta clave:** ¿por qué amend es peligroso si YA habías hecho push?

Al hacer --amend, Git borra el commit anterior y genera uno totalmente nuevo con un HASH distinto. Si ya habías subido el commit original a GitHub, al intentar hacer git push te dará un conflicto de historial y tendrás que forzar la subida (push --force), lo cual puede causar problemas a tus compañeros de equipo.





## Misión 3 — squash: la que no hiciste en CMS Jr.


```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

a698ed4 (HEAD -> feature/1-primeros-platos) Add starters section to the daily menu

01e3b43 (origin/main, origin/HEAD, main) Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git push -u origin feature/1-primeros-platos

Username for 'https\://github.com': tpaiu-ivelon

Password for 'https\://tpaiu-ivelon\@github.com': 

Enumerando objetos: 5, listo.

Contando objetos: 100% (5/5), listo.

Compresión delta usando hasta 12 hilos

Comprimiendo objetos: 100% (3/3), listo.

Escribiendo objetos: 100% (3/3), 402 bytes | 402.00 KiB/s, listo.

Total 3 (delta 0), reusados 0 (delta 0), pack-reusados 0

remote: 

remote: Create a pull request for 'feature/1-primeros-platos' on GitHub by visiting:

remote:      https\://github.com/tpaiu-invelon/git-kata-tpaiu/pull/new/feature/1-primeros-platos

remote: 

To https\://github.com/tpaiu-invelon/git-kata-tpaiu.git

 \* [new branch]      feature/1-primeros-platos -> feature/1-primeros-platos

rama 'feature/1-primeros-platos' configurada para rastrear 'origin/feature/1-primeros-platos'.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 
```

¿Cuántos commits quedan? ¿Se perdió algún cambio del fichero?

quedan  un único commit  en la rama que es el commites  final unificado mediante. 

Agrupa los 2 commits ( Add pumpkin cream to starters y el Add starters section to the daily menu ) y los otros 4 comits (`wip`, `fix`, `asdf`, `otra vez`) que unificado en la misión 1 y los he subido a  la rama  feature/1-primeros-platos

 ¿Por qué un revisor prefiere 1 commit claro a 4 commits "wip"?



**`a698ed4` (1 commit en tu rama):** Es tu commit final unificado mediante *squash*. Agrupa los  commits hechos anteriormente en un único commit.

**`01e3b43` y `ec45db7` (2 commits base):** Son los commits originales de la historia del repositorio sobre los que construiste la rama.

##  Misión 4 — PR y merge
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch main

git pull

git log --oneline --graph --all

Cambiado a rama 'main'

Tu rama está actualizada con 'origin/main'.

remote: Enumerating objects: 1, done.

remote: Counting objects: 100% (1/1), done.

remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)

Desempaquetando objetos: 100% (1/1), 917 bytes | 229.00 KiB/s, listo.

Desde https\://github.com/tpaiu-invelon/git-kata-tpaiu

   01e3b43..bdf4ae2  main       -> origin/main

Actualizando 01e3b43..bdf4ae2

Fast-forward

 menu.md | 5 ++++-

 1 file changed, 4 insertions(+), 1 deletion(-)

\*   bdf4ae2 (HEAD -> main, origin/main, origin/HEAD) Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

|\  

\| \* a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

|/  

\* 01e3b43 Add base menu

\* ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 
```


¿Aparece un "commit de merge"? ¿Qué es y por qué existe?

Sí, es el commit bdf4ae2. Es un commit especial que se crea automáticamente al fusionar dos ramas.





## Misión 5 — fetch vs pull (demuéstralo, no lo recites)
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline main -1

bdf4ae2 (HEAD -> main, origin/main, origin/HEAD) Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline origin/main -1

bdf4ae2 (HEAD -> main, origin/main, origin/HEAD) Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git fetch origin



remote: Enumerating objects: 5, done.

remote: Counting objects: 100% (5/5), done.

remote: Compressing objects: 100% (3/3), done.

remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)

Desempaquetando objetos: 100% (3/3), 1010 bytes | 1010.00 KiB/s, listo.

Desde https\://github.com/tpaiu-invelon/git-kata-tpaiu

   bdf4ae2..19fae3a  main       -> origin/main

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline main -1

bdf4ae2 (HEAD -> main) Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline origin/main -1

19fae3a (origin/main, origin/HEAD) Update README.md with editing note

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git status 

En la rama main

Tu rama está detrás de 'origin/main' por 1 commit, y puede ser avanzada rápido.

  (usa "git pull" para actualizar tu rama local)



nada para hacer commit, el árbol de trabajo está limpio

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git pull

Actualizando bdf4ae2..19fae3a

Fast-forward

 README.md | 4 +++-

 1 file changed, 3 insertions(+), 1 deletion(-)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline main -1

19fae3a (HEAD -> main, origin/main, origin/HEAD) Update README.md with editing note
```


- Después del fetch, ¿cambió tu main? ¿Cambió origin/main?

No cambiaron ni main ni origin/main porque hemos hecho los cambios desde la web y no los hemos descargado los cambios que hemos añadido en el [README.md](http://readme.md)  desde la página web.

- ¿Qué es exactamente origin/main? ¿Está en tu disco o en GitHub?

Es una copia local de solo lectura que guarda el Git para recordar en qué punto se encuentra la rama `main` de GitHub la última vez que te comunicaste con el servidor desde el local.

- Completa: git pull = git fetch + git merge



- ¿Cuándo usarías fetch solo, sin pull?

Según gemini me recomendó usar el `git fetch` en los siguientes escenarios:

1. **Inspección segura:** Cuando quieres revisar qué cambios han hecho tus compañeros antes de meterlos en tu código (evitando romper tu entorno de trabajo por sorpresa).
2. **Comparar diferencias:** Cuando quieres hacer un `git diff main origin/main` o un `git log main..origin/main` para examinar el trabajo remoto sin alterar tus archivos.
3. **Trabajar sin conexión o evitar merges automáticos:** Para traer las ramas y etiquetas (*tags*) del servidor a tu disco sin forzar una integración con tu trabajo en curso.



## Misión 6 — El conflicto (rebase de verdad)
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch main && git pull

Ya en 'main'

Tu rama está actualizada con 'origin/main'.

Ya está actualizado.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch -c feature/2-postre-tarta

Cambiado a nueva rama 'feature/2-postre-tarta'

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ nano menu.md 

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -am "Change dessert to cheesecake"

[feature/2-postre-tarta e28145f] Change dessert to cheesecake

 1 file changed, 1 insertion(+), 1 deletion(-)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git push -u origin feature/2-postre-tarta

Username for 'https\://github.com': tpaiu-invelon

Password for 'https\://tpaiu-invelon\@github.com': 

Enumerando objetos: 5, listo.

Contando objetos: 100% (5/5), listo.

Compresión delta usando hasta 12 hilos

Comprimiendo objetos: 100% (3/3), listo.

Escribiendo objetos: 100% (3/3), 348 bytes | 348.00 KiB/s, listo.

Total 3 (delta 1), reusados 0 (delta 0), pack-reusados 0

remote: Resolving deltas: 100% (1/1), completed with 1 local object.

remote: 

remote: Create a pull request for 'feature/2-postre-tarta' on GitHub by visiting:

remote:      https\://github.com/tpaiu-invelon/git-kata-tpaiu/pull/new/feature/2-postre-tarta

remote: 

To https\://github.com/tpaiu-invelon/git-kata-tpaiu.git

 \* [new branch]      feature/2-postre-tarta -> feature/2-postre-tarta

rama 'feature/2-postre-tarta' configurada para rastrear 'origin/feature/2-postre-tarta'.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch main

Cambiado a rama 'main'

Tu rama está actualizada con 'origin/main'.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch -c feature/3-postre-helado

Cambiado a nueva rama 'feature/3-postre-helado'

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ nano menu.md 

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -am "Change dessert to vanilla ice cream"

[feature/3-postre-helado a9b8fd9] Change dessert to vanilla ice cream

 1 file changed, 1 insertion(+), 1 deletion(-)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git push -u origin feature/3-postre-helado

Username for 'https\://github.com': tpaiu-invelon

Password for 'https\://tpaiu-invelon\@github.com': 

Enumerando objetos: 5, listo.

Contando objetos: 100% (5/5), listo.

Compresión delta usando hasta 12 hilos

Comprimiendo objetos: 100% (3/3), listo.

Escribiendo objetos: 100% (3/3), 360 bytes | 360.00 KiB/s, listo.

Total 3 (delta 1), reusados 0 (delta 0), pack-reusados 0

remote: Resolving deltas: 100% (1/1), completed with 1 local object.

remote: 

remote: Create a pull request for 'feature/3-postre-helado' on GitHub by visiting:

remote:      https\://github.com/tpaiu-invelon/git-kata-tpaiu/pull/new/feature/3-postre-helado

remote: 

To https\://github.com/tpaiu-invelon/git-kata-tpaiu.git

 \* [new branch]      feature/3-postre-helado -> feature/3-postre-helado

rama 'feature/3-postre-helado' configurada para rastrear 'origin/feature/3-postre-helado'.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git push --force-with-lease

Username for 'https\://github.com': tpaiu-invelon

Password for 'https\://tpaiu-invelon\@github.com': 

Enumerando objetos: 5, listo.

Contando objetos: 100% (5/5), listo.

Compresión delta usando hasta 12 hilos

Comprimiendo objetos: 100% (3/3), listo.

Escribiendo objetos: 100% (3/3), 452 bytes | 452.00 KiB/s, listo.

Total 3 (delta 0), reusados 0 (delta 0), pack-reusados 0

To https\://github.com/tpaiu-invelon/git-kata-tpaiu.git

 + a9b8fd9...09e21bd feature/3-postre-helado -> feature/3-postre-helado (forced update)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git show HEAD

commit 09e21bdd177aec574e00e7487739d41af3bbed28 (HEAD -> feature/3-postre-helado, origin/feature/3-postre-helado)

Author: tpaiu-invelon \<tpaiu\@invelon.com>

Date:   Tue Nov 3 11:45:52 2026 +0100



    Arreglar el conflicto generado al hacer merge con las dos ramas.



diff --git a/menu.md b/menu.md

index bb849b2..b8fdcd5 100644

\--- a/menu.md

+++ b/menu.md

@@ -9,5 +9,8 @@

 - Pollo



 ## Postre

+<<<<<<< HEAD

 - Tarta de queso

+=======

+- Helado de vainilla

 - Crema de calabaza (vegana)

```















arreglar el conflicto generado al hacer merge con las dos ramas 

¿Qué significa HEAD en el conflicto? ¿Tu cambio o el de main? (

HEAD (<<<<<<< HEAD): Indica el inicio de tus cambios locales. Todo lo que esté entre esta línea y la línea de guiones (=======) pertenece a tu rama actual.

¿Por qué el push normal falló y necesitó --force-with-lease?¿Por qué usamos el segundo? 

Por qué al hacer el merge entre la rama main y  feature/2-postre-tarta y hacer un cambio sobre el archivo y después hacer otro merge centre la rama  rama main y  feature/3-postre-tarta y modificar la misma línea que se modificó en el   feature/2-postre-tarta  el push no sabe cual es correcta y cuál no por lo que necesitamos establecer nosotros cual usaremos lo que sale entre <<<<<<< HEAD y después hacer push --force-with-lease que lo que hace es comprueba antes de sobrescribir que nadie haya subido nuevos commits a la rama remota en GitHub. Si detecta cambios ajenos que no tienes en local, detiene la subida y evita que borres el trabajo de otros.

¿Qué diferencia hay entre --force y --force-with-lease?

**`--force` (`-f`):** Sobrescribe a la fuerza la rama en GitHub **sin comprobar nada**. Si un compañero de equipo subió cambios a esa misma rama mientras tú trabajabas, `--force` los borrará para siempre sin avisar.

**`--force-with-lease`:** Es la **alternativa segura**. Comprueba antes de sobrescribir que nadie haya subido nuevos commits a la rama remota en GitHub. Si detecta cambios ajenos que no tienes en local, detiene la subida y evita que borres el trabajo de otros.

Si te hubieras arrepentido a mitad del rebase, ¿cómo lo cancelas? (pista: git rebase --?????)

Con git rebase --abort

##  Misión 7 — merge vs rebase, visto en el grafo
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline --graph --all

\* 09e21bd (HEAD -> feature/3-postre-helado, origin/feature/3-postre-helado) Arreglar el conflicto generado al hacer merge con las dos ramas.

\*   704c97f (origin/main, origin/HEAD, main) Merge pull request #2 from tpaiu-invelon/feature/2-postre-tarta

|\  

\| \* e28145f (origin/feature/2-postre-tarta, feature/2-postre-tarta) Change dessert to cheesecake

|/  

\* 19fae3a Update README.md with editing note

\*   bdf4ae2 Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

|\  

\| \* a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

|/  

\* 01e3b43 Add base menu

\* ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 
```
¿Qué forma tiene la historia de la rama que **mergeaste** y cuál la de la que **rebaseaste**?

El *rebase* limpia el camino en local y el *merge* integra el trabajo públicamente sin riesgo.



¿Por qué NUNCA debes hacer rebase de una rama que comparten otras personas?

Si hacemos `rebase` en una rama compartida y fuerzas la subida (`push --force`), cambiaremos los cambios realizados por el compañero. Cuando otra persona intenten hacer `git pull` o `push`, su historial local ya no coincidirá con el del servidor, provocando **conflictos&#x20;**&#x65;n sus equipos.





## Misión 8 — Deshacer: revert, reset, reflog




```bash

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch main && git pull

Cambiado a rama 'main'

Tu rama está actualizada con 'origin/main'.

Ya está actualizado.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch -c sandbox/deshacer

Cambiado a nueva rama 'sandbox/deshacer'

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ echo "- Pizza con piña" >> menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -am "Add controversial pizza"

[sandbox/deshacer b5b317f] Add controversial pizza

 1 file changed, 1 insertion(+)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git revert HEAD

[sandbox/deshacer 324c294] Reapply "Add controversial pizza 2"

 1 file changed, 1 insertion(+)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

324c294 (HEAD -> sandbox/deshacer) Reapply "Add controversial pizza 2"

848f336 Revert "Add controversial pizza"

b5b317f Add controversial pizza

704c97f (origin/main, origin/HEAD, main) Merge pull request #2 from tpaiu-invelon/feature/2-postre-tarta

e28145f (origin/feature/2-postre-tarta, feature/2-postre-tarta) Change dessert to cheesecake

19fae3a Update README.md with editing note

bdf4ae2 Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

01e3b43 Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 
```
¿Desapareció el commit malo o hay **dos** commits ahora?

No hay **dos&#x20;**&#x63;ommits ahora 
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ echo "- Otro error" >> menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -am "Bad commit"

[sandbox/deshacer 9d7fd56] Bad commit

 1 file changed, 1 insertion(+)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git reset --soft HEAD\~1

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git status

En la rama sandbox/deshacer

Cambios a ser confirmados:

  (usa "git restore --staged \<archivo>..." para sacar del área de stage)

    modificados:     menu.md

¿Dónde están tus cambios: en staging, sin stagear, o perdidos?

**Están en el Staging Area&#xA0;**



tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

324c294 (HEAD -> sandbox/deshacer) Reapply "Add controversial pizza 2"

848f336 Revert "Add controversial pizza"

b5b317f Add controversial pizza

704c97f (origin/main, origin/HEAD, main) Merge pull request #2 from tpaiu-invelon/feature/2-postre-tarta

e28145f (origin/feature/2-postre-tarta, feature/2-postre-tarta) Change dessert to cheesecake

19fae3a Update README.md with editing note

bdf4ae2 Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

01e3b43 Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

324c294 (HEAD -> sandbox/deshacer) Reapply "Add controversial pizza 2"

848f336 Revert "Add controversial pizza"

b5b317f Add controversial pizza

704c97f (origin/main, origin/HEAD, main) Merge pull request #2 from tpaiu-invelon/feature/2-postre-tarta

e28145f (origin/feature/2-postre-tarta, feature/2-postre-tarta) Change dessert to cheesecake

19fae3a Update README.md with editing note

bdf4ae2 Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

01e3b43 Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git status

En la rama sandbox/deshacer

Cambios a ser confirmados:

  (usa "git restore --staged \<archivo>..." para sacar del área de stage)

&#x9;modificados:     menu.md



tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git reset --hard HEAD\~1

HEAD está ahora en 848f336 Revert "Add controversial pizza"

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

848f336 (HEAD -> sandbox/deshacer) Revert "Add controversial pizza"

b5b317f Add controversial pizza

704c97f (origin/main, origin/HEAD, main) Merge pull request #2 from tpaiu-invelon/feature/2-postre-tarta

e28145f (origin/feature/2-postre-tarta, feature/2-postre-tarta) Change dessert to cheesecake

19fae3a Update README.md with editing note

bdf4ae2 Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

01e3b43 Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git reflog

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git reset --hard 848f336

HEAD está ahora en 848f336 Revert "Add controversial pizza"

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

848f336 (HEAD -> sandbox/deshacer) Revert "Add controversial pizza"

b5b317f Add controversial pizza

704c97f (origin/main, origin/HEAD, main) Merge pull request #2 from tpaiu-invelon/feature/2-postre-tarta

e28145f (origin/feature/2-postre-tarta, feature/2-postre-tarta) Change dessert to cheesecake

19fae3a Update README.md with editing note

bdf4ae2 Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

01e3b43 Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 
```
revert vs reset: ¿cuál usas en una rama **compartida** y por qué?

Usa git revert, porque crea un commit nuevo que anula los cambios sin reescribir ni romper el historial que tus compañeros ya tienen descargado.

\--soft vs --mixed vs --hard: una frase cada uno.

**`--soft`:** Deshace el commit pero **mantiene las modificaciones en el Staging Area** (listas en verde para volver a commitear).

**`--mixed` (por defecto):** Deshace el commit y saca los cambios del Staging Area, pero **los conserva guardados en tu espacio de trabajo** (sin preparar, en rojo).

**`--hard`:** Deshace el commit y **borra de forma permanente** todas las modificaciones de tus archivos en el disco duro.

¿Qué es el reflog y cuánto tiempo guarda las cosas?

No, **nada que haya sido commiteado se pierde de forma inmediata**, ya que siempre se puede recuperar mediante su Hash usando `git reflog` hasta que venza el periodo de limpieza de Git.

## Misión 9 — stash: la interrupción

```bash

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch -c feature/4-bebidas

Cambiado a nueva rama 'feature/4-bebidas'

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ echo "## Bebidas" >> menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ echo "- Agua" >> menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch main

M    menu.md

Cambiado a rama 'main'

Tu rama está actualizada con 'origin/main'.

Git te deja o te bloquea?

Si git te permite cambiar de rama si no hay conflictos.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git stash

Directorio de trabajo y estado de índice WIP on main: 704c97f Merge pull request #2 from tpaiu-invelon/feature/2-postre-tarta guardados

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git status                      En la rama main

Tu rama está actualizada con 'origin/main'.



nada para hacer commit, el árbol de trabajo está limpio

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch main

Ya en 'main'

Tu rama está actualizada con 'origin/main'.



tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git add menu.md

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git commit -m "Add drinks section to the menu"

[feature/4-bebidas 08321af] Add drinks section to the menu

 1 file changed, 2 insertions(+)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git push -u origin feature/4-bebidas

Username for 'https\://github.com': tpaiu-invelon

Password for 'https\://tpaiu-invelon\@github.com': 

Enumerando objetos: 9, listo.

Contando objetos: 100% (9/9), listo.

Compresión delta usando hasta 12 hilos

Comprimiendo objetos: 100% (7/7), listo.

Escribiendo objetos: 100% (7/7), 803 bytes | 401.00 KiB/s, listo.

Total 7 (delta 2), reusados 0 (delta 0), pack-reusados 0

remote: Resolving deltas: 100% (2/2), completed with 1 local object.

remote: 

remote: Create a pull request for 'feature/4-bebidas' on GitHub by visiting:

remote:      https\://github.com/tpaiu-invelon/git-kata-tpaiu/pull/new/feature/4-bebidas

remote: 

To https\://github.com/tpaiu-invelon/git-kata-tpaiu.git

 \* [new branch]      feature/4-bebidas -> feature/4-bebidas

rama 'feature/4-bebidas' configurada para rastrear 'origin/feature/4-bebidas'.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 



tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git stash pop

No se encontraron entradas de stash.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git status 

En la rama feature/4-bebidas

Tu rama está actualizada con 'origin/feature/4-bebidas'.



nada para hacer commit, el árbol de trabajo está limpio

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 

Si hemos hecho los cambios.
```


¿Qué pasó exactamente al intentar cambiar de rama sin commitear?

Que hemos modificado un fichero mientras estábamos en la rama main no en la rama feature/4-bebidas.







`git stash pop` vs `git stash apply`: ¿Diferencia?

**`git stash pop`:** Recupera los cambios guardados y **los elimina permanentemente de la lista del stash**.

**`git stash apply`:** Recupera los cambios en tu espacio de trabajo pero **mantiene una copia guardada en la lista del stash** por si necesitas aplicarla en otra rama.



¿Dónde se guarda lo del stash?

En .git/refs/stash

## Misión 10 — cherry-pick: un commit suelto
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline feature/2-postre-tarta 

e28145f (origin/feature/2-postre-tarta, feature/2-postre-tarta) Change dessert to cheesecake

19fae3a Update README.md with editing note

bdf4ae2 Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

01e3b43 Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch -c sandbox/cherry main

Cambiado a nueva rama 'sandbox/cherry'

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 







tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git cherry-pick e28145f

En la rama sandbox/cherry

Estás realizando un cherry-picking en el commit e28145f.

  (todos los conflictos corregidos: ejecuta "git cherry-pick --continue")

  (usa "git cherry-pick --skip" para saltar este parche)

  (usa "git cherry-pick --abort" para cancelar la operación cherry-pick)



nada para hacer commit, el árbol de trabajo está limpio

El cherry-pick anterior ahora está vacío, posiblemente por un conflicto de resolución.

Si deseas realizar un commit de todas maneras, usa:



    git commit --allow-empty



Caso contrario, por favor usa 'git cherry-pick --skip'

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git log --oneline

704c97f (HEAD -> sandbox/cherry, origin/main, origin/HEAD, main) Merge pull request #2 from tpaiu-invelon/feature/2-postre-tarta

e28145f (origin/feature/2-postre-tarta, feature/2-postre-tarta) Change dessert to cheesecake

19fae3a Update README.md with editing note

bdf4ae2 Merge pull request #1 from tpaiu-invelon/feature/1-primeros-platos

a698ed4 (origin/feature/1-primeros-platos, feature/1-primeros-platos) Add starters section to the daily menu

01e3b43 Add base menu

ec45db7 Initial commit

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 
```




¿El hash del commit cherry-pickeado es el mismo que el original? ¿Por qué?

**No, el HASH no es el mismo.**

Un HASH en Git se calcula la fecha/hora exacta y **el HASH del commit padre anterior**. Como en la nueva rama el commit padre la fecha de aplicación cambia, Git genera un commit nuevo con un HASH completamente diferente.



¿Cuándo usarías cherry-pick en vez de merge? 

Se utiliza cuando necesitas **extraer una funcionalidad concreta sin traerte la rama entera** como podría ser rescatar un commit específico.

##  Misión 11 — .gitignore






```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ echo "SECRET_KEY=no-subas-esto" > .env

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git status 

En la rama sandbox/cherry

Estás realizando un cherry-picking en el commit e28145f.

  (todos los conflictos corregidos: ejecuta "git cherry-pick --continue")

  (usa "git cherry-pick --skip" para saltar este parche)

  (usa "git cherry-pick --abort" para cancelar la operación cherry-pick)



Archivos sin seguimiento:

  (usa "git add \<archivo>..." para incluirlo a lo que será confirmado)

    .env



no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$

Sí, `.env` aparece claramente en rojo



tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ echo ".env"   >> .gitignore

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ echo "venv/"  >> .gitignore

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git status 

En la rama sandbox/cherry

Estás realizando un cherry-picking en el commit e28145f.

  (todos los conflictos corregidos: ejecuta "git cherry-pick --continue")

  (usa "git cherry-pick --skip" para saltar este parche)

  (usa "git cherry-pick --abort" para cancelar la operación cherry-pick)



Archivos sin seguimiento:

  (usa "git add \<archivo>..." para incluirlo a lo que será confirmado)

    .gitignore



no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 

No por que esta en el .gitignore



tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git add .gitignore && git commit -m "Add gitignore rules"

[sandbox/cherry 1fbaf5c] Add gitignore rules

 Date: Tue Nov 3 11:43:24 2026 +0100

 1 file changed, 2 insertions(+)

 create mode 100644 .gitignore

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git rm --cached .env

fatal: ruta especificada '.env' no concordó con ningún archivo

```

¿Por qué .env nunca va al repo?

Por que el archivo .env en django se suele usar para  contiene las llaves como API_KEY, DB_PASS, que usa para encriptar y desencriptar si alguien clona el proyecto puede usar la llave para hacer peticiones por api todas las normas y protección implementada  no servirán de nada. 



**La trampa:** si un fichero YA está trackeado, añadirlo al .gitignore **no lo saca**. ¿Qué comando hace falta? (pista: git rm --??????)

git rm --cached .env

Si subes una contraseña por error y luego haces un commit borrándola, ¿está a salvo? **¿Por qué no?**

**Aunque hagas un commit borrando la contraseña, esta sigue estando 100% visible y accesible para cualquier persona que tenga acceso al repositorio si es público puede verlo cualquier persona.**



##  Misión 12 — Investigar





```
git log --oneline --graph --all --decorate
```







**Lo usaría para&#x20;**&#x70;oder mostrar el historial completo del proyecto en un gráfico tipo árbol.





```
git show <hash>
```





**Lo usaría para&#x20;**&#x6D;ostrar el los cambios exactos que se han introducido en un commit específico.



```
git diff main..feature/2-postre-tarta
```



Lo usaria para compara las diferencias exactas de código entre dos ramas antes de hacer un merge en este caso entre main y feature/2-postre-tarta



```
git blame menu.md
```

Lo usaría para mostrar que se modificó cada línea de un archivo y en qué commit se ha hecho hizo.



```
git log -p menu.md
```

Lo usaría para mostrar el historial de cambios y parches aplicados exclusivamente a un archivo.







**En la bitácora:** una frase por comando, un ejemplo de uso real  una frase no más de 10 - 20 palabras .







##  Misión 13 — Tag y Release
```bash
tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git switch main && git pull

Cambiado a rama 'main'

Tu rama está actualizada con 'origin/main'.

Ya está actualizado.

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git tag -a v1.0.0 -m "Git kata completed"

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ git push origin v1.0.0

Username for 'https\://github.com': tpaiu-invelon

Password for 'https\://tpaiu-invelon\@github.com': 

Enumerando objetos: 1, listo.

Contando objetos: 100% (1/1), listo.

Escribiendo objetos: 100% (1/1), 164 bytes | 164.00 KiB/s, listo.

Total 1 (delta 0), reusados 0 (delta 0), pack-reusados 0

To https\://github.com/tpaiu-invelon/git-kata-tpaiu.git

 \* [new tag]         v1.0.0 -> v1.0.0

tiberiupaiu\@TR-8PPBB:\~/Git_Kata/git-kata-tpaiu$ 

```

#### git tag v1.0.0 vs git tag -a v1.0.0 -m "...": ¿diferencia? (ligero vs anotado)



- **`git tag v1.0.0` (Tag Ligero / Lightweight):** Es simplemente un puntero o marcador fijo que apunta a un commit específico. No almacena información extra.
- **`git tag -a -m` (Tag Anotado / Annotated):** Crea un objeto completo en la base de datos de Git que guarda el mensaje de la versión, el autor, la fecha, la firma y su propio Hash. Es el estándar para versiones de producción.

#### ¿Por qué un tag y no el nombre de la rama para marcar una versión?



- **Las ramas son dinámicas:** Mueven su puntero cada vez que haces un nuevo commit.
- **Los tags son estáticos e inmutables:** Apuntan **para siempre a un commit concreto del pasado**, garantizando que esa versión publicada nunca cambiará aunque la rama `main` siga avanzando.

#### SemVer: has arreglado un bug → ¿v1.0.1, v1.1.0 o v2.0.0?

**Es el formato para indicar el número del patch que se ha realizado `v1.0.1`** como corrección de errores y bugs.

**Es el formato para indicar (`v1.1.0`) que se trata de una&#x20;**&#x66;uncionalidades nueva.

**Es el formato para indicar (`v1.1.0`)&#x20;**_Breaking changes._
