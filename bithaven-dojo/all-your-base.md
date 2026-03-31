# All your base are belong to us  
Category: Misc  
Points: 100  
Author: dfoo

<img width="446" height="565" alt="Screenshot 2026-03-30 154238" src="https://github.com/user-attachments/assets/a0e59da3-88a3-469c-a091-66a61249b147" />  

Title:  
All your base are belong to us  
Text:  
Base32? Sure.  
Base64? Yeah I know that one.  
Base2^16? ?????????

*Flag format is wwf{}

Content:  
MkpIbmdFcWs4MzVjR3BHRXFVVnZtZWJUQWtSTlNNamE1dGZYQTdwR25ac203SnJQV2FyTUdHQnA3Uk1XZDNZVFlTNTJjemVya1BCN0dBY2NBNkN4U1VBS29TalVBOU1tR1EyYUF0UVlHZTFYOXp1TThWS2o1OHdKRFJaVXhzTGRaZUpaTGV6NUFWc2JHdm5CbTdjV28yNTRyWGpzQURYdEhkSmJmWmtGREVEQWZWeEhFeDNYanNNODZMZVo2cnM2NExGbU5QeG1mUXBqQ3BoY3pCczlRa3kySnFZb1JzSnFtUnk0cW02WFgyOU50N1g2Vg==

---

### My Solution path:  
[dcode website](https://www.dcode.fr/cipher-identifier) cipher identifier and decoding tools:  
Challenge code > Base64 > Base58 > Base32 > (Base92 errors/dead end)  
Then, [Cyberchef](https://cyberchef.org/):  
dcode Base58 decoded results > From Base32 > Magic Wand (From Base85) >  
Then, [Base65536 decoding website](https://www.better-converter.com/Encoders-Decoders/Base65536-Decode) > flag

---
### My process

This challenge provides us with a long string of alphanumeric characters. One might be familiar enough with ciphers and encoding to recognize this string as base64 encoded.

I was not familiar with any of this at the time.

I had, however, recently been made aware of [dcode.fr](https://www.dcode.fr/en), so I copy/pasted the string into the [cipher identifier](https://www.dcode.fr/cipher-identifier). 

It was identified as Base64 with a relatively high level of reliability.
<img width="1079" height="556" alt="Screenshot 2026-03-31 144304" src="https://github.com/user-attachments/assets/ef1c2c77-63c5-4481-9e13-f0e890951374" />

So I clcked on the [base64 coding](https://www.dcode.fr/base-64-encoding) link and pasted the string into the decoder there.

<img width="1071" height="736" alt="Screenshot 2026-03-31 144507" src="https://github.com/user-attachments/assets/b3874961-7fe0-4a07-b09f-f139d9ab61f7" />

Then copy/paste the result and go back to the cipher identifier to do it all again.

It was identified as Base58. Copy/paste result and decode.
That result was identified as Base32. Repeat.

Here's where things started to get a little muddy. The Base32 decoded string was identified, with relatively high reliability, as Base92. Base92 decoding, however, resulted in an error.  

<img width="1068" height="626" alt="Screenshot 2026-03-31 144926" src="https://github.com/user-attachments/assets/217d5b9c-358b-434f-b7e6-7bd2eca857b0" />  

This is where I started kind of flailing around a little, trying different settings on the Base92 decoding page, and generally getting thrown off by the high reliability reported on the Base92 identification. Note the second place identified encoding here, though.

<img width="1050" height="243" alt="Screenshot 2026-03-31 153219" src="https://github.com/user-attachments/assets/dc384b11-c3e7-4b00-9442-407bea96cc8e" />  

I went back and read the challenge text again, and calculated 2^16 as 65536. So I looked up a Base65536 decoder, since dcode didn't appear to have it, and cyber chef didn't have it, and found one [here](https://www.better-converter.com/Encoders-Decoders/Base65536-Decode).

I have since discovered that dcode does indeed have a Base65536 decoding tool, but I had not found it yet via the cipher identifier, because, unbeknownst to me, I didn't have a Base65536 encoded string to be identified yet.

Regardless, I put the string I had gotten from the Base32 decoding into the Base65536 decoder, and got an error about invalid characters.

This then had me going on to Cyberchef and playing around with the output encoding feature on the results pane, which can come in handy sometimes now that I've learned to try it out. But I kept running into dead ends.

I followed the decoding path from the beginning a few more times, always getting thrown off after the Base32 decoding. I messed around in Cyberchef with the output encoding and kept pasting results into the Base65536 decoder and getting errors.

As with many solutions, I finally got lucky after trying a lot of different things and feeling bad about how none of them worked.

What finally worked: Pasting the Base32 string (the Base58 decoded result that was identified as Base32) into Cyberchef, choosing "from Base32" and then clicking the magic wand icon that appeared. 

<img width="1653" height="615" alt="Screenshot 2026-03-31 150754" src="https://github.com/user-attachments/assets/1acbeb11-541e-48cf-89de-1f69468db682" />  

It looks like Cyberchef recognized an additional layer of what it calls Base85. Alternatively, as you may have noticed in the reliability screenshot posted earlier, ASCII85 was identified as the second most likely encoding for the Base32 decoded string, and if I had clicked through and tried ASCII85 in dcode, I would have gotten the same result I got from Cyberchef.

The Cyberchef magic wand result gave me a string of characters that had no errors or missing character symbols, but which was still not a recognizable flag. If I had done some research into what Base65536 looks like, I might have felt good about the kinds of characters I was seeing, but at the time, I had no idea what Base65536 was. It wasn't until I pasted that string into the Base65536 decoder that I realized I'd finally hit the jackpot.

<img width="784" height="808" alt="Screenshot 2026-03-31 151034" src="https://github.com/user-attachments/assets/89b69ff9-be69-48d5-867b-8e4de55bc40b" />
