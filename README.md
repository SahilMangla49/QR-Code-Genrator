# QR-Code-Genrator
# QR Code Generator with Logo Overlay

This project shows how to generate a QR code from a URL and overlay an image (such as a logo) onto the QR code using Python. The QR code library used is `qrcode`, and `Pillow` (PIL) is used for image processing.
# code
*1.import libraries*
import qrcode 
from PIL import Image

*2.generate qr code*
`github_url = 'https://github.com/SahilMangla49'  
qr_img = qrcode.make(github_url)
qr_img = qr_img.convert('RGB')`

*3.load the logo*
`logo = Image.open('sahil.jpg')
logo = logo.convert("RGBA")`

*4.set dimensions of logo*
`qr_width, qr_height = qr_img.size
logo_size = int(qr_width / 4)
logo = logo.resize((logo_size, logo_size))`

*5.set position of logo in qr code*
`pos = ((qr_width - logo_size) // 2, (qr_height - logo_size) // 2)
qr_img.paste(logo, pos, mask=logo)`

*6.save the qr*
`qr_img.save('Github_qr.png')
qr_img.show()`

