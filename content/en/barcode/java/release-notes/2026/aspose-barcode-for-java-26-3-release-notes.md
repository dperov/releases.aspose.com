---
id: "aspose-barcode-for-java-26-3-release-notes"
slug: "aspose-barcode-for-java-26-3-release-notes"
linktitle: "Aspose.BarCode for Java 26.3 Release Notes"
title: "Aspose.BarCode for Java 26.3 Release Notes"
weight: 9700
description: "Aspose.BarCode for Java 26.3 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.BarCode for Java 26.3 Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes information
for [Aspose.BarCode for Java 26.3](https://releases.aspose.com/barcode/java/26-3/).

{{% /alert %}}

## **All Changes**

| **Key**             | **Summary**                                                                                                             | **Category** |
|:--------------------|:------------------------------------------------------------------------------------------------------------------------|:-------------|
|BARCODENET-38718|Detect Unicode charsets in 2D barcodes|Enhancement|
|BARCODENET-39516|Fix ExtendedCodetext mode in QR encoder|Bug|

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

```java
//In this example, UTF-8 encoded Chinese text is correctly detected and decoded from a DataMatrix barcode.

public void example1() {
    BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DATA_MATRIX);
    gen.setCodeText("条形码改进", StandardCharsets.UTF_8);

    BarCodeReader reader = new BarCodeReader(gen.generateBarCodeImage(), DecodeType.DATA_MATRIX);
    reader.getBarcodeSettings().setDetectEncoding(true);
    BarCodeResult[] results = reader.readBarCodes();
    for (BarCodeResult result : results)
    {
        System.out.printf("CodeText: %s%n", result.getCodeText());
        System.out.printf("CodeType: %s%n", result.getCodeType());
    }
}
```


### Extended encoding mode for QR and RectMicroQR

The ***Extended*** encoding mode for ***QR*** and ***RectMicroQR*** barcodes has been fixed. 
This improvement ensures correct processing of mixed ECI segments and plain text when using ***QREncodeMode.Extended***. 
Previously, certain combinations of ECI-encoded fragments could lead to incorrect encoding or decoding behavior.

```java
//In this example, multiple ECI segments with different encodings (Win1251, UTF-8, UTF-16BE) 
// are correctly encoded and decoded within a single QR barcode using Extended mode.

public void example2() {
    QrExtCodetextBuilder textBuilder = new QrExtCodetextBuilder();
    textBuilder.addECICodetext(ECIEncodings.Win1251, "Will");
    textBuilder.addECICodetext(ECIEncodings.UTF8, "犬Right狗");
    textBuilder.addECICodetext(ECIEncodings.Win1251, "привет");
    textBuilder.addECICodetext(ECIEncodings.UTF16BE, "犬Power狗");
    textBuilder.addPlainCodetext("test");
    String extCodetext = textBuilder.getExtendedCodetext();

    BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.QR, extCodetext);
    gen.getParameters().getBarcode().getQR().setEncodeMode(QREncodeMode.EXTENDED);

    BarCodeReader reader = new BarCodeReader(gen.generateBarCodeImage(), DecodeType.QR);
    reader.getBarcodeSettings().setDetectEncoding(true);
    BarCodeResult[] results = reader.readBarCodes();
    for (BarCodeResult result : results)
    {
        System.out.printf("CodeText: %s%n", result.getCodeText());
        System.out.printf("CodeType: %s%n", result.getCodeType());
    }
}
```
