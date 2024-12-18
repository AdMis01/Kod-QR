# Kod-QR
Generowanie statycznych kodów QR

Najpierw trzeba zainstalować dodatki:

```
python.exe -m pip install --upgrade pip

pip install qrcode

pip install Pillow
```
Zaczynamy z podpięciem biblioteki do pliku
```
import qrcode
```
Tutaj podajemy dane jakie chcemy umieścić w link URL lub jakiś tekst
```
data = "https://github.com/"
```
Konfigurowanie wyglądu 
- verion - odpowiada za wersję rozmiarową kodu QR
- box_size - wielkość kwadratów 
- error_correction - korekcja błędów
- border - jaką wielkość ma mieć ramka 
```
qr = qrcode.QRCode(
    version=1,
    error_correction=qrcode.constants.ERROR_CORRECT_L,
    box_size=10,
    border=4,
)
qr.add_data(data)
qr.make(fit=True)
```
Tworzenie i zapisywanie kodu QR
```
img = qr.make_image(fill='black', back_color='white')
img.save("qr_code.png")
```
![qr_code](https://github.com/user-attachments/assets/2e257c8f-f65c-4ca7-9e44-7a758ed942fd)
