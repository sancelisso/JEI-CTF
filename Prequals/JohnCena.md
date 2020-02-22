# JEI-CTF – John Cena

* **Points:** 150

## Challenge

> Hint! [https://tenor.com/search/john-cena-cant-see-me-gifs](https://tenor.com/search/john-cena-cant-see-me-gifs)
## Solution
Pour ce challenge, il faut avouer que le lien du hint ne nous a pas été utile. You can't see me pour dire que le flag est un peu caché. Pour cela, nous nous sommes connecté à nouveau sur le serveur ftp et à l'aide de la commande ```ls -la```  nous avons pu trouver un fichier
 [.flag2.txt](Files/.flag2.txt)
 ```console
 Sancelisso@kali:~/Bureau/JEI-CTF$ ftp 91.234.194.228
 Connected to 91.234.194.228.
 220 (vsFTPd 3.0.3)
 Name (91.234.194.228:Sancelisso): ifri_hacker
 331 Please specify the password.
 Password:
 230 Login successful.
 Remote system type is UNIX.
 Using binary mode to transfer files.
 ftp> ls -la
 200 PORT command successful. Consider using PASV.
 150 Here comes the directory listing.
 dr-xr-xr-x    2 65534    65534        4096 Feb 16 09:01 .
 dr-xr-xr-x    2 65534    65534        4096 Feb 16 09:01 ..
 -rw-r--r--    1 0        0              24 Feb 16 08:39 .flag2.txt
 -rw-r--r--    1 0        0              29 Feb 16 08:38 Flag.txt
 -rw-r--r--    1 0        0          520528 Feb 16 09:01 angel.png
 226 Directory send OK.
 ftp> get .flag2.txt
 local: .flag2.txt remote: .flag2.txt
 200 PORT command successful. Consider using PASV.
 150 Opening BINARY mode data connection for .flag2.txt (24 bytes).
 226 Transfer complete.
 24 bytes received in 0.00 secs (96.8492 kB/s)
 ftp> quit
 221 Goodbye.
 ```
 En ouvrant le fichier on obtient le flag ci-après:

```
JeiCtf_{ s3cUr3_Sh3lL }

```
