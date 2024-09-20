## Descripción 
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/6353/` ([link](https://jupiter.challenges.picoctf.org/problem/6353/)) or http://jupiter.challenges.picoctf.org:6353

## Datos de Acceso al Nivel
user: 
password:

## Solución
- Inspeccionamos el codigo fuente de la pagina.
- Ordenamos el codigo para una mayor legibilidad.
- Ordenamos la cadena y formamos la bandera.

```bash
var cad = ["0a029}", "_again_5", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
undefined
cad[8] + cad[9] + cad[1] + cad[0]
'picoCTF{not_this_again_50a029}'
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/69