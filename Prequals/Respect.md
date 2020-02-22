# JEI-CTF – Respect

* **Points:** 500

## Challenge

> Useless bar
## Solution
A ce niveau, nous avons ouvert l'image [angel.png](Files/angel.png). Il faut remarquer c'est une image provenant d'un challenge de stéganographie sur [root-me](root-me.org) (ce n'est pas grave si vous ne le saviez pas).

En zoomant l'image (la partie du haut), nous voyons **PASS=TOTORO** : c'était le but du challenge de root-me. Dans notre cas, ce texte trouvé ne correspond pas au format des flags, alors il faut chercher ailleurs :)

En tapant la commande ci-après: ```
strings angel.png ``` on peut lire decodeMe.txt dans le retour de la commande.
On suppose donc qu'un tel fichier est embarqué avec l'image. Du coup, nous utiliserons l'outil **binwalk** pour extraire le fichier en question.
En ouvrant le fichier extrait, nous obtenons ceci:

```
||L|1U|vM|i8|x|L1||cv||||Y|y|9|G|L0|Uve|i9V|L20|vMS|9ZL|00v|My|9|OL24||vVS||9X||L3Qv|Qi9NL|2svN|S9H|L08vWC|9|S|L1|IvUy|9FL|zAve||i|9|UL|1Q||v|Ti9|K|L|1|o|v|M|i|9|a|L|1|I|v|U|C|9|U|L|z|A|v|P|Q|=|=
```
Le titre nous disait Useless bar, du coup il faut supprimer les bars
Nous avons fait plusieurs opérations avec python3 avant de trouver le flag :
```console
Sancelisso@kali:~$ python3
Python 3.7.5 (default, Oct 27 2019, 15:43:29)
[GCC 9.2.1 20191022] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> string="||L|1U|vM|i8|x|L1||cv||||Y|y|9|G|L0|Uve|i9V|L20|vMS|9ZL|00v|My|9|OL24||vVS||9X||L3Qv|Qi9NL|2svN|S9H|L08vWC|9|S|L1|IvUy|9FL|zAve||i|9|UL|1Q||v|Ti9|K|L|1|o|v|M|i|9|a|L|1|I|v|U|C|9|U|L|z|A|v|P|Q|=|="
>>> string=string.replace('|','')
>>> import base64
>>> base64.b64decode(string)
b'/U/2/1/W/c/F/E/z/U/m/1/Y/M/3/N/n/U/W/t/B/M/k/5/G/O/X/R/R/S/E/0/z/T/T/N/J/Z/2/Z/R/P/T/0/='
>>> string="/U/2/1/W/c/F/E/z/U/m/1/Y/M/3/N/n/U/W/t/B/M/k/5/G/O/X/R/R/S/E/0/z/T/T/N/J/Z/2/Z/R/P/T/0/="
>>> string=string.replace('/','')
>>> base64.b64decode(string)
b'SmVpQ3RmX3sgQkA2NF9tQHM3M3IgfQ=='
>>> string="SmVpQ3RmX3sgQkA2NF9tQHM3M3IgfQ=="
>>> base64.b64decode(string)
b'JeiCtf_{ B@64_m@s73r }'
>>>
```

```
JeiCtf_{ B@64_m@s73r }
```
