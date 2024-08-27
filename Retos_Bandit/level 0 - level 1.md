
## Objetivo 
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
## Datos de Acceso al Nivel
User: bandit0
Password:
## Solución
```
C:\Users\Carlos>ssh bandit0@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit0@bandit.labs.overthewire.org's password:

bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

bandit0@bandit:~$
```
## Notas Adicionales

- **ls (list)**:
    - **Descripción**: Muestra el contenido de un directorio.
    - **Uso**: Utilizado para listar archivos y directorios en el directorio actual o en un directorio especificado.
    - 
- **cd (change directory)**:
    - **Descripción**: Cambia el directorio actual de trabajo.
    - **Uso**: Se usa para navegar entre diferentes directorios en el sistema de archivos.
    
- **cat (concatenate)**:
    - **Descripción**: Muestra el contenido de uno o varios archivos en la salida estándar.
    - **Uso**: Utilizado para ver rápidamente el contenido de un archivo de texto o concatenar archivos y mostrar su contenido combinado.
    
- **file**:
    - **Descripción**: Determina el tipo de un archivo.
    - **Uso**: Utilizado para identificar el tipo de archivo, especialmente útil cuando la extensión del archivo no es clara o puede estar cambiada.
    
- **du (disk usage)**:
    - **Descripción**: Muestra el espacio en disco usado por archivos y directorios.
    - **Uso**: Utilizado para verificar cuánto espacio en disco está ocupando un archivo o un directorio. Muy útil para gestión de almacenamiento.
    
- **find**:
    - **Descripción**: Busca archivos y directorios en un árbol de directorios.
    - **Uso**: Utilizado para buscar archivos o directorios específicos basados en criterios como nombre, tamaño, permisos, etc.

## Referencias 
https://manpages.ubuntu.com/manpages/noble/man1/

