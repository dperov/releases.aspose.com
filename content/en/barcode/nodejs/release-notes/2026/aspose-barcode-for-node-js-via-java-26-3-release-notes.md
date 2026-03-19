---
id: "aspose-barcode-for-node-js-via-java-26-3-release-notes"
slug: "aspose-barcode-for-node-js-via-java-26-3-release-notes"
linktitle: "Aspose.BarCode for Node.js via Java 26.3"
title: "Aspose.BarCode for Node.js via Java 26.3"
weight: 960
description: "Aspose.BarCode for Node.js via Java 26.3 – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.BarCode for Node.js via Java 26.3"
menuItemWithNoContent: false
---

{{% alert color="primary" %}} 

This page contains release notes information for [Aspose.BarCode for Node.js via Java 26.3](https://releases.aspose.com/barcode/nodejs/new-releases/aspose.barcode-for-node.js-via-java-26.3/).

{{% /alert %}} 
## **All Changes**

| **Key**           | **Summary**                               | **Category** |
|:------------------|:------------------------------------------|:-------------|
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
```javascript
let generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX, "ASPOSE");
generator.setCodeText("条形码改进", "UTF-8", false);
let img = generator.generateBarCodeImage(BarCodeImageFormat.PNG);

let reader = new BarCodeReader(img, null, DecodeType.DATA_MATRIX);
reader.getBarcodeSettings().setDetectEncoding(true);

const results = reader.readBarCodes();

for (const result of results) {
    console.log(result.getCodeText());
    console.log(result.getCodeTypeName());
}
```


### Extended encoding mode for QR and RectMicroQR

The ***Extended*** encoding mode for ***QR*** and ***RectMicroQR*** barcodes has been fixed.
This improvement ensures correct processing of mixed ECI segments and plain text when using ***QREncodeMode.Extended***.
Previously, certain combinations of ECI-encoded fragments could lead to incorrect encoding or decoding behavior.

In this example, multiple ECI segments with different encodings (Win1251, UTF-8, UTF-16BE)
are correctly encoded and decoded within a single QR barcode using Extended mode.
```javascript
let textBuilder = new QrExtCodetextBuilder();
console.log(QrExtCodetextBuilder);
textBuilder.addECICodetext(ECIEncodings.Win1251, "Will");
textBuilder.addECICodetext(ECIEncodings.UTF8, "犬Right狗");
textBuilder.addECICodetext(ECIEncodings.Win1251, "привет");
textBuilder.addECICodetext(ECIEncodings.UTF16BE, "犬Power狗");
textBuilder.addPlainCodetext("test");
let extCodetext = textBuilder.getExtendedCodetext();

let generator = new BarcodeGenerator(EncodeTypes.QR, extCodetext);
generator.getParameters().getBarcode().getQR().setEncodeMode(QREncodeMode.EXTENDED);

let img = generator.generateBarCodeImage(BarCodeImageFormat.PNG);
let reader = new BarCodeReader(img, null,DecodeType.QR);
reader.getBarcodeSettings().setDetectEncoding(true);
const results = reader.readBarCodes();
for (const result of results) {
    console.log(result.getCodeText());
    console.log(result.getCodeTypeName());
}
```
