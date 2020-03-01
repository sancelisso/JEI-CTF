# JEI-CTF – Belle au bois dormant

* **Category:** Stegano
* **Points:** 250

## Challenge
> Et si son type de sommeil cachait quelque chose ? <br>
> [La_belle_au_bois_dormant.docx](Ressources/ La_belle_au_bois_dormant.docx)

## Solution
En utilisant la commande _strings_ sur le fichier en quoi, on remarque qu'il est embarqué avec un autre fichier _flag.txt_. Ainsi nous utilisons l'outil *binwalk* pour pouvoir extraire le fichier flag.txt. Après extraction, nous pouvons découvrir le flag dans le fichier concerné.
```
JeiCtf_{ d0cx_m4n1pul4t0r }
```
