# Blind Date (573 Points)
My mom got me a date with someone! she sent me an image but i cannot open it. I don't want it to be a blind date. Can you help me?
and a jpeg file (xyz.jpg)
<br>
Checking the hex of xyz.jpg showed that every 4 bytes were reversed
![alt-text](https://i.imgur.com/lkFQCA2.png)
<br>Running strings on this image gave Base64 encoded string:<br>
<b>g4iLuACIuACIgAiLg4iLuACIuACIgAiLg4iLuACIuACIgAiLgAiLN4iLg4iCgACIgAiLg4CIgACIgACIgAiLgACIg4CIgACIgAiLg4CIg4CIK0AIgACIu4CIgACIgACIgACIu4CIgACIgACIgAiLu4CIgACIgACIgAiLKPgL</b>
<br>
which on decoding gave a braille text
``` ..   .  ..  ..   .  ..  ..   .  ..  .  ..
.    .   .       .      .    .   .  .  
    ..          ..      .   ..      .  .   
```
Which translated to F4C3P4LM (will be used to later)
The header should have ffd8ffe0 instead of e0ffd8ff<br>
Using blind.py, the bits were reversed which gave the image <br>
![alt-text](https://github.com/DoMINAToR98/CTFs/blob/master/NOX_CTF/Misc/BlindDate/-Untitled-.jpg)
<br>
using Binwalk, a hidden zip file(96DA.zip) was extracted, which was opened with 7z with the password F4C3P4LM
and it gave us flag.txt
Flag.txt had brainfuck code 
```
++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>>++++++++++.+.+++++++++.<---.+++++++++++++++++.--------------.>+++.<+++++++++++++++++.<++++++++++++++++++.>>------.---------.--------.-----.++++++++++++++++++++++++++.<<.>>----.<++++++++.+++.>---------.<<+.>>++.<++.-----.+++++.<+++.>>++++++.<<-.>-----.<+.>.+++.>--------.<<---.>>++.<++.-----.+++++.<+++.>>++++++.<<-.++++++++++++.>>+++++++++.<<<++++++++++++++++++++++.
```
Decoding the brainfuck code  <br> gave us the <b>Flag:noxCTF{W0uld_y0u_bl1nd_d4t3_4_bl1nd_d4t3?}</b>
