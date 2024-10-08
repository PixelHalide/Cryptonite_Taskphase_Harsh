# Oasis CTF Challenge

## Ready Player One?

On playing the message, it plays a series of bips and bops. It is obviously Morse code. I go to an online morse code decoder, where you can upload a sound file of morse code and it decodes it for you, revealing the flag.

## Arte-Miss?

We downloaded the file, and the first thing you do with any image is you open it as a text file to search for hidden text. I've done this before several times for other hunts/challenges. Opening it as a text file reveals the flag.

## String me to sleep

There is a large amount of text provided to us, and the problem says "find the flag hidden in the book". A simple CTRL+F Search of **"OASIS{"** yields us the flag.

## This or that?

The text provided to us is obviously encoded in Hex. I decode it from Hex into ASCII, But it yields a string with some unreadable characters. I try to do several things with this string. I try to treat it as a Vigenere Cypher, with ARTEMIS_WHISPER as the key, but that doesn't work.

I trace back my steps and read the question again. I realise the question puts emphasis on the word **exclusive**. I quickly realise that this implies the XOR operation, the **Exclusive** or operation. I repeat the key "ARTEMIS_WHISPER" until it maches the size of the decoded Hex and perform an XOR operation on it to get the key.

## Jekylle and Hide!

We are greeted to a website with a text entry field. My first thought was to try SQL Injection to try to break something, but I'm not very proficient with it and decided to try something simple. I inspect element the page, and look through the HTML. On Firefox, there is a search function to search the source of a page. I put in **OASIS{** and it yields the first part of the flag. Looking through more of the JS behind the website, I was able to find the 2nd part of the flag.

## Keynough is enough

I've solved a lot of Vigenere cyphers before. If a key is given and a cypher is given, It's most likely a Vigenere cypher. There is also a clue "vinegar" given in the text to indicate this. Decoding the cypher with "WHISPER" as the key yields the answer.

## BasiKEllY

My first thought was this was an Engima cypher, Considering the word "enigma" was used in the challenge text. However, we don't have all the information like the rotor and ring numbers, So it can't be one. I use a Cypher Identifier and it tells me it's likely Base32. Decoding it with Base32 indeed yields us the flag.

## Key-Key do you love me?

## Knock Knock

Open up the image in Krita, Clean up the image with the magic wand tool to be able to scan the qr code.

## Microsoft StrongEdge

We download the PDF and look through it. We try to look for offslide elements but can't find any. We discover a feature in Powerpoint in the accessibility settings that tells us that there is an offslide element somewhere, which is an image. We convert the PPT into a zip file and unzip it, to get all media seperated from the pdf. We find the hidden image, which is decoded with a Caeser cipher with a shift of 13, As implied by the 13 written behind the flag.

## Maze Runner

Google reverse imaging the image yields us the name of the structure and its location. I try putting the name of the creator and location in as the flag, but it doesn't work. I keep trying for a while, until I just try to look for more information on the place. I look the Wikipedia page of the labrynth, and find out the Ideator is a different person from the creator of the place. Putting his name in gives us the flag.

## Not Noice

The audio sounds very weird. My first thought was that it's not morse. But I still decided to put it in a morse decoder anyway, Since I'm not aware of any other way to decode something from sound. Putting it in a morse code decoder reveals that The frequency of the beeps spell out the flag.

## Nom-Nom

I inspect element the page to find any information. The first thing that appears is a warning by firefox saying this: 
```Cookie “admin” does not have a proper “SameSite” attribute value. Soon, cookies without the “SameSite” attribute or with an invalid value will be treated as “Lax”. This means that the cookie will no longer be sent in third-party contexts. If your application depends on this cookie being available in such contexts, please add the “SameSite=None“ attribute to it. To know more about the “SameSite“ attribute, read https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite```

This immediately reveals that there is a cookie affecting our admin status. I go to the cookies tab and indeed, there is. I change the admin status from false to true, and this yields the flag.

## Quence your thirst

My first thought was to try a Caeser cypher, as with any garbled text. This didn't work. I then took a look at the link and realised it was a substitution cypher, and was able to decode it starting with HTTPS.
We get a katb link, However this link is broken. I try several things, Such as doing a Vigenere decode on it with the key as "egg" (the "eggcelent" pun made me think of this), But this didn't work. Then I realised that only 20 or so alphabet had some sort of mapping to another alphabhet, and some of the alphabets without any mapping were in the Link. This means that these alphabets could be replace with any other alphabet, and

## Git Gud

Unzipping the folder reveals a pdf. I look through the pdf. It's a research paper with nothing of note. I then go back and try to look at the file again. I then unhide my hidden files in my file explorer, and find a .git folder.

## Stairway to Heaven

chmod +x


## I have been falling for 30 minutes!

I just played around with the link for a minute and set the number in the link as -1. Yields me the flag. Pure luck.

## Heads up, tails down

A corrupted PNG. I look through the text file of the png for the flag, but there is none. Only hint is that the 1st line says fix_metocrackme, Which means we have no option other than fixing the png. I try some online png "fixers", to uncorrupt an image, but it doesn't work. I look through the txt file, And find repetetive text. I remove it, but it still doesn't work. I try to convert the file into a png, gif, avif, But that also doesn't work.

I then look through the PNG specification, and find that the header of the file is broken. There has to be a specific hex text at the start for it to be identified as a PNG. I open the file in hexedit, and adjust the header of the file with the text that is supposed to be there. It fixes the png and the photo reveals the flag.

## All that for a drop of blood

I inspect element the page and try to find something. Nothing was found. I try to look through the cookies, But nothing was found. Somehow the website is authenticating us without storing anything on our machine. This means that everything is done on their server. Doing research online suggest packet manipulation. I come across Burp Suite, An application just for doing this. I intercept the packets going from my browser to the website.

## A Rocky Start

I download Unity and play the game. There's no way to shoot or do anything useful. As a kid, I've used Cheat Engine a lot in video games. I'd make my health/ammo/money go infinite. So I try to do the same thing. I go in and try to change my score to a 100. But then I realise I have to change my score value atleast once to actually do this. There are many memory addresses with the value of 0. And if I want to figure out which one of them correspond to the value of score, I'll have to change the value of score atleast once, Which is not possible. So then I trace back my steps and 