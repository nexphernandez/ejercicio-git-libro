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
 
+## Ejercicio 2:
+
+```Code
+pro@jpexposito-VirtualBox:~/ejercicio-git-libro$ git add .
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
+```
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