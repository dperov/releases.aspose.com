---
date: "2026-04-16"
id: "aspose-barcode-for-net-26-4-release-notes"
slug: "aspose-barcode-for-net-26-4-release-notes"
linktitle: "Aspose.BarCode for .NET 26.4 Release Notes"
title: "Aspose.BarCode for .NET 26.4 Release Notes"
author: "Alexander Gavriluk"
weight: 185
description: "A summary of recent changes, enhancements and bug fixes in Aspose.BarCode for .NET 26.4.0 (April 2026) release."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.BarCode for .NET 26.4 Release Notes"
keywords:
- "2026"
- "April"
- "new"
- "release"
- "changelog"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This article contains release notes information for [**Aspose.BarCode for .NET 26.4 (April 2026)**](https://releases.aspose.com/barcode/net/new-releases/aspose.barcode-for-.net-26.4/).

{{% /alert %}}
## **All Changes**

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|BARCODENET-37951|Add AllowShortBarcodes to BarcodeReader|Enhancement|
|BARCODENET-39527|Improve Postal barcodes recognition engine|Enhancement|

## Features and Improvements

### Improved postal barcode recognition quality

The recognition quality of postal barcode symbologies has been improved, including:
* AustraliaPost
* DutchKIX
* Mailmark
* OneCode
* Planet
* Postnet
* RM4SCC

```cs
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.RM4SCC, "ASPOSE");
gen.Save("test.png");
using (BarCodeReader reader = new BarCodeReader("test.png", DecodeType.AustraliaPost, DecodeType.DutchKIX, DecodeType.Mailmark, DecodeType.OneCode, DecodeType.Planet, DecodeType.Postnet, DecodeType.RM4SCC))
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine(result.CodeText);
```

### Improved recognition of short Code39 barcodes
The recognition quality of short Code39 barcodes (including single-character barcodes) has been improved for the following symbologies:
* Code39
* Code39FullASCII

```cs
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39, "S");
gen.Save("test.png");
using (BarCodeReader reader = new BarCodeReader("test.png", DecodeType.Code39, DecodeType.Code39FullASCII))
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine(result.CodeText);
```
