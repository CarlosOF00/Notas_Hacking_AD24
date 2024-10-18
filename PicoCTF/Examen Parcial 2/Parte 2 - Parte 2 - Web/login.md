## Descripción 
My dog-sitter's brother made this website but I can't get in; can you help?[login.mars.picoctf.net](https://login.mars.picoctf.net/)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Ingresamos al link de la pagina web.
- Inspeccionamos la pagina e ingresamos al apartado de `Debugger` ahí encontraremos un archivo de java script.
- Tras analizarlo, podemos darnos cuenta de que tanto el usuario como la contraseña se encuentran ahí, pero encriptadas.
```bash
(
  async() => {
    await new Promise((e => window.addEventListener('load', e))),
    document.querySelector('form').addEventListener(
      'submit',
      (
        e => {
          e.preventDefault();
          const r = {
            u: 'input[name=username]',
            p: 'input[name=password]'
          },
          t = {};
          for (const e in r) t[e] = btoa(document.querySelector(r[e]).value).replace(/=/g, '');
          return 'YWRtaW4' !== t.u ? alert('Incorrect Username') : 'cGljb0NURns1M3J2M3JfNTNydjNyXzUzcnYzcl81M3J2M3JfNTNydjNyfQ' !== t.p ? alert('Incorrect Password') : void alert(`Correct Password! Your flag is ${ atob(t.p) }.`)
        }
      )
    )
  }
) ();
```
- En linux, podemos desencriptar el mensaje y obtenemos usuario y contraseña. La contraseña parece ser la bandera del reto.
```bash
┌──(kali㉿kali)-[~/Parcial2]
└─$ echo 'YWRtaW4' | base64 -d                                                   
admin base64: invalid input

┌──(kali㉿kali)-[~/Parcial2]
└─$ echo 'cGljb0NURns1M3J2M3JfNTNydjNyXzUzcnYzcl81M3J2M3JfNTNydjNyfQ' | base64 -d
picoCTF{53rv3r_53rv3r_53rv3r_53rv3r_53rv3r}base64: invalid input
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ 

```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/200
