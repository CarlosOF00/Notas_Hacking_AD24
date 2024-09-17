## Descripción 
How well can you perfom basic binary operations?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ nc titan.picoctf.net 57628

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01101001
Binary Number 2: 00111111


Question 1/6:
Operation 1: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0001 1001 1101 0111

Incorrect input. Provide the right input
Enter the binary result: 0001100111010111               
Correct!

Question 2/6:
Operation 2: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 01101000
Incorrect. Try again
Enter the binary result: 01101010    
Incorrect. Try again
Enter the binary result: 011010010
Correct!

Question 3/6:
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00101001
Correct!

Question 4/6:
Operation 4: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01111111
Correct!

Question 5/6:
Operation 5: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 111111
Incorrect. Try again
Enter the binary result: 00111111   
Incorrect. Try again
Enter the binary result: 00011111
Correct!

Question 6/6:
Operation 6: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10101000
Correct!

Enter the results of the last operation in hexadecimal: A8

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_675602ae}

```

## Notas Adicionales
![[Binhexa.png]]

## Referencias 
https://play.picoctf.org/practice/challenge/404

