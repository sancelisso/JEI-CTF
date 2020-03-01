# JEI-CTF – Bat

* **Category:** Crypto
* **Points:** 250

## Challenge
> [crypto0](Ressources/crypto0.zip)

## Solution
Quand on décompresse le fichier donné on a:

enc.bat
```
@echo off
setlocal ENABLEEXTENSIONS ENABLEDELAYEDEXPANSION
title Encrypt
color a
:mainmenu
set savefile=on
::set Encrypt=Nothing
(set CHAR[a]=UDFM45) & (set CHAR[b]=H21DGF) & (set CHAR[c]=FDH56D) & (set CHAR[d]=FGS546) & (set CHAR[e]=JUK4JH)
(set CHAR[f]=ERG54S) & (set CHAR[g]=T5H4FD) & (set CHAR[h]=RG641G) & (set CHAR[i]=RG4F4D) & (set CHAR[j]=RT56F6)
(set CHAR[k]=VCBC3B) & (set CHAR[l]=F8G9GF) & (set CHAR[m]=FD4CJS) & (set CHAR[n]=G423FG) & (set CHAR[o]=F45GC2)
(set CHAR[p]=TH5DF5) & (set CHAR[q]=CV4F6R) & (set CHAR[r]=XF64TS) & (set CHAR[s]=X78DGT) & (set CHAR[t]=TH74SJ)
(set CHAR[u]=BCX6DF) & (set CHAR[v]=FG65SD) & (set CHAR[w]=4KL45D) & (set CHAR[x]=GFH3F2) & (set CHAR[y]=GH56GF)
(set CHAR[z]=45T1FG) & (set CHAR[1]=D4G23D) & (set CHAR[2]=GB56FG) & (set CHAR[3]=SF45GF) & (set CHAR[4]=P4FF12)
(set CHAR[5]=F6DFG1) & (set CHAR[6]=56FG4G) & (set CHAR[7]=USGFDG) & (set CHAR[8]=FKHFDG) & (set CHAR[9]=IFGJH6)
(set CHAR[0]=87H8G7) & (set CHAR[@]=G25GHF) & (set CHAR[#]=45FGFH) & (set CHAR[$]=75FG45) & (set CHAR[*]=54GDH5)
(set CHAR[C]=45F465) & (set CHAR[_]=HG56FG) & (set CHAR[,]=DF56H4) & (set CHAR[-]=F5JHFH) & (set CHAR[ ]=SGF4HF)
(set CHAR[\]=45GH45) & (set CHAR[/]=56H45G) & (set CHAR[{]=46HM6G) & (set CHAR[}]=M68ATG) & (set CHAR[J]=SGP45F)
echo Enter a string to encrypt:
set /p Encrypt=
cls
set Encrypt2=%Encrypt%
set "EncryptOut="
:encrypt2
set char=%Encrypt2:~0,1%
set Encrypt2=%Encrypt2:~1%
set EncryptOut=%EncryptOut%!CHAR[%char%]!
if not "%Encrypt2%"=="" goto encrypt2
echo Input string: %Encrypt%
echo.
echo Output string: %EncryptOut%
set string=%EncryptOut%
set temp_str=%string%
set str_len=0
:lengthloop
if defined temp_str (
set temp_str=%temp_str:~1%
set /A str_len += 1
goto lengthloop )
echo.
echo Output string is %str_len% characters long!
if not "%savefile%"=="on" echo.%EncryptOut%>>%~d0%~p0encrypted.txt
echo.
pause
cls
goto mainmenu
```
encrypted.txt

```
D3L373ERG54SD3L373FD3L3738G9GD3L373FUDFM45TD3L3735H4FDSGF4HFRD3L373G4F4DX78DGTSGD3L373FD3L3734HFSGP45FJUKD3L3734JHRG4F4D45FD3L373465TH74SJERG54SHG56FG46HM6GSGF4HFUSGFDGSF45GFP4FF1245F465D3L373RG6D3L37341GHGD3L37356FGFD3L373D4CJSSF45GD3L373FHGD3L37356FGFD3L373KHFDGP4D3L373FF1D3L3732USGFD3L373DG45F465RGD3L373D3L37D3L3733641GSD3L373GF4HD3L37D3L3733FM6D3L3738ATD3L373D3L373G
```

Avec un peut de recherche on tombe sur un fichier que je vais nommer dec.bat

