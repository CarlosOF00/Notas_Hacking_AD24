## Descripción 
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 7449`, but it doesn't speak English...

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.eTtg1PLtko
carlosof-picoctf@webshell:~$ cd /tmp/tmp.eTtg1PLtko/
carlosof-picoctf@webshell:/tmp/tmp.eTtg1PLtko$ nc mercury.picoctf.net 7449
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
102 
50 
100 
55 
99 
97 
102 
97 
125 
10 

carlosof-picoctf@webshell:/tmp/tmp.eTtg1PLtko$ nc mercury.picoctf.net 7449 > salida.txt

carlosof-picoctf@webshell:/tmp/tmp.eTtg1PLtko$ tr ' ' '\n' < salida.txt | awk '{printf "%c", $1}'
picoCTF{g00d_k1tty!_n1c3_k1tty!_f2d7cafa}
carlosof-picoctf@webshell:/tmp/tmp.eTtg1PLtko$ 
```


## Notas Adicionales
El comando `nc mercury.picoctf.net 7449 > salida.txt` utiliza `nc` (Netcat) para conectarse a un servidor en la red y redirige la salida de esa conexión a un archivo.

**`tr ' ' '\n' < salida.txt`**:
	- **`tr`**: `tr` es una utilidad de la línea de comandos que se usa para traducir o eliminar caracteres.
	- **`' '`**: Representa el espacio en blanco. Este es el carácter que se quiere reemplazar.
	- **`'\n'`**: Representa el carácter de nueva línea. Cada espacio en blanco se reemplaza por una nueva línea.
	- **`< salida.txt`**: Redirige el contenido del archivo `salida.txt` a la entrada estándar del comando `tr`. Es decir, `tr` toma el contenido de `salida.txt` y lo procesa.

## Referencias 
https://play.picoctf.org/practice/challenge/156
[Tr Command in Linux with Examples | Linuxize](https://linuxize.com/post/linux-tr-command/#:~:text=tr%20is%20a%20command-line%20utility%20in%20Linux%20and,to%20lowercase%2C%20and%20basic%20character%20replacing%20and%20removing.)
