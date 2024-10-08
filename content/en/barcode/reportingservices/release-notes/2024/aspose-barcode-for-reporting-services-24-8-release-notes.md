---
id: "aspose-barcode-for-reporting-services-24-8-release-notes"
slug: "aspose-barcode-for-reporting-services-24-8-release-notes"
linktitle: "Aspose.BarCode for Reporting Services 24.8 Release Notes"
title: "Aspose.BarCode for Reporting Services 24.8 Release Notes"
weight: 196
description: "Aspose.BarCode for Reporting Services 24.8 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.BarCode for Reporting Services 24.8 Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes information for [Aspose.BarCode for Reporting Services 24.8](https://releases.aspose.com/barcode/reportingservices/new-releases/aspose.barcode-for-reporting-services-24.8/).

{{% /alert %}}
## **All Changes**

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|BARCODENET-38022|AustralianPostShortBarHeight is ignored|Bug + Enhancement + Reopened|
|BARCODENET-38369|Update PZN encoder, decoder|Enhancement|

## Public API changes and backwards compatibility

### AustraliaPost, Planet, Postnet barcodes generation

AustraliaPost, Planet, Postnet barcodes generation is changed.

***AustralianPost.AustralianPostShortBarHeight*** by default is set to zero and calculated by default as 0.26 from ***BarHeight***.
```cs
//AustraliaPost barcode generation
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.AustraliaPost, "6212345678AP");
gen.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable = CustomerInformationInterpretingType.CTable;
gen.Parameters.Barcode.BarHeight.Pixels = 100;

// If short bar is not specified, it is scaled to 0.26 * BarHeight
gen.Parameters.Barcode.AustralianPost.AustralianPostShortBarHeight.Pixels = 10;
gen.Parameters.Barcode.Padding.Left.Pixels = 10;
gen.Parameters.Barcode.Padding.Top.Pixels = 10;
gen.Parameters.Barcode.Padding.Right.Pixels = 10;
gen.Parameters.Barcode.Padding.Bottom.Pixels = 10;
gen.Save("AustraliaPost.png", BarCodeImageFormat.Png);
```

***Postal.PostalShortBarHeight*** by default is set to zero and calculated by default as 0.5 from ***BarHeight***.
```cs
//Planet, Postnet barcodes generation
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Postnet, "5552357000");
gen.Parameters.Barcode.BarHeight.Pixels = 100;

// If short bar is not specified, it is scaled to 0.5 * BarHeight
gen.Parameters.Barcode.Postal.PostalShortBarHeight.Pixels = 40;

gen.Parameters.Barcode.CodeTextParameters.Location = CodeLocation.None;
gen.Parameters.Barcode.Padding.Left.Pixels = 10;
gen.Parameters.Barcode.Padding.Top.Pixels = 10;
gen.Parameters.Barcode.Padding.Right.Pixels = 10;
gen.Parameters.Barcode.Padding.Bottom.Pixels = 10;
```

### PZN7 and PZN8 barcodes generation

PZN8 and PZN7 encoding and decoding are supported:
- To encode PZN7 it is needed to provide 6 digits or less to CodeText, like "123456".
- To encode PZN8 it is needed to provide 7 digits or more to CodeText, like "1234567".
- Provided last checksum digit is ignored and generated by the barcode engine.

```cs
//encode and decode PZN7
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.PZN, "123456"))
using (BarCodeReader reader = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.PZN))
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine(result.CodeTypeName + ":" + result.CodeText);

//encode and decode PZN8
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.PZN, "1234567"))
using (BarCodeReader reader = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.PZN))
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine(result.CodeTypeName + ":" + result.CodeText);
```