```
@echo off
setlocal  ENABLEEXTENSIONS ENABLEDELAYEDEXPANSION
title Decrypt
color a
:mainmenu
set savefile=on
::set Decrypt=Nothing
(set CHAR[UDFM45]=a) & (set CHAR[H21DGF]=b) & (set CHAR[FDH56D]=c) & (set CHAR[FGS546]=d) & (set CHAR[JUK4JH]=e)
(set CHAR[ERG54S]=f) & (set CHAR[T5H4FD]=g) & (set CHAR[RG641G]=h) & (set CHAR[RG4F4D]=i) & (set CHAR[RT56F6]=j)
(set CHAR[VCBC3B]=k) & (set CHAR[F8G9GF]=l) & (set CHAR[FD4CJS]=m) & (set CHAR[G423FG]=n) & (set CHAR[F45GC2]=o)
(set CHAR[TH5DF5]=p) & (set CHAR[CV4F6R]=q) & (set CHAR[XF64TS]=r) & (set CHAR[X78DGT]=s) & (set CHAR[TH74SJ]=t)
(set CHAR[BCX6DF]=u) & (set CHAR[FG65SD]=v) & (set CHAR[4KL45D]=w) & (set CHAR[GFH3F2]=x) & (set CHAR[GH56GF]=y)
(set CHAR[45T1FG]=z) & (set CHAR[D4G23D]=1) & (set CHAR[GB56FG]=2) & (set CHAR[SF45GF]=3) & (set CHAR[P4FF12]=4)
(set CHAR[F6DFG1]=5) & (set CHAR[56FG4G]=6) & (set CHAR[USGFDG]=7) & (set CHAR[FKHFDG]=8) & (set CHAR[IFGJH6]=9)
(set CHAR[87H8G7]=0) & (set CHAR[G25GHF]=@) & (set CHAR[45FGFH]=#) & (set CHAR[75FG45]=$) & (set CHAR[54GDH5]=*)
(set CHAR[45F465]=() & (set CHAR[HG56FG]=.) & (set CHAR[DF56H4]=,) & (set CHAR[F5JHFH]=-) & (set CHAR[SGF4HF]= )
(set CHAR[45GH45]=\) & (set CHAR[56H45G]=/)
echo Enter a string to decrypt:
set /p Decrypt=
cls
set Decrypt2=%Decrypt%
set "DecryptOut="
:decrypt2
set char=%Decrypt2:~0,6%
set Decrypt2=%Decrypt2:~6%
set DecryptOut=%DecryptOut%!CHAR[%char%]!
if not "%Decrypt2%"=="" goto decrypt2
echo Input string: %Decrypt%
echo.
echo Output string: %DecryptOut%
set string=%DecryptOut%
set temp_str=%string%
set str_len=0
:lengthloop
if defined temp_str (
set temp_str=%temp_str:~1%
set /A str_len += 1
goto lengthloop )
echo.
echo Output string is %str_len% characters long!
if "%savefile%"=="on" echo.%DecryptOut%>>%~d0%~p0decrypted.txt
echo.
pause
cls
goto mainmenu
```
En executant dec.bat en donnant encrypted.txt on ne trouve rien de bon mais après une bonne analyse on constate que la séquence des six premières lettres n'est pas utilisé par les programmes et donc on les supprime
un petit code python qui le fait
```
data="D3L373ERG54SD3L373FD3L3738G9GD3L373FUDFM45TD3L3735H4FDSGF4HFRD3L373G4F4DX78DGTSGD3L373FD3L3734HFSGP45FJUKD3L3734JHRG4F4D45FD3L373465TH74SJERG54SHG56FG46HM6GSGF4HFUSGFDGSF45GFP4FF1245F465D3L373RG6D3L37341GHGD3L37356FGFD3L373D4CJSSF45GD3L373FHGD3L37356FGFD3L373KHFDGP4D3L373FF1D3L3732USGFD3L373DG45F465RGD3L373D3L37D3L3733641GSD3L373GF4HD3L37D3L3733FM6D3L3738ATD3L373D3L373G"
while 'D3L373' in data:
	data=data.replace('D3L373','')
print(data)

```
quand on execute dec.bat et on lui donne la sortie du code précedant en argument on a:
```
flag is ei(tf. 743(h.m3.847(h
```
Avec un peu de bricolage on trouve:
```
flag is JeiCtf_{ 743Ch_m3_847Ch }
```
