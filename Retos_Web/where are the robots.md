## Descripción 
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/60915/` ([link](https://jupiter.challenges.picoctf.org/problem/60915/)) or http://jupiter.challenges.picoctf.org:60915

## Datos de Acceso al Nivel
user: 
password:

## Solución 1
- A la URL le agregamos robots.txt
- Nos dará una dirección que se encuentra oculta para nosotros. En este caso (Disallow: /8028f.html).
- La copiamos y cambiamos por robots.txt, lo que nos redirige a otra pagina que contiene la bandera.
-  picoCTF{ca1cu1at1ng_Mach1n3s_8028f}`

## Solución 2
```bash
carlosof-picoctf@webshell:~$ curl http://jupiter.challenges.picoctf.org:60915
<!doctype html>
<html>
  <head>
    <title>Welcome</title>
    <link href="https://fonts.googleapis.com/css?family=Monoton|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>

  <body>
    <div class="container">
      <header>
        <h1>Welcome</h1>
      </header>
      <div class="content">
        <p>Where are the robots?</p>
      </div>
      <footer></footer>
    </div>
  </body>
</html>
carlosof-picoctf@webshell:~$ curl http://jupiter.challenges.picoctf.org:60915/robots.txt
User-agent: *
Disallow: /8028f.html
carlosof-picoctf@webshell:~$ curl http://jupiter.challenges.picoctf.org:60915/8028f.html
<!doctype html>
<html>
  <head>
    <title>Where are the robots</title>
    <link href="https://fonts.googleapis.com/css?family=Monoton|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <div class="container">
      
      <div class="content">
        <p>Guess you found the robots<br />
          <flag>picoCTF{ca1cu1at1ng_Mach1n3s_8028f}</flag></p>
      </div>
      <footer></footer>
  </body>
</html>
carlosof-picoctf@webshell:~$
```


## Notas Adicionales
La ruta `robots.txt` es un archivo que se coloca en la raíz de un sitio web y se utiliza para indicar a los motores de búsqueda qué partes del sitio pueden o no pueden rastrear. Es una herramienta importante para el control de acceso y la gestión del SEO.

### ¿Cómo funciona?

1. **Ubicación**: El archivo debe estar en la raíz del dominio. Por ejemplo, `www.ejemplo.com/robots.txt`.
    
2. **Directrices**: Contiene directrices específicas para los robots de búsqueda, como:
    - `User-agent`: Especifica a qué motor de búsqueda se aplican las reglas.
    - `Disallow`: Indica las URL que no deben ser rastreadas.
    - `Allow`: Permite el rastreo de ciertas URL que podrían estar bajo una regla `Disallow`.

## Referencias 
https://jupiter.challenges.picoctf.org/problem/60915//8028f.html
https://developers.google.com/search/docs/crawling-indexing/robots/intro?hl=es