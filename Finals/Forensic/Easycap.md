# JEI-CTF – Easycap ?

* **Catégorie :** Forensic
* **Points :** 100

## Challenge

>  Can you get the flag from the packet capture?  <br>
> [easycap.pcap](Ressources/easycap.pcap)

## Solution
Pour obtenir le flag, il suffit de suivre le flux tcp de l'un des paquets tcp.

En faisant cela, nous obtenons:
```
FLAG:385b87afc8671dee07550290d16a8071
```
En respectant le format des flags, nous avons le string ci-après
```
Jei_CTF{ 385b87afc8671dee07550290d16a8071 }
```
