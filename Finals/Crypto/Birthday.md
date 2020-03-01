# JEI-CTF – Birthday

* **Category:** Crypto
* **Points:** 100

## Challenge
>   Joyeux anniversaire à mon frère César.  <br>
>  D txlfn eurzq ira mxpsv ryhu wkh odcb grj

## Solution
Il s'agit d'un texte chiffé avec l'algorithe de césar. A travers ce site [https://www.dcode.fr/chiffre-cesar](https://www.dcode.fr/chiffre-cesar) nous avons essayer un bruteforce puis nous remarquons que la valeur du décalage était 3.

Texte obtenu: __A quick brown fox jumps over the lazy dog__

```
JeiCtf_{ Aquickbrownfoxjumpsoverthelazydo  }
```
