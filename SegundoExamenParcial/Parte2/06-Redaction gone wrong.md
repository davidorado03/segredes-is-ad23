# Redaction gone wrong

## Objetivo
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
## Solución
```bash
┌──(kali㉿kali)-[~/2Exa/2/Redaction]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2023-11-03 19:21:06--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.38, 18.160.124.34, 18.160.124.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.38|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_for_ABC_Labs.pdf                          100%[=======================================================================================================================================>]  34.10K  --.-KB/s    in 0.003s  

2023-11-03 19:21:06 (13.1 MB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/2Exa/2/Redaction]
└─$ open Financial_Report_for_ABC_Labs.pdf 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/2Exa/2/Redaction]
└─$ nano key.txt

Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.
Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document.

```
## Notas adicionales

## Referencias