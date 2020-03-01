# JEI-CTF – 5 digits

* **Category:** Misc
* **Points:** 350

## Challenge

>  Enter the good int to get the flag <br>
 nc 31.207.34.225 40111 <br>
 **Hint!** crunch 0 128 aabcdefghijklmnopqrstuvwxyz0123456789 <br>
 **Hint!** 28900 c'est plus 29500 c'est moins

## Solution
Pour trouver ce flag, il suffit de faire du bruteforce avec les valeurs possibles
```console
Sancelisso@kali:~/JEI-CTF$ for i in {28900..29500}; do echo $i | nc 31.207.34.225 40111 | grep -i jei; done
 JeiCtf_{ 90od_8rU7f0rC3R }
^C
Sancelisso@kali:~/JEI-CTF$
```
The solution.

```
JeiCtf_{ 90od_8rU7f0rC3R }
```
