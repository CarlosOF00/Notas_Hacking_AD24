## Descripción 
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/17/challenge.zip)

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ ssh -p 63393 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Higher! Try again.
Enter your guess: 350
Higher! Try again.
Enter your guess: 450
Higher! Try again.
Enter your guess: 470
Lower! Try again.
Enter your guess: 460
Higher! Try again.
Enter your guess: 465
Lower! Try again.
Enter your guess: 462
Congratulations! You guessed the correct number: 462
Here's your flag: picoCTF{g00d_gu355_6dcfb67c}
Connection to atlas.picoctf.net closed.
carlosof-picoctf@webshell:~$ 
```


## Notas Adicionales


## Referencias 
https://play.picoctf.org/practice/challenge/442
