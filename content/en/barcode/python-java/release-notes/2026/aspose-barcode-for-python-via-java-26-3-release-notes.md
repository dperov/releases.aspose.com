---
id: "aspose-barcode-for-python-via-java-26-3-release-notes"
slug: "aspose-barcode-for-python-via-java-26-3-release-notes"
linktitle: "Aspose.BarCode for Python via Java 26.3"
title: "Aspose.BarCode for Python via Java 26.3"
weight: 960
description: "Aspose.BarCode for Python via Java 26.3 – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.BarCode for Python via Java 26.3"
menuItemWithNoContent: false
---

{{% alert color="primary" %}} 

This page contains release notes information for [Aspose.BarCode for Python via Java 26.3](https://releases.aspose.com/barcode/python-java/new-releases/aspose.barcode-for-python-via-java-26.3/).

## Important notice for the next release



{{% /alert %}} 
## **All Changes**

| **Key**           | **Summary**                                                                                                             | **Category** |
|:------------------|:------------------------------------------------------------------------------------------------------------------------|:-------------|
| BARCODENET-38718  | Detect Unicode charsets in 2D barcodes    | Enhancement  |
| BARCODENET-39516  | Fix ExtendedCodetext mode in QR encoder   | Bug          |

## Features and Improvements

### DetectEncoding property extended to all 2D barcodes

The ***DetectEncoding*** property in ***BarCodeReader*** has been extended.
Previously, automatic encoding detection was supported only for QR Code.
Starting from this release, encoding detection is available for all supported 2D barcode types:
- Aztec
- DataMatrix
- MacroPdf417
- Pdf417
- MicroPdf417
- QR
- MicroQR
- CompactPdf417
- MaxiCode
- DotCode
- HanXin
- RectMicroQR

When ***DetectEncoding*** is set to ***true***, the reader automatically determines the correct character
encoding used during barcode generation.
This allows proper decoding of UTF-8 and other multibyte encoded content without manual encoding configuration.

In this example, UTF-8 encoded Chinese text is correctly detected and decoded from a DataMatrix barcode.
```python
def example1(self):
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, "ASPOSE")
    generator.set_code_text("条形码改进", "UTF-8", False)
    img = generator.generate_barcode_image()
    reader = BarCodeReader(img, DecodeType.DATA_MATRIX)
    reader.barcode_settings.detect_encoding = True
    results = reader.read_barcodes()
    print("=== Result ===")
    for result in results:
        print("CodeText =", result.code_text())
        print("CodeType =", result.code_type_name)
```


### Extended encoding mode for QR and RectMicroQR

The ***Extended*** encoding mode for ***QR*** and ***RectMicroQR*** barcodes has been fixed.
This improvement ensures correct processing of mixed ECI segments and plain text when using ***QREncodeMode.Extended***.
Previously, certain combinations of ECI-encoded fragments could lead to incorrect encoding or decoding behavior.

In this example, multiple ECI segments with different encodings (Win1251, UTF-8, UTF-16BE)
are correctly encoded and decoded within a single QR barcode using Extended mode.
```python
def example2(self):
    # Build extended QR codetext with multiple ECI segments
    text_builder = QrExtCodetextBuilder()
    text_builder.add_eci_codetext(ECIEncodings.Win1251, "Will")
    text_builder.add_eci_codetext(ECIEncodings.UTF8, "犬Right狗")
    text_builder.add_eci_codetext(ECIEncodings.Win1251, "привет")
    text_builder.add_eci_codetext(ECIEncodings.UTF16BE, "犬Power狗")
    text_builder.add_plain_codetext("test")
    ext_codetext = text_builder.extended_codetext()
    # Create QR generator in EXTENDED mode
    generator = BarcodeGenerator(EncodeTypes.QR, ext_codetext)
    generator.parameters.barcode.qr.encode_mode = QREncodeMode.EXTENDED
    # Generate barcode image
    img = generator.generate_barcode_image()
    # Read QR barcode
    reader = BarCodeReader(img, DecodeType.QR)
    reader.barcode_settings.detect_encoding = True
    results = reader.read_barcodes()
    print("=== Result ===")
    for result in results:
        print("CodeText =", result.code_text())
        print("CodeType =", result.code_type_name)
```
