## Descripción 
Can you get the flag?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Iniciamos el launcher e ingresamos al link de la pagina web.
- Inspeccionamos la pagina y no encontraremos nada, así que nos loggearemos como admin y una contraseña cualquiera.
- Nos aparecerá un mensaje de que la contraseña es incorrecta, pero ahora al momento de `inspeccionar` podremos ver que en el aparato de `Source` aparecerán nuevos archivos, en especial uno llamado `secure.js` su contenido es el siguiente: 
```bash
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}

```
- Ahora ya sabemos el usuario y contraseña, así que ingresamos esos datos y obtenemos la bandera.
- Bandera: picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/278
