# Python Barcode Generation & Recognition API

[Product Page](https://www.e-iceblue.com/Introduce/barcode-for-python.html) 丨 [Documentation](https://www.e-iceblue.com/Tutorials.html) 丨 [Examples](https://github.com/eiceblue/Spire.Barcode-for-Python) 丨 [Forum](https://www.e-iceblue.com/forum/spire-barcode-f13.html) 丨 [Temporary License](https://www.e-iceblue.com/TemLicense.html) 丨 [Customized Demo](https://www.e-iceblue.com/Misc/customized-demo.html)

[![Foo](https://imgur.com/nOySOqE.png)](https://www.e-iceblue.com/Introduce/barcode-for-python.html)

**[Spire.Barcode for Python](https://www.e-iceblue.com/Introduce/barcode-for-python.html)** is a powerful and flexible Python API for barcode generation and recognition. It is designed to cater to the needs of developers to integrate barcode processing capabilities into their Python applications. 

With support for various barcode formats, including 1D and 2D barcodes, this library streamlines the procedures involved in generating, reading, and scanning barcodes, making it suitable for a variety of use cases, such as inventory management, product labeling, document tracking, and more.

## Key Features

- **Barcode Generation:** Easily generate barcodes in different formats, such as EAN-13, Code 128, and QR Code.
- **Barcode Recognition:** Accurately detect and decode barcodes, regardless of their orientation or position within an image.
- **Image Processing:** High-quality barcode rendering on a variety of image formats, including Bitmap, JPG, PNG, EMF, TIFF, GIF, and WMF.
- **Customization Options:** Customize barcode images by setting parameters like border style, color, width, and margins. Rotate barcodes at any angle and allow insertion of an image in the center.
- **Easy Integration:**  Seamlessly integrate Spire.Barcode for Python into your application to perform bracode generation & recognition functions with a few lines of code, saving development time and effort.

## Supported Barcode Types:

- CODE_25
- CODABAR
- CODE_11
- INTERLEAVED_25
- CODE_39
- CODE_39_EXTENDED
- CODE_93
- CODE_93_EXTENDED
- CODE_128
- EAN_8
- EAN_13
- EAN_128
- EAN_14
- SCC_14
- SSCC_18
- ITF_14
- ITF_6
- UPCA
- UPCE
- POST_NET
- SINGAPORE_POST_4_STATE
- PLANET
- MSI
- RSS_14
- RSS_14_TRUNCATED
- RSS_LIMITED
- RSS_EXPANDED
- USPS
- SWISS_POST_PARCEL
- PZN
- OPC
- DEUTSCHE_POST_IDENTCODE
- DEUTSCHE_POST_LEITCODE
- ROYAL_MAIL_4_STATE
- DATA_MATRIX
- QR_CODE
- PDF_417
- PDF_417_MACRO



### Generate a Code-128 Barcode in Python

```python
from spire.barcode import *

# Function to write all bytes to a file
def WriteAllBytes(fname: str, data):
    with open(fname, "wb") as fp:
        fp.write(data)
    fp.close()

# Create an instance of BarcodeSettings
barcodeSettings = BarcodeSettings()

# Set the type of barcode to Code128
barcodeSettings.Type = BarCodeType.Code128

# Set the data for the barcode
barcodeSettings.Data = "12345"

# Set the Code128SetMode type of barcode to Auto
barcodeSettings.Code128SetMode = Code128SetMode.Auto

# Create an instance of BarCodeGenerator with the specified settings
barCodeGenerator = BarCodeGenerator(barcodeSettings)

# Generate the image for the barcode
barcodeimage = barCodeGenerator.GenerateImage()

# Write the PNG image to disk
WriteAllBytes("Code128.png", barcodeimage)
```



### Generate QR Code with a Logo Image in Python

```python
from spire.barcode import *

# Function to write all bytes to a file
def WriteAllBytes(fname:str,data):
    fp = open(fname,"wb")
    fp.write(data)
    fp.close()

# Initialize a new instance of BarcodeSettings
barcodeSettings = BarcodeSettings()

# Set the barcode type to QR Code
barcodeSettings.Type = BarCodeType.QRCode

# Specify the background color as WhiteSmoke
barcodeSettings.BackColor = Color.get_WhiteSmoke()

# Set the QR Code data mode to Byte
barcodeSettings.QRCodeDataMode = QRCodeDataMode.Byte

# Choose the error correction level (ECL) as M
barcodeSettings.QRCodeECL = QRCodeECL.M

# Set whether to display text at the bottom of the barcode
barcodeSettings.ShowTextOnBottom = True

# Define the horizontal offset (not sure what this does exactly)
barcodeSettings.X = 3

# Store the data to be encoded in variables and set it on the settings
data = "ABC 123456789"
barcodeSettings.Data2D = data
barcodeSettings.Data = data

# Add a logo image to the QR Code
barcodeSettings.SetQRCodeLogoImage("data/Logo.png")

# Create a new instance of BarCodeGenerator using the provided settings
barCodeGenerator = BarCodeGenerator(barcodeSettings)

# Generate the barcode image
barcodeimage = barCodeGenerator.GenerateImage()

# Write the resulting image to a file
WriteAllBytes("AddLogoImageQRCode.png", barcodeimage)
```



### Scan a Barcode Image in Python

```python
from spire.barcode import *

# Function to append all lines of text to a file
def AppendAllText(fname: str, text: List[str]):
    # Open the file in write mode
    fp = open(fname, "w")

    # Iterate over each line of text
    for s in text:
        # Write the line to the file
        fp.write(s)

    # Close the file handle
    fp.close()

# Use BarcodeScanner class to scan a file using the specified barcode type 
strCode = BarcodeScanner.ScanFileWithBarCodeType("data/QRCode.png",BarCodeType.QRCode)

# Append all scanned strings to a text file
AppendAllText("ScanFileWithBarCodeType.txt",strCode)
```



[Product Page](https://www.e-iceblue.com/Introduce/barcode-for-python.html) 丨 [Documentation](https://www.e-iceblue.com/Tutorials.html) 丨 [Examples](https://github.com/eiceblue/Spire.Barcode-for-Python) 丨 [Forum](https://www.e-iceblue.com/forum/spire-barcode-f13.html) 丨 [Temporary License](https://www.e-iceblue.com/TemLicense.html) 丨 [Customized Demo](https://www.e-iceblue.com/Misc/customized-demo.html)
