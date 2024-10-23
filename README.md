<<<<<<< HEAD
# Entornos de Desarrollo: Repasando lo que sabemos de Git

## Creo el repositorio y lo clono:

```Code
pro@jpexposito-VirtualBox:~$ git clone https://github.com/nexphernandez/ejercicio-git-libro
Clonando en 'ejercicio-git-libro'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Recibiendo objetos: 100% (3/3), listo.
pro@jpexposito-VirtualBox:~$ cd ejercicio-git-libro/ 
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ ls -la
total 16
drwxrwxr-x  3 pro pro 4096 oct 14 00:33 .
drwxr-x--- 22 pro pro 4096 oct 14 00:32 ..
drwxrwxr-x  8 pro pro 4096 oct 14 00:33 .git
-rw-rw-r--  1 pro pro   21 oct 14 00:33 README.md
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ code .

```

## Ejercicio 1:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log
commit d22b24951cf408609fdda8ec0f3030bb595a5672 (HEAD -> main, origin/main, origin/HEAD)
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ mkdir capitulos
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > capitulos/capitulo
1.txt
Git es un sistema de control de versiones ideado por Linux Trovals.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "Capitulo1
 añadido."
[main 8114bc9] Capitulo1 añadido.
 2 files changed, 38 insertions(+), 1 deletion(-)
 rewrite README.md (100%)
 create mode 100644 capitulos/capitulo1.txt
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log
commit 8114bc9814037ad0589f487bd405217626f19a77 (HEAD -> main)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:43:00 2024 +0100

    Capitulo1 añadido.

commit d22b24951cf408609fdda8ec0f3030bb595a5672 (origin/main, origin/HEAD)
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit
```

## Ejercicio 2:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit "cambios real
izados."
error: ruta especificada 'cambios realizados.' no concordó con ningún archivo conocido por git
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "cambios realizados."
[main 12dbbfb] cambios realizados.
 1 file changed, 19 insertions(+)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > capitulos/capitulo
2.txt
El flujo de trabajo básico con Git consiste en:
 1- Hacer cambios en el repositorio.
 2- Añadir los cambios a la zona de intercambio temporal.
 3- Hacer un commit de los cambios.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git ad .
git: 'ad' no es un comando de git. Mira 'git --help'.

Los comandos más similares son
        add
        am
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "capitulo 
2 añadido."
En la rama main
Tu rama está adelantada a 'origin/main' por 2 commits.
  (usa "git push" para publicar tus commits locales)

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
        capitulos/capitulo2.txt

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git diff HEAD~2..HEAD
diff --git a/README.md b/README.md
index 9a06b52..17fa94e 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,56 @@
-# ejercicio-git-libro
\ No newline at end of file
+# Entornos de Desarrollo: Repasando lo que sabemos de Git
+
+## Creo el repositorio y lo clono:
+
+```Code
+pro@jpexposito-VirtualBox:~$ git clone https://github.com/nexphernandez/:
```

## Ejercicio 3:

```Code

pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > capitulos/capitulo
3.txt
Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add . 
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "capitulo 
3 añadido."
[main 7e49370] capitulo 3 añadido.
 3 files changed, 53 insertions(+)
 create mode 100644 capitulos/capitulo2.txt
 create mode 100644 capitulos/capitulo3.txt
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log
commit 7e49370761f2ec0678da2c498a2163114023ba80 (HEAD -> main)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:54:29 2024 +0100

    capitulo 3 añadido.

commit 12dbbfb5abd193c765574a5a63292be8bb4be866
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:45:02 2024 +0100

    cambios realizados.

commit 8114bc9814037ad0589f487bd405217626f19a77
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:43:00 2024 +0100

    Capitulo1 añadido.

commit d22b24951cf408609fdda8ec0f3030bb595a5672 (origin/main, origin/HEAD
)
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git diff <codigo hash de
 la primera version>..HEAD
zsh: no existe el archivo o el directorio: codigo
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git diff HEAD~2..HEAD
diff --git a/README.md b/README.md
index 081e097..e76532d 100644
--- a/README.md
+++ b/README.md
@@ -33,5 +33,72 @@ pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ mkdir capitulos
 pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > capitulos/capitulo
 1.txt
 Git es un sistema de control de versiones ideado por Linux Trovals.
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "Capitulo1
+ añadido."
+[main 8114bc9] Capitulo1 añadido.
+ 2 files changed, 38 insertions(+), 1 deletion(-)
+ rewrite README.md (100%)
+ create mode 100644 capitulos/capitulo1.txt
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log
+commit 8114bc9814037ad0589f487bd405217626f19a77 (HEAD -> main)
+Author: nexphernandez <nicolaseh3b1112@gmail.com>
+Date:   Mon Oct 14 00:43:00 2024 +0100
+
+    Capitulo1 añadido.
+
+commit d22b24951cf408609fdda8ec0f3030bb595a5672 (origin/main, origin/HEA
D)
+Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
+Date:   Thu Oct 10 18:00:34 2024 +0100
+
+    Initial commit
 ```
 
## Ejercicio 2:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit "cambios rea
l
+izados."
+error: ruta especificada 'cambios realizados.' no concordó con ningún ar
chivo conocido por git
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "cambios 
realizados."
+[main 12dbbfb] cambios realizados.
+ 1 file changed, 19 insertions(+)
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > capitulos/capitul
o
+2.txt
+El flujo de trabajo básico con Git consiste en:
+ 1- Hacer cambios en el repositorio.
+ 2- Añadir los cambios a la zona de intercambio temporal.
+ 3- Hacer un commit de los cambios.
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git ad .
+git: 'ad' no es un comando de git. Mira 'git --help'.
+
+Los comandos más similares son
+        add
+        am
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "capitulo
 
+2 añadido."
+En la rama main
+Tu rama está adelantada a 'origin/main' por 2 commits.
+  (usa "git push" para publicar tus commits locales)
+
+Archivos sin seguimiento:
+  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
+        capitulos/capitulo2.txt
+
+no hay nada agregado al commit pero hay archivos sin seguimiento present
es (usa "git add" para hacerles seguimiento)
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git diff HEAD~2..HEAD
+diff --git a/README.md b/README.md
+index 9a06b52..17fa94e 100644
+--- a/README.md
++++ b/README.md
+@@ -1 +1,56 @@
+-# ejercicio-git-libro
+\ No newline at end of file
++# Entornos de Desarrollo: Repasando lo que sabemos de Git
++
++## Creo el repositorio y lo clono:
++
++```Code
++pro@jpexposito-VirtualBox:~$ git clone https://github.com/nexphernandez
/:
+
```Code
\ No newline at end of file
diff --git a/capitulos/capitulo2.txt b/capitulos/capitulo2.txt
new file mode 100644
index 0000000..4abf557
--- /dev/null
+++ b/capitulos/capitulo2.txt
@@ -0,0 +1,4 @@
+El flujo de trabajo básico con Git consiste en:
+ 1- Hacer cambios en el repositorio.
+ 2- Añadir los cambios a la zona de intercambio temporal.
+ 3- Hacer un commit de los cambios.
diff --git a/capitulos/capitulo3.txt b/capitulos/capitulo3.txt
new file mode 100644
index 0000000..6e501ab
--- /dev/null
+++ b/capitulos/capitulo3.txt
@@ -0,0 +1 @@
+Git permite la creación de ramas lo que permite tener distintas versione
s del mismo proyecto y trabajar de manera simultanea en ellas.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ 
```


