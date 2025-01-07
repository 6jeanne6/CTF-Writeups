# IrisCTF2025 - Where's Bobby 2

OSINT - Medium - 50 points

## Challenge description

*I took this picture while I was on a trip, somewhere, and I saw this beautiful wall art. However, in a shocking turn of events, I don't know where it was! Can you find it for me?*

*The flag is the coordinates of the building which contains this wall art, in decimal format and correct to 3 decimal places, and seperated by an underscore (_).*

*For example, if the building was located at 50°59'52.934"N, 118°13'28.792"W the flag would be irisctf{50.998_-118.225}.*

## Solution

By using Google Lens, we have indications of the place in a Chinese blog article : the Baiziwan metro station.

On the Chinese Wikipedia page, we have GPS coordinates : `39°53′29″N 116°29′30″E`

It is in Degrees Minutes Seconds but the flag asked for a Decimal Degrees format. I used `https://www.latlong.net/degrees-minutes-seconds-to-decimal-degrees` to convert.

The flag is: `irisctf{39.891_116.492}`
