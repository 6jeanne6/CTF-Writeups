# IrisCTF2025 - Sleuths and Sweets

OSINT - Easy - 50 points

## Challenge description

*I visited my friend in Japan, and we had some alright crepes! The area had a lot of foot traffic, so we expected a long wait, but it was worth it. I’m usually not a fan of yogurt in my crepe, but it still tasted pretty alright.*

*Question: What is the address of this location?*

## Solution

Based on the written characters of kanjis and katakana, we can guess the location is in Japan.

Using Google Lens, we can find an Instagram account with an interesting post about crepes, which has the same appearance as the one on our photo: the brand's name is Marion Crepes.

I searched all Marion Crepes shops in Japan with Google Maps, and looked for the location which has the red rectangle sign with kanjis meaning Bank outside thanks to Street View: it leads to Marion Crepes Shibuya Modi. Its address is: 1 Chome-21-3 Jinnan, Shibuya, Tokyo 150-0041, Japon.

The flag is: `irisctf{1_Chome_21_3_Jinnan}`
