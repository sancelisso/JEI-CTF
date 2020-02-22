# JEI-CTF  – DNS

* **Points:** 150

## Challenge

> Something you tell can DNS

## Solution
A ce niveau, il faut filtrer les paquets du fichier pcap selon le protocole DNS.
En effet, nous obtenons l'url ci-après:

```
www.4a65694374665f7b2044306d40696e5f6e406d335f53797374656d207d.com
```
Remarquons que le string 4a65694374665f7b2044306d40696e5f6e406d335f53797374656d207d est codé en hexadécimal. Après décodage avec l'outil [cyberchef](https://gchq.github.io/CyberChef/) nous obtenons le fameux flag
```
JeiCtf_{ D0m@in_n@m3_System }
```