## Ejercicio 4:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > indice.txt
git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "Se crea e
l indice."
[main f35f7fe] Se crea el indice.
 2 files changed, 151 insertions(+)
 create mode 100644 indice.txt
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ echo "Indice de los capi
tulos, con conceptos avanzados de git" >> indice.txt
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit "Añadido el i
ndice."
error: ruta especificada 'Añadido el indice.' no concordó con ningún archivo conocido por git
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m"Añadido el indice."
[main 78eb6b0] Añadido el indice.
 1 file changed, 1 insertion(+), 1 deletion(-)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git annotate indice.txt
78eb6b08        (nexphernandez  2024-10-14 01:06:55 +0100       1)Indice de los capitulos, con conceptos avanzados de git
```
## Ejercicio 5:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git branch bibliografia
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git branch -av
  bibliografia        78eb6b0 Añadido el indice.
* main                78eb6b0 [adelante 5] Añadido el indice.
  remotes/origin/HEAD -> origin/main
  remotes/origin/main d22b249 Initial commit
```

## Ejercicio 6:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > capitulos/capitulo
4.txt
  En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[D^[[C^[[C^[[C
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git comit -m "capitulo.4
 añadido."
git: 'comit' no es un comando de git. Mira 'git --help'.

El comando más similar es
        commit
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "capitulo.4 añadido."
[main 0f1a97e] capitulo.4 añadido.
 2 files changed, 42 insertions(+), 5 deletions(-)
 create mode 100644 capitulos/capitulo4.txt
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log --garph --all --
online
fatal: argumento no reconocido: --garph
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log --garph --all --oneline
fatal: argumento no reconocido: --garph
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log --graph --all --oneline
* 0f1a97e (HEAD -> main) capitulo.4 añadido.
* 78eb6b0 (bibliografia) Añadido el indice.
* f35f7fe Se crea el indice.
* 7e49370 capitulo 3 añadido.
* 12dbbfb cambios realizados.
* 8114bc9 Capitulo1 añadido.
* d22b249 (origin/main, origin/HEAD) Initial commit
```
## Ejercicio 7:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git checkout bibliografi
a
error: Los cambios locales de los siguientes archivos serán sobrescritos por checkout:
        README.md
Por favor realice un commit con los cambios o un stash antes de cambiar ramas.
Abortando
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit "Cambios"
error: ruta especificada 'Cambios' no concordó con ningún archivo conocido por git
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m"Cambios"
[main b79314f] Cambios
 1 file changed, 32 insertions(+)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git checkout bibliografia      
Cambiado a rama 'bibliografia'
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > bibliografia.txt
Chacon, S. and Straub, B. Pro Git. Apress.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "Añadida p
rimera referencia bibliográfica."
[bibliografia 8c4fd67] Añadida primera referencia bibliográfica.
 1 file changed, 1 insertion(+)
 create mode 100644 bibliografia.txt
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log --graph --all --oneline
* 8c4fd67 (HEAD -> bibliografia) Añadida primera referencia bibliográfica.
| * b79314f (main) Cambios
| * 0f1a97e capitulo.4 añadido.
|/  
* 78eb6b0 Añadido el indice.
* f35f7fe Se crea el indice.
* 7e49370 capitulo 3 añadido.
* 12dbbfb cambios realizados.
* 8114bc9 Capitulo1 añadido.
* d22b249 (origin/main, origin/HEAD) Initial commit
```

## Ejercicio 8:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git checkout main      
Cambiado a rama 'main'
Tu rama está adelantada a 'origin/main' por 7 commits.
  (usa "git push" para publicar tus commits locales)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git merge bibliografia
Auto-fusionando README.md
CONFLICTO (contenido): Conflicto de fusión en README.md
Fusión automática falló; arregle los conflictos y luego realice un commit con el resultado.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git merge bibliografia
Auto-fusionando README.md
Merge made by the 'ort' strategy.
 README.md | 8 ++++----
 1 file changed, 4 insertions(+), 4 deletions(-)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log --graph --all --oneline
*   8a878c5 (HEAD -> main) Merge branch 'bibliografia'
|\  
| * d45a34d (bibliografia) Cambios
| * 8c4fd67 Añadida primera referencia bibliográfica.
* | f407bd0 (origin/main, origin/HEAD) Cambios
* | 40c296f Añadida primera referencia bibliográfica.
* | b79314f Cambios
* | 0f1a97e capitulo.4 añadido.
|/  
* 78eb6b0 Añadido el indice.
* f35f7fe Se crea el indice.
* 7e49370 capitulo 3 añadido.
* 12dbbfb cambios realizados.
* 8114bc9 Capitulo1 añadido.
* d22b249 Initial commit
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git branch -d bibliografia
Eliminada la rama bibliografia (era d45a34d).
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log --graph --all --oneline
*   8a878c5 (HEAD -> main) Merge branch 'bibliografia'
|\  
| * d45a34d Cambios
| * 8c4fd67 Añadida primera referencia bibliográfica.
* | f407bd0 (origin/main, origin/HEAD) Cambios
* | 40c296f Añadida primera referencia bibliográfica.
* | b79314f Cambios
* | 0f1a97e capitulo.4 añadido.
|/  
* 78eb6b0 Añadido el indice.
* f35f7fe Se crea el indice.
* 7e49370 capitulo 3 añadido.
* 12dbbfb cambios realizados.
* 8114bc9 Capitulo1 añadido.
* d22b249 Initial commit
```

## Ejercicio 9:

```Code
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git branch bibliografia           
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git checkout bibliografia
M       README.md
Cambiado a rama 'bibliografia'
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > bibliografia.txt   
Scott Chacon and Ben Straub. Pro Git. Apress.
Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -a -m "Añadida nueva ref
erencia bibliográfica."
[bibliografia 474a922] Añadida nueva referencia bibliográfica.
 2 files changed, 93 insertions(+), 1 deletion(-)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git checkout main        
Cambiado a rama 'main'
Tu rama está adelantada a 'origin/main' por 3 commits.
  (usa "git push" para publicar tus commits locales)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ cat > bibliografia.txt   
- Chacon, S. and Straub, B. Pro Git. Apress.
- Loeliger, J. and McCullough, M. Version control with Git. O'Reilly.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -a -m "Añadida nueva ref
erencia bibliográfica."
[main eaff202] Añadida nueva referencia bibliográfica.
 1 file changed, 2 insertions(+), 1 deletion(-)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git merge bibliografia
Auto-fusionando bibliografia.txt
CONFLICTO (contenido): Conflicto de fusión en bibliografia.txt
Fusión automática falló; arregle los conflictos y luego realice un commit con el resultado.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "Cambios"
U       bibliografia.txt
error: No es posible realizar un commit porque tienes archivos sin fusionar.
ayuda: Corrígelos en el árbol de trabajo y entonces usa 'git add/rm <archivo>',
ayuda: como sea apropiado, para marcar la resolución y realizar un commit.
fatal: Saliendo porque existe un conflicto sin resolver.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commmit -m "cambios"
git: 'commmit' no es un comando de git. Mira 'git --help'.

El comando más similar es
        commit
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "cambios" 
[main 9ed9dff] cambios
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git merge bibliografia  
Ya está actualizado.
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git nano bibliografia
git: 'nano' no es un comando de git. Mira 'git --help'.

Los comandos más similares son
        annotate
        daemon
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git nano bibliografia.txt
git: 'nano' no es un comando de git. Mira 'git --help'.

Los comandos más similares son
        annotate
        daemon
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ nano bibliografia.txt
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git nano bibliografia.txt
git: 'nano' no es un comando de git. Mira 'git --help'.

Los comandos más similares son
        annotate
        daemon
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ 
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git nano bibliografia    
git: 'nano' no es un comando de git. Mira 'git --help'.

Los comandos más similares son
        annotate
        daemon
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git commit -m "Cambios"
[main 1448407] Cambios
 1 file changed, 1 insertion(+), 1 deletion(-)
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git push
Enumerando objetos: 26, listo.
Contando objetos: 100% (26/26), listo.
Compresión delta usando hasta 4 hilos
Comprimiendo objetos: 100% (21/21), listo.
Escribiendo objetos: 100% (21/21), 3.16 KiB | 3.16 MiB/s, listo.
Total 21 (delta 9), reusados 0 (delta 0), pack-reusados 0
remote: Resolving deltas: 100% (9/9), completed with 1 local object.
To https://github.com/nexphernandez/ejercicio-git-libro
   f407bd0..1448407  main -> main
```

### Continuación en clase porque no sabia usar el nano.
```Code
pro@jpexposito-VirtualBox:~/Documentos/ejercicio-git-libro$ nano bibliogr
afia
pro@jpexposito-VirtualBox:~/Documentos/ejercicio-git-libro$ nano bibliografia.txt
pro@jpexposito-VirtualBox:~/Documentos/ejercicio-git-libro$ git commit -a
 -m "Solucionando conflicto bibliografía."
[main cfe3ef8] Solucionando conflicto bibliografía.
 1 file changed, 1 insertion(+)
pro@jpexposito-VirtualBox:~/Documentos/ejercicio-git-libro$ git log --gra
ph --all --oneline
* cfe3ef8 (HEAD -> main) Solucionando conflicto bibliografía.
* 9965ee5 (origin/main, origin/HEAD) Cambios
* 1448407 Cambios
*   9ed9dff cambios
|\  
| * 474a922 Añadida nueva referencia bibliográfica.
* | eaff202 Añadida nueva referencia bibliográfica.
|/  
*   8a878c5 Merge branch 'bibliografia'
|\  
| * d45a34d Cambios
| * 8c4fd67 Añadida primera referencia bibliográfica.
* | f407bd0 Cambios
* | 40c296f Añadida primera referencia bibliográfica.
* | b79314f Cambios
* | 0f1a97e capitulo.4 añadido.
|/  
* 78eb6b0 Añadido el indice.
* f35f7fe Se crea el indice.
* 7e49370 capitulo 3 añadido.
* 12dbbfb cambios realizados.
* 8114bc9 Capitulo1 añadido.
* d22b249 Initial commit
```

# Entornos de Desarrollo: Avanzando en Git "Creando tags (etiquetas)"

## Ejercicio 1: Etiquetar una versión.

```Code
pro@jpexposito-VirtualBox:~$ git clone https://github.com/nexphernandez/ejercicio-git-libro
Clonando en 'ejercicio-git-libro'...
remote: Enumerating objects: 68, done.
remote: Counting objects: 100% (68/68), done.
remote: Compressing objects: 100% (42/42), done.
remote: Total 68 (delta 24), reused 62 (delta 21), pack-reused 0 (from 0)
Recibiendo objetos: 100% (68/68), 12.46 KiB | 354.00 KiB/s, listo.
Resolviendo deltas: 100% (24/24), listo.
pro@jpexposito-VirtualBox:~$ cd ejercicio-git-libro
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ code .
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ ls -la
total 44
drwxrwxr-x  4 pro pro  4096 oct 17 18:12 .
drwxr-x--- 23 pro pro  4096 oct 17 18:12 ..
-rw-rw-r--  1 pro pro   306 oct 17 18:12 bibliografia.txt
drwxrwxr-x  2 pro pro  4096 oct 17 18:12 capitulos
drwxrwxr-x  8 pro pro  4096 oct 17 18:23 .git
-rw-rw-r--  1 pro pro	56 oct 17 18:12 indice.txt
-rw-rw-r--  1 pro pro 20373 oct 17 18:12 README.md
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ ls
bibliografia.txt  capitulos  indice.txt  README.md
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git branch
* main
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git tag
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git tag -a <1.0.0> -m "Se crea la version 1.0.0"
zsh: no existe el archivo o el directorio: 1.0.0
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git tag -a <1.0.0> -m "Se crea la version 1.0.0"
zsh: no existe el archivo o el directorio: 1.0.0
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git tag -a <1.0.0> -m "Se crea la version 1.0.0"
zsh: no existe el archivo o el directorio: 1.0.0
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git tag -a 1.0.0 -m "Se crea la version 1.0.0"
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git tag
1.0.0
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git push
Username for 'https://github.com': nexphernandez
Password for 'https://nexphernandez@github.com':
Everything up-to-date
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git push origin --tags
Username for 'https://github.com': nexphernandez
Password for 'https://nexphernandez@github.com':
Enumerando objetos: 1, listo.
Contando objetos: 100% (1/1), listo.
Escribiendo objetos: 100% (1/1), 177 bytes | 177.00 KiB/s, listo.
Total 1 (delta 0), reusados 0 (delta 0), pack-reusados 0
To https://github.com/nexphernandez/ejercicio-git-libro
 * [new tag]     	1.0.0 -> 1.0.0
pro@jpexposito-VirtualBox:~/ejercicio-git-libro$
```

## Ejercicio 2: Revertir un commit

```CODE
PS C:\Users\nico\Downloads\ejercicio-git-libro> cd capitulos
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> cd capitulo1
cd : No se encuentra la ruta de acceso 'C:\Users\nico\Down
loads\ejercicio-git-libro\capitulos\capitulo1' porque no   
+ ~~~~~~~~~~~~
  otFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.Powe  
   rShell.Commands.SetLocationCommand
 
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> echo Linea de texto temporal >> .\capitulo1.txt
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> dit commit -m "commit temporal"
dit : El término 'dit' no se reconoce como nombre de un 
cmdlet, función, archivo de script o programa ejecutable.  
correcta e inténtelo de nuevo.
En línea: 1 Carácter: 1
    + CategoryInfo          : ObjectNotFound: (dit:String  
   ) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException     
 
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git commit -m "commit temporal"
[main 49544b3] commit temporal
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git revert
usage: git revert [--[no-]edit] [-n] [-m <parent-number>] [-s] [-S[<keyid>]] <commit>...
   or: git revert (--continue | --skip | --abort | --quit) 

    --quit                end revert or cherry-pick sequence
    --continue            resume revert or cherry-pick sequence
    --abort               cancel revert or cherry-pick sequence
    --skip                skip current commit and continue 
    --[no-]cleanup <mode> how to strip spaces and #comments from message
    -n, --no-commit       don't automatically commit       
    --commit              opposite of --no-commit
    -e, --[no-]edit       edit the commit message
    -s, --[no-]signoff    add a Signed-off-by trailer      
    -m, --[no-]mainline <parent-number>
                          select mainline parent
    --[no-]rerere-autoupdate
                          update the index with reused conf
#
                          merge strategy
    -X, --[no-]strategy-option <option>
                          option for merge strategy        
    -S, --[no-]gpg-sign[=<key-id>]
                          GPG sign commit
    --[no-]reference      use the 'reference' format to refer to commits

PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git revert HEAD
[main 09f6662] Revert "commit temporal"
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos>
```

## Ejercicio 3: Aplicar cambios de otra rama con Cherry-pick

```CODE

```
```CODE
PS C:\Users\nico\Downloads\ejercicio-git-libro> cd capitulos
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> cd capitulo1
cd : No se encuentra la ruta de acceso 'C:\Users\nico\Down
loads\ejercicio-git-libro\capitulos\capitulo1' porque no   
+ ~~~~~~~~~~~~
  otFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.Powe  
   rShell.Commands.SetLocationCommand
 
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> echo Linea de texto temporal >> .\capitulo1.txt
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> dit commit -m "commit temporal"
dit : El término 'dit' no se reconoce como nombre de un 
cmdlet, función, archivo de script o programa ejecutable.  
correcta e inténtelo de nuevo.
En línea: 1 Carácter: 1
    + CategoryInfo          : ObjectNotFound: (dit:String  
   ) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException     
 
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git commit -m "commit temporal"
[main 49544b3] commit temporal
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git revert
usage: git revert [--[no-]edit] [-n] [-m <parent-number>] [-s] [-S[<keyid>]] <commit>...
   or: git revert (--continue | --skip | --abort | --quit) 

    --quit                end revert or cherry-pick sequence
    --continue            resume revert or cherry-pick sequence
    --abort               cancel revert or cherry-pick sequence
    --skip                skip current commit and continue 
    --[no-]cleanup <mode> how to strip spaces and #comments from message
    -n, --no-commit       don't automatically commit       
    --commit              opposite of --no-commit
    -e, --[no-]edit       edit the commit message
    -s, --[no-]signoff    add a Signed-off-by trailer      
    -m, --[no-]mainline <parent-number>
                          select mainline parent
    --[no-]rerere-autoupdate
                          update the index with reused conf
#
                          merge strategy
    -X, --[no-]strategy-option <option>
                          option for merge strategy        
    -S, --[no-]gpg-sign[=<key-id>]
                          GPG sign commit
    --[no-]reference      use the 'reference' format to refer to commits

PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git revert HEAD
[main 09f6662] Revert "commit temporal"
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos>
```

## Ejercicio 3: Aplicar cambios de otra rama con Cherry-pick

```CODE

<<<<<<< HEAD
```CODE
PS C:\Users\nico\Downloads\ejercicio-git-libro> cd capitulos
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> cd capitulo1
cd : No se encuentra la ruta de acceso 'C:\Users\nico\Down
loads\ejercicio-git-libro\capitulos\capitulo1' porque no   
+ ~~~~~~~~~~~~
  otFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.Powe  
   rShell.Commands.SetLocationCommand
 
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> echo Linea de texto temporal >> .\capitulo1.txt
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> dit commit -m "commit temporal"
dit : El término 'dit' no se reconoce como nombre de un 
cmdlet, función, archivo de script o programa ejecutable.  
correcta e inténtelo de nuevo.
En línea: 1 Carácter: 1
    + CategoryInfo          : ObjectNotFound: (dit:String  
   ) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException     
 
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git commit -m "commit temporal"
[main 49544b3] commit temporal
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git revert
usage: git revert [--[no-]edit] [-n] [-m <parent-number>] [-s] [-S[<keyid>]] <commit>...
   or: git revert (--continue | --skip | --abort | --quit) 

    --quit                end revert or cherry-pick sequence
    --continue            resume revert or cherry-pick sequence
    --abort               cancel revert or cherry-pick sequence
    --skip                skip current commit and continue 
    --[no-]cleanup <mode> how to strip spaces and #comments from message
    -n, --no-commit       don't automatically commit       
    --commit              opposite of --no-commit
    -e, --[no-]edit       edit the commit message
    -s, --[no-]signoff    add a Signed-off-by trailer      
    -m, --[no-]mainline <parent-number>
                          select mainline parent
    --[no-]rerere-autoupdate
                          update the index with reused conf
#
                          merge strategy
    -X, --[no-]strategy-option <option>
                          option for merge strategy        
    -S, --[no-]gpg-sign[=<key-id>]
                          GPG sign commit
    --[no-]reference      use the 'reference' format to refer to commits

PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos> git revert HEAD
[main 09f6662] Revert "commit temporal"
 1 file changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro\capitulos>
```

## Ejercicio 3: Aplicar cambios de otra rama con Cherry-pick

```CODE
commit 49544b3f8c18de52ffd6619fe7695f781378727e
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:11:48 2024 +0100

    commit temporal

commit d7c3847fccf483e104b653554cc43a709bdccf92
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:04:18 2024 +0100

    Ejercicio1

commit 93d43be9dc7909d5af311ec2d7841b851b639d29 (tag: 1.0.0)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 16:01:09 2024 +0100

    Modificaciones en el README

commit cfe3ef8d60a676073b53a1b2a04f4f2f0fa9dabb
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 15:57:13 2024 +0100

    Solucionando conflicto bibliografía.

commit 9965ee5f03d6fa66a2af02d492c318de383629e0
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 02:05:17 2024 +0100

    Cambios

commit 144840787a600c4fd80e6bbb6a01c320028c9b81
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 02:02:52 2024 +0100

    Cambios

commit 9ed9dffe58afd7e4d784334ec061e3affcca71f1
Merge: eaff202 474a922
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:49:13 2024 +0100

    cambios

commit eaff20241a61354969dc3f4d7259b83caac4af51
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:47:40 2024 +0100

    Añadida nueva referencia bibliográfica.

commit 474a922bf8ed4e74fcf2ad984fdfde0b5c4f14e9
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:44:43 2024 +0100

    Añadida nueva referencia bibliográfica.

commit 8a878c5380617463b9baf7b65e9726e5f081c0ff
Merge: f407bd0 d45a34d
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:35:28 2024 +0100

    Merge branch 'bibliografia'

commit f407bd08a953da117aaa98752a3ed593e683a4b8
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:28:40 2024 +0100

    Cambios

commit 40c296f69d9951446e3828f7f8e301eb3534e950
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:24:47 2024 +0100

    Añadida primera referencia bibliográfica.

commit d45a34d2b281ee901fd8893113cf4df02f23f668
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:28:40 2024 +0100

    Cambios

commit 8c4fd67e366bea9a794b61a25cd84fc9f66000d4
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:24:47 2024 +0100

    Añadida primera referencia bibliográfica.

commit b79314ffaf320a62845817757bec7e03cd0f492e
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:22:58 2024 +0100

    Cambios

commit 0f1a97ea0946dfc14789c1c22c7338182a8d60d9
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:18:05 2024 +0100

    capitulo.4 añadido.

commit 78eb6b082d172b4b01476148e95fbfdcb9c30762
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:06:55 2024 +0100

    Añadido el indice.

commit f35f7fe2af38d8ada1537d677a6c750958a61a74
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:04:17 2024 +0100

    Se crea el indice.

commit 7e49370761f2ec0678da2c498a2163114023ba80
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:54:29 2024 +0100

    capitulo 3 añadido.

commit 12dbbfb5abd193c765574a5a63292be8bb4be866
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:45:02 2024 +0100

    cambios realizados.

commit 8114bc9814037ad0589f487bd405217626f19a77
Author: nexphernandez <nicolaseh3b1112@gmail.com>
    Capitulo1 añadido.

commit d22b24951cf408609fdda8ec0f3030bb595a5672
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick d22b24951cf408609fdda8ec0f3030bb595a5672
Auto-merging README.md
CONFLICT (add/add): Merge conflict in README.md
error: could not apply d22b249... Initial commit
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
-pick",
hint: run "git cherry-pick --abort".
flict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkout nueva-funcionalida
error: pathspec 'nueva-funcionalida' did not match any file(s) known to git
PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkout nueva-funcionalidad
error: Merging is not possible because you have unmerged fihint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit. 
fatal: Exiting because of an unresolved conflict.
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --abort
PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkout nueva-funcionalidad
Switched to branch 'nueva-funcionalidad'
PS C:\Users\nico\Downloads\ejercicio-git-libro> git log    
commit 8153388608c4a8f81cc12dd4446a75a06333f1b8 (HEAD -> nueva-funcionalidad)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 22:22:24 2024 +0100

    Se añade capitulo 5

commit 9458af88019d4f49765ae0b09afdcf916cbac6cf (origin/main, origin/HEAD, main)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    Añado ejercicio2

commit 09f66627968238aacdddfb29b074ecc17338797d
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:14:11 2024 +0100

    Revert "commit temporal"

    This reverts commit 49544b3f8c18de52ffd6619fe7695f781378727e.

commit 49544b3f8c18de52ffd6619fe7695f781378727e
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:11:48 2024 +0100

    commit temporal

commit d7c3847fccf483e104b653554cc43a709bdccf92
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:04:18 2024 +0100

    Ejercicio1

commit 93d43be9dc7909d5af311ec2d7841b851b639d29 (tag: 1.0.0)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 16:01:09 2024 +0100

    Modificaciones en el README

commit cfe3ef8d60a676073b53a1b2a04f4f2f0fa9dabb
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 15:57:13 2024 +0100

    Solucionando conflicto bibliografía.

commit 9965ee5f03d6fa66a2af02d492c318de383629e0
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 02:05:17 2024 +0100

    Cambios

commit 144840787a600c4fd80e6bbb6a01c320028c9b81
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 02:02:52 2024 +0100

    Cambios

commit 9ed9dffe58afd7e4d784334ec061e3affcca71f1
Merge: eaff202 474a922
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:49:13 2024 +0100

    cambios

commit eaff20241a61354969dc3f4d7259b83caac4af51
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:47:40 2024 +0100

    Añadida nueva referencia bibliográfica.

commit 474a922bf8ed4e74fcf2ad984fdfde0b5c4f14e9
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:44:43 2024 +0100

    Añadida nueva referencia bibliográfica.

commit 8a878c5380617463b9baf7b65e9726e5f081c0ff
Merge: f407bd0 d45a34d
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:35:28 2024 +0100

    Merge branch 'bibliografia'

commit f407bd08a953da117aaa98752a3ed593e683a4b8
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:28:40 2024 +0100

    Cambios

commit 40c296f69d9951446e3828f7f8e301eb3534e950
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:24:47 2024 +0100

    Añadida primera referencia bibliográfica.

commit d45a34d2b281ee901fd8893113cf4df02f23f668
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:28:40 2024 +0100

    Cambios

commit 8c4fd67e366bea9a794b61a25cd84fc9f66000d4
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:24:47 2024 +0100

    Añadida primera referencia bibliográfica.

commit b79314ffaf320a62845817757bec7e03cd0f492e
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:22:58 2024 +0100

    Cambios

commit 0f1a97ea0946dfc14789c1c22c7338182a8d60d9
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:18:05 2024 +0100

    capitulo.4 añadido.

commit 78eb6b082d172b4b01476148e95fbfdcb9c30762
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:06:55 2024 +0100

    Añadido el indice.

commit f35f7fe2af38d8ada1537d677a6c750958a61a74
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:04:17 2024 +0100

    Se crea el indice.

commit 7e49370761f2ec0678da2c498a2163114023ba80
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:54:29 2024 +0100

    capitulo 3 añadido.

commit 12dbbfb5abd193c765574a5a63292be8bb4be866
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:45:02 2024 +0100

    cambios realizados.

commit 8114bc9814037ad0589f487bd405217626f19a77
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:43:00 2024 +0100
    Capitulo1 añadido.

commit d22b24951cf408609fdda8ec0f3030bb595a5672
om>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit
PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick d22b24951cf408609fdda8ec0f3030bb595a5672
Auto-merging README.md
CONFLICT (add/add): Merge conflict in README.md
error: could not apply d22b249... Initial commit
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
hint: run "git cherry-pick --abort".
hint: Disable this message with "git config advice.mergeConflict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .  
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit 
-m "Cambios"
[main 523b7d2] Cambios
 Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
 Date: Thu Oct 10 18:00:34 2024 +0100
flict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .  
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit 
-m "Cambios"
[main 523b7d2] Cambios
 Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
 Date: Thu Oct 10 18:00:34 2024 +0100
[main 523b7d2] Cambios
 Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
 Date: Thu Oct 10 18:00:34 2024 +0100
 Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
 Date: Thu Oct 10 18:00:34 2024 +0100
PS C:\Users\nico\Downloads\ejercicio-git-libro>








Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 459 bytes | 459.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/nexphernandez/ejercicio-git-libro
Already on 'main'
Your branch is up to date with 'origin/main'.
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .    
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
error: pathspec '-' did not match any file(s) known to git
error: pathspec 'm' did not match any file(s) known to git
error: pathspec 'Cambios' did not match any file(s) known to git
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Aborting
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit - m "cambios"
error: pathspec '-' did not match any file(s) known to git
error: pathspec 'm' did not match any file(s) known to git
error: pathspec 'cambios' did not match any file(s) known to git
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit -m "cambios" 
[main dc79655] cambios
 1 file changed, 4 insertions(+), 1 deletion(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkout nueva-funcionalidad
Switched to branch 'nueva-funcionalidad'
PS C:\Users\nico\Downloads\ejercicio-git-libro> git log
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 22:22:24 2024 +0100


commit 9458af88019d4f49765ae0b09afdcf916cbac6cf
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick 9458af88019d4f49765ae0b09afdcf916cbac6cf
Auto-merging README.md
error: could not apply 9458af8... Añado ejercicio2
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: Disable this message with "git config advice.mergeConflict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --continue
>> 
U       README.md
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit -m "cambios"
[main e73dfb2] cambios
 Date: Wed Oct 23 18:21:05 2024 +0100
 1 file changed, 7 deletions(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --continue
>> 
error: no cherry-pick or revert in progress
fatal: cherry-pick failed
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick 9458af88019d4f49765ae0b09afdcf916cbac6cf
Auto-merging README.md

~

~
error: could not apply 9458af8... Añado ejercicio2
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
hint: run "git cherry-pick --abort".
hint: Disable this message with "git config advice.mergeConflict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --continue
>>
hint: Waiting for your editor to close the file...
[No se ha escrito nada al disco desde el último cambio]

Pulse INTRO o escriba una orden para continuar
[No se ha escrito nada al disco desde el último cambio]

Pulse INTRO o escriba una orden para continuar
Aborting commit due to empty commit message.
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --abort
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick 9458af88019d4f49765ae0b09afdcf916cbac6cf
Auto-merging README.md
error: could not apply 9458af8... Añado ejercicio2
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: run "git cherry-pick --abort".
hint: Disable this message with "git config advice.mergeConflict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --continue
>> 
[main c77db0d] Añado ejercicio2
 Date: Wed Oct 23 18:21:05 2024 +0100
 1 file changed, 60 insertions(+)
PS C:\Users\nico\Downloads\ejercicio-git-libro> git update-ref -d CHERRY_PICK_HEAD
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --continue        
>>
error: no cherry-pick or revert in progress
fatal: cherry-pick failed
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick 9458af88019d4f49765ae0b09afdcf916cbac6cf
error: could not apply 9458af8... Añado ejercicio2
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit "cambios"
fatal: cannot do a partial commit during a cherry-pick.
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit -m "cambios"
[main 42ef983] cambios
 Date: Wed Oct 23 18:21:05 2024 +0100
 1 file changed, 3 insertions(+)
PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkout main
Already on 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)
Counting objects: 100% (14/14), done.
Delta compression using up to 24 threads
Compressing objects: 100% (12/12), done.
Writing objects: 100% (12/12), 1.51 KiB | 1.51 MiB/s, done.
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To https://github.com/nexphernandez/ejercicio-git-libro
   523b7d2..42ef983  main -> main
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit -m "cambios"
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick 9458af88019d4f49765ae0b09afdcf916cbac6cf
Auto-merging README.md
error: could not apply 9458af8... Añado ejercicio2
hint: After resolving the conflicts, mark them with
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
hint: Disable this message with "git config advice.mergeConflict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --abort
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --abort
error: no cherry-pick or revert in progress
fatal: cherry-pick failed
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit -m "cambios"
[main 7078c24] cambios
 1 file changed, 2 deletions(-)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 24 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 381 bytes | 381.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/nexphernandez/ejercicio-git-libro
   42ef983..7078c24  main -> main
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick d22b249
Auto-merging README.md
error: could not apply d22b249... Initial commit
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
hint: run "git cherry-pick --abort".
hint: Disable this message with "git config advice.mergeConflict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --continue
>> 
error: no cherry-pick or revert in progress
fatal: cherry-pick failed
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick 9458af88019d4f49765ae0b09afdcf916cbac6cf
CONFLICT (content): Merge conflict in README.md
error: could not apply 9458af8... Añado ejercicio2
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
hint: run "git cherry-pick --abort".
hint: Disable this message with "git config advice.mergeConflict false"
Already on 'main'
Your branch is up to date with 'origin/main'.
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit -m "cambios"
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --continue
>>
error: no cherry-pick or revert in progress
fatal: cherry-pick failed
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick 9458af88019d4f49765ae0b09afdcf916cbac6cf
k --skip".
-pick",
hint: run "git cherry-pick --abort".
hint: Disable this message with "git config advice.mergeConflict false"
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-k --skip".pick --skip                                                -pick",
PS C:\Users\nico\Downloads\ejercicio-git-libro> git push origin main                                                  flict false"
Everything up-to-date                                      pick --skip
PS C:\Users\nico\Downloads\ejercicio-git-libro> git log    
commit 6a5cb22e6473b74d75544d34abcaec284a1fa936 (HEAD -> main, origin/main, origin/HEAD)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    Añado ejercicio2

commit 579c975dd288ca1835be21ed15090f71a3e53a66
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit

commit 7078c24abe2e4e776b5bf6c304cdec048673830a
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 23:10:47 2024 +0100

    cambios

commit 42ef9837ea0849bf6c603a7bebd5a0932a09dcb1
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    cambios

commit c77db0d4aa4bb69aff22af2cacda1af4f3b07d40
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    Añado ejercicio2

commit e73dfb277fd3dbac409eac629fc9d66d7ca17b8c
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    cambios

commit dc796557ce0f3fff8dac1b8ab9a34e621e4d5378
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 22:45:26 2024 +0100

    cambios

commit 523b7d2449e8f36126c8c1a36fc3bd6a0734930c
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Cambios

commit 9458af88019d4f49765ae0b09afdcf916cbac6cf
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    Añado ejercicio2

commit 09f66627968238aacdddfb29b074ecc17338797d
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:14:11 2024 +0100

    Revert "commit temporal"

    This reverts commit 49544b3f8c18de52ffd6619fe7695f781378727e.

commit 49544b3f8c18de52ffd6619fe7695f781378727e
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:11:48 2024 +0100

    commit temporal

commit d7c3847fccf483e104b653554cc43a709bdccf92
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:04:18 2024 +0100

    Ejercicio1

commit 93d43be9dc7909d5af311ec2d7841b851b639d29 (tag: 1.0.0)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 16:01:09 2024 +0100

    Modificaciones en el README

commit cfe3ef8d60a676073b53a1b2a04f4f2f0fa9dabb
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 15:57:13 2024 +0100

    Solucionando conflicto bibliografía.

commit 9965ee5f03d6fa66a2af02d492c318de383629e0
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 02:05:17 2024 +0100

    Cambios

commit 144840787a600c4fd80e6bbb6a01c320028c9b81
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 02:02:52 2024 +0100

    Cambios

commit 9ed9dffe58afd7e4d784334ec061e3affcca71f1
Merge: eaff202 474a922
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:49:13 2024 +0100

    cambios

commit eaff20241a61354969dc3f4d7259b83caac4af51
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:47:40 2024 +0100

    Añadida nueva referencia bibliográfica.

commit 474a922bf8ed4e74fcf2ad984fdfde0b5c4f14e9
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:44:43 2024 +0100

    Añadida nueva referencia bibliográfica.

commit 8a878c5380617463b9baf7b65e9726e5f081c0ff
Merge: f407bd0 d45a34d
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:35:28 2024 +0100

    Merge branch 'bibliografia'

commit f407bd08a953da117aaa98752a3ed593e683a4b8
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:28:40 2024 +0100

    Cambios

commit 40c296f69d9951446e3828f7f8e301eb3534e950
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:24:47 2024 +0100

    Añadida primera referencia bibliográfica.

commit d45a34d2b281ee901fd8893113cf4df02f23f668
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:28:40 2024 +0100

    Cambios

commit 8c4fd67e366bea9a794b61a25cd84fc9f66000d4
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:24:47 2024 +0100

    Añadida primera referencia bibliográfica.

commit b79314ffaf320a62845817757bec7e03cd0f492e
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:22:58 2024 +0100

    Cambios

commit 0f1a97ea0946dfc14789c1c22c7338182a8d60d9
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:18:05 2024 +0100

    capitulo.4 añadido.

commit 78eb6b082d172b4b01476148e95fbfdcb9c30762
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:06:55 2024 +0100

    Añadido el indice.

commit f35f7fe2af38d8ada1537d677a6c750958a61a74
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:04:17 2024 +0100

    Se crea el indice.

commit 7e49370761f2ec0678da2c498a2163114023ba80
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:54:29 2024 +0100

    capitulo 3 añadido.

commit 12dbbfb5abd193c765574a5a63292be8bb4be866
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:45:02 2024 +0100

    cambios realizados.

commit 8114bc9814037ad0589f487bd405217626f19a77
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:43:00 2024 +0100

    Capitulo1 añadido.
commit d22b24951cf408609fdda8ec0f3030bb595a5672
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit
PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkout nueva-funcionalidad
Switched to branch 'nueva-funcionalidad'
PS C:\Users\nico\Downloads\ejercicio-git-libro> git log    
commit 8153388608c4a8f81cc12dd4446a75a06333f1b8 (HEAD -> nueva-funcionalidad)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 22:22:24 2024 +0100


commit 9458af88019d4f49765ae0b09afdcf916cbac6cf
PS C:\Users\nico\Downloads\ejercicio-git-libro> git checkouSwitched to branch 'main'
Your branch is up to date with 'origin/main'.
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick --skip
fatal: cherry-pick failed
PS C:\Users\nico\Downloads\ejercicio-git-libro>
PS C:\Users\nico\Downloads\ejercicio-git-libro>
PS C:\Users\nico\Downloads\ejercicio-git-libro> git cherry-pick 8153388608c4a8f81cc12dd4446a75a06333f1b8
[main 6529672] Se añade capitulo 5
 Date: Wed Oct 23 22:22:24 2024 +0100
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 Capitulo5.txt
PS C:\Users\nico\Downloads\ejercicio-git-libro> git log    
commit 65296720abb4d584622baa807febdd2ce3b03fef (HEAD -> main)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 22:22:24 2024 +0100

    Se añade capitulo 5

commit 6a5cb22e6473b74d75544d34abcaec284a1fa936 (origin/main, origin/HEAD)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    Añado ejercicio2

commit 579c975dd288ca1835be21ed15090f71a3e53a66
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit

commit 7078c24abe2e4e776b5bf6c304cdec048673830a
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 23:10:47 2024 +0100

    cambios

commit 42ef9837ea0849bf6c603a7bebd5a0932a09dcb1
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    cambios

commit c77db0d4aa4bb69aff22af2cacda1af4f3b07d40
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    Añado ejercicio2

commit e73dfb277fd3dbac409eac629fc9d66d7ca17b8c
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    cambios

commit dc796557ce0f3fff8dac1b8ab9a34e621e4d5378
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 22:45:26 2024 +0100

    cambios

commit 523b7d2449e8f36126c8c1a36fc3bd6a0734930c
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Cambios

commit 9458af88019d4f49765ae0b09afdcf916cbac6cf
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:21:05 2024 +0100

    Añado ejercicio2

commit 09f66627968238aacdddfb29b074ecc17338797d
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:14:11 2024 +0100

    Revert "commit temporal"

    This reverts commit 49544b3f8c18de52ffd6619fe7695f781378727e.

commit 49544b3f8c18de52ffd6619fe7695f781378727e
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:11:48 2024 +0100

    commit temporal

commit d7c3847fccf483e104b653554cc43a709bdccf92
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Wed Oct 23 18:04:18 2024 +0100

    Ejercicio1

commit 93d43be9dc7909d5af311ec2d7841b851b639d29 (tag: 1.0.0)
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 16:01:09 2024 +0100

    Modificaciones en el README

commit cfe3ef8d60a676073b53a1b2a04f4f2f0fa9dabb
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 15:57:13 2024 +0100

    Solucionando conflicto bibliografía.

commit 9965ee5f03d6fa66a2af02d492c318de383629e0
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 02:05:17 2024 +0100

    Cambios

commit 144840787a600c4fd80e6bbb6a01c320028c9b81
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 02:02:52 2024 +0100

    Cambios

commit 9ed9dffe58afd7e4d784334ec061e3affcca71f1
Merge: eaff202 474a922
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:49:13 2024 +0100

    cambios

commit eaff20241a61354969dc3f4d7259b83caac4af51
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:47:40 2024 +0100

    Añadida nueva referencia bibliográfica.

commit 474a922bf8ed4e74fcf2ad984fdfde0b5c4f14e9
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:44:43 2024 +0100

    Añadida nueva referencia bibliográfica.

commit 8a878c5380617463b9baf7b65e9726e5f081c0ff
Merge: f407bd0 d45a34d
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:35:28 2024 +0100

    Merge branch 'bibliografia'

commit f407bd08a953da117aaa98752a3ed593e683a4b8
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:28:40 2024 +0100

    Cambios

commit 40c296f69d9951446e3828f7f8e301eb3534e950
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:24:47 2024 +0100

    Añadida primera referencia bibliográfica.

commit d45a34d2b281ee901fd8893113cf4df02f23f668
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:28:40 2024 +0100

    Cambios

commit 8c4fd67e366bea9a794b61a25cd84fc9f66000d4
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:24:47 2024 +0100

    Añadida primera referencia bibliográfica.

commit b79314ffaf320a62845817757bec7e03cd0f492e
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:22:58 2024 +0100

    Cambios

commit 0f1a97ea0946dfc14789c1c22c7338182a8d60d9
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:18:05 2024 +0100

    capitulo.4 añadido.

commit 78eb6b082d172b4b01476148e95fbfdcb9c30762
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:06:55 2024 +0100

    Añadido el indice.

commit f35f7fe2af38d8ada1537d677a6c750958a61a74
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 01:04:17 2024 +0100

    Se crea el indice.

commit 7e49370761f2ec0678da2c498a2163114023ba80
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:54:29 2024 +0100

    capitulo 3 añadido.

commit 12dbbfb5abd193c765574a5a63292be8bb4be866
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:45:02 2024 +0100

    cambios realizados.

commit 8114bc9814037ad0589f487bd405217626f19a77
Author: nexphernandez <nicolaseh3b1112@gmail.com>
Date:   Mon Oct 14 00:43:00 2024 +0100

    Capitulo1 añadido.

commit d22b24951cf408609fdda8ec0f3030bb595a5672
Author: Nicolas Exposito Hernandez <nicolaseh3b1112@gmail.com>
Date:   Thu Oct 10 18:00:34 2024 +0100

    Initial commit
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit -m " Consigo hacer el git cherry pick"
[main 731b409]  Consigo hacer el git cherry pick
 1 file changed, 3 deletions(-)
PS C:\Users\nico\Downloads\ejercicio-git-libro> git push
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 24 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 752 bytes | 752.00 KiB/s, done.
Total 6 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/nexphernandez/ejercicio-git-libro
   6a5cb22..731b409  main -> main
PS C:\Users\nico\Downloads\ejercicio-git-libro>
```

## Ejercicio 4: Comparar ramas:

```Code
PS C:\Users\nico\Downloads\ejercicio-git-libro> git add .  
PS C:\Users\nico\Downloads\ejercicio-git-libro> git commit 
-m "Cambios"
[main 89acf4e] Cambios
 1 file changed, 984 insertions(+)
PS C:\Users\nico\Downloads\ejercicio-git-libro> git diff
diff --git a/README.md b/README.md
index ad96ff5..90723a0 100644
--- a/README.md
+++ b/README.md
@@ -1752,3 +1752,4 @@ PS C:\Users\nico\Downloads\ejercicio-git-libro>
 
 ## Ejercicio 4: Comparar ramas:

+Cambio realizado para el ejecicio 4
\ No newline at end of file
PS C:\Users\nico\Downloads\ejercicio-git-libro> 
```