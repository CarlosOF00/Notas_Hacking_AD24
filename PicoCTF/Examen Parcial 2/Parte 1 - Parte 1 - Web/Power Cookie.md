## Descripción 
Can you get the flag?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Iniciamos el launcher del reto e ingresamos a la pagina web.
- Inspeccionamos la pagina y nos vamos al apartado de `Application`, ahí buscamos en el apartado `Storage` las `Cookies`, según el navegador, algunos nos permitirán editar las cookies y en otros necesitaremos una extensión, una recomendación es `CookiesEditor`.
- Cambiaremos el valor de `isAdmin` que esta en 0 a 1.
- Recargamos la pagina y obtenemos la bandera.
- Flag:
	- picoCTF{gr4d3_A_c00k13_0d351e23}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/288
