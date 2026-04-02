---
title: Don't Look Down  
tags:  
  - Misc / General Skills
---
# Don't Look Down
Category: Misc  
Points: 100  
Author: dfoo  

<img width="473" height="352" alt="Screenshot 2026-03-30 135424" src="https://github.com/user-attachments/assets/551b8069-785e-49c9-8fb7-f6f9ec747d72" />

Title: Don't Look Down  
Text: No really, don't.  
Content: noyjsbrm}ej-+m44fx+TPY+ej4m+U-i+v5m+kIdy+dj2gy|  

---
### Solution path:

[dcode cipher identifier](https://www.dcode.fr/cipher-identifier) > keyboard shift > flag

---
### My process:  

This was one of my very first CTFs ever attempted. I had no idea where to begin.  
So it was a huge hint when the challenge author pointed me to the website: [dcode](https://www.dcode.fr/en). 
Specifically, the [cipher identifier](https://www.dcode.fr/cipher-identifier)

The cipher identifier is now bookmarked in my browser and one of the first places I visit when I encounter what looks like encoded data. I've since learned to incorporate other tools as well, namely [cyberchef](https://cyberchef.org/) but I prefer to try the dcode cipher identifier before I visit cyberchef.

Pasting the text into the cipher identifier, however, doesn't give us a very strong positive match for any cipher in particular. 
The top results in the left pane all have only a little bit of green in the reliability meter.

In retrospect, I spent more time than necessary on this one. 
Even knowing that is the case with almost _all_ CTF challenges once you know the solution, 
I now know that getting bogged down in trying to make the first idea work is often less productive that a general approach of trying a lot of pathways before commiting to one.

But this was my first CTF.
I ended up chasing dead ends and dealing with my lack of familiarity with the dcode website and the concepts involved. 

Here's what I would do now that I'm older and wiser:

- feed the cipher into the cipher identifier
- click through to the decrypt page of each of top 10 or so results and simply paste the cipher and hit "decrypt"
- skim the results, note anything that catches my eye, and MOVE ON

Because this approach would have solved the challenge more quickly.

What I ended up doing, instead, was playing around with changing the decryption settings in the top results, and spending a lot more time trying to get the "most promising" decrypt options to work.

When the simple "spray and pray" approach outlined above would have given me the flag much sooner.

As it happened, I eventually ended up trying the number 3 option on the cipher identifier results list, and there, 
at the very top of the results of a basic "paste and press the button" was a very obvious flag.

<img width="1095" height="678" alt="Screenshot 2026-03-30 144944" src="https://github.com/user-attachments/assets/6b204bae-aac2-4569-b4f5-d8afa3e89f9b" />  



It was only in retrospect that the reference to "Don't look down" was literally referring to the keyboard in front of me, 
and knowing the flag format is bithaven{flag}, I could have seen that the character for the 'b' in bithaven was 'n' and the character for the '}' at the end was '|', that I could have decrypted this manually, if I had been just a bit more clever.

<img width="1900" height="639" alt="Screenshot 2026-03-30 145218" src="https://github.com/user-attachments/assets/95d3257e-a4ad-4219-a348-2325b2bfd64f" />

