# Marcode (573 Points)
Marcode (Mr. Code in Hebrew), Ineed your help!
I got a movie but I cant see it. It hypnotizes me.
please help me!
yours,
Gveretcode (Mrs. Code in Hebrew)

P.S.
change NOXCTF to noxCTF.
It contained the video (Marcode.mp4) which had barcodes on each frame <br> Using ffmpeg to extract all the frames 
```
ffmpeg -i Marcode.mp4 -r 25 -f image2 pictures/images-%04d.png
```
using recursively python.py decoded all the bar codes 
```
for i in `seq -w 1 3490 `; do python2.7 python.py pictures/images-$i.png; done
```
this gave all the google drive links which are further stored in uniquelinks.txt 
<br>
Using the textgen.py, generated the text (text_1.txt) which was a chapter from Harry Potter and deathly hallows part 1

```
import requests
from bs4 import BeautifulSoup

links = open('unique_links.txt').read().split()

for link in links:
    r = requests.get(link)
    soup = BeautifulSoup(r.text, 'html.parser')
    print (soup.title)
```
<br>
Some of the words were mispelled, taking out the extra characters <br>
gave the <b>Flag:noxCTF{AVADAKEDAVRA}</b>
