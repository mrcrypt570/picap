# picap
hides a short string (95 characters) in the red channel of an image (LSB), creating a PNG called "new.png".

reads JPG, BMP, PNG and others - but ONLY IF THEY'RE 'RGB' or 'RGBA' color modes. 

once i grok lossy compression better, options to save as JPG will be added.

records the length of the message in the color data of the first pixel,
so if you don't want to leave a clue with some strange color in the first pixel,
encode your message in an image whose first pixel is close to the value this
script will set.

######## WORK IN PROGRESS ########

usage: picap [-h] [-d DECRYPT] [-e ENCRYPT] [-m MESSAGE]

hides a short string in the red channel of an image

options:

  -h, --help            show this help message and exit
  
  -d DECRYPT, --decrypt DECRYPT
  
  -e ENCRYPT, --encrypt ENCRYPT
  
  -m MESSAGE, --message MESSAGE

Examples...

ENCRYPT: python3 picap.py -e cover.jpg -m "secret"

DECRYPT: python3 picap.py -d new.png

BOTH: python3 picap.py -e cover.jpg -m "secret" -d new.png
