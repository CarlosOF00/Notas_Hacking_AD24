## Descripción 
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 13758`.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosCrypto]
└─$ nc jupiter.challenges.picoctf.org 13758
-------------------------------------------------------------------------------
jvkzxtgo rbxb yo dvwx actz - axbmwbkjd_yo_j_vfbx_ctnlut_ukfgaxgtdw
-------------------------------------------------------------------------------
hb hbxb kvg nwjr nvxb grtk t mwtxgbx va tk rvwx vwg va vwx oryq gycc hb oth rbx oyki, tku grbk y wkubxogvvu avx grb ayxog gynb hrtg hto nbtkg ld t oryq avwkubxykz yk grb obt.  y nwog tjikvhcbuzb y rtu rtxucd bdbo gv cvvi wq hrbk grb obtnbk gvcu nb orb hto oykiykz; avx axvn grb nvnbkg grtg grbd xtgrbx qwg nb ykgv grb lvtg grtk grtg y nyzrg lb otyu gv zv yk, nd rbtxg hto, to yg hbxb, ubtu hygryk nb, qtxgcd hygr axyzrg, qtxgcd hygr rvxxvx va nyku, tku grb grvwzrgo va hrtg hto dbg lbavxb nb.
                                                                                 
┌──(kali㉿kali)-[~/retosCrypto]
└─$ 
```
- Ingresamos a la siguiente pagina web [Substitution Solver ](https://www.guballa.de/substitution-solver) y pegamos el texto que obtuvimos.
- Nos devuelve lo siguiente:
```bash
congrats here is your flag - frequency_is_c_over_lambda_dnvtfrtayu
-------------------------------------------------------------------------------
we were not much more than a quarter of an hour out of our ship till we saw her sink, and then i understood for the first time what was meant by a ship foundering in the sea.  i must acknowledge i had hardly eyes to look up when the seamen told me she was sinking; for from the moment that they rather put me into the boat than that i might be said to go in, my heart was, as it were, dead within me, partly with fright, partly with horror of mind, and the thoughts of what was yet before me.

```
- Bandera:
	- frequency_is_c_over_lambda_dnvtfrtayu

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/38?category=2&difficulty=2&page=1&search=waves
https://www.guballa.de/substitution-solver
