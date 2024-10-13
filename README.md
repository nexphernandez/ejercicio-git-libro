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
```

