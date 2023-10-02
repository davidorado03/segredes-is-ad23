# Insp3ct0r

## Objetivo
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/41511/` ([link](https://jupiter.challenges.picoctf.org/problem/41511/)) or http://jupiter.challenges.picoctf.org:41511
## Solución
```bash
davidorado-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/problem/41511/
--2023-10-02 15:41:35--  https://jupiter.challenges.picoctf.org/problem/41511/
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/html]
Saving to: 'index.html'

index.html                       [ <=>                                          ]     966  --.-KB/s    in 0s      

2023-10-02 15:41:35 (215 MB/s) - 'index.html' saved [966]

davidorado-picoctf@webshell:~$ cat index.html 
<!doctype html>
<html>
  <head>
    <title>My First Website :)</title>
    <link href="https://fonts.googleapis.com/css?family=Open+Sans|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="mycss.css">
    <script type="application/javascript" src="myjs.js"></script>
  </head>

  <body>
    <div class="container">
      <header>
        <h1>Inspect Me</h1>
      </header>

      <button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">What</button>
      <button class="tablink" onclick="openTab('tababout', this, '#222')">How</button>
      
      <div id="tabintro" class="tabcontent">
        <h3>What</h3>
        <p>I made a website</p>
      </div>

      <div id="tababout" class="tabcontent">
        <h3>How</h3>
        <p>I used these to make this site: <br/>
          HTML <br/>
          CSS <br/>
          JS (JavaScript)
        </p>
        <!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
      </div>
      
    </div>
    
  </body>
</html>

picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?832b0699}
```
## Notas adicionales

## Referencias
