---
date: "2026-03-16"
id: "aspose-barcode-for-net-26-3-release-notes"
slug: "aspose-barcode-for-net-26-3-release-notes"
linktitle: "Aspose.BarCode for .NET 26.3 Release Notes"
title: "Aspose.BarCode for .NET 26.3 Release Notes"
author: "Alexander Gavriluk"
weight: 190
description: "A summary of recent changes, enhancements and bug fixes in Aspose.BarCode for .NET 26.3.0 (March 2026) release."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.BarCode for .NET 26.3 Release Notes"
keywords:
- "2026"
- "March"
- "new"
- "release"
- "changelog"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This article contains release notes information for [**Aspose.BarCode for .NET 26.3 (March 2026)**](https://releases.aspose.com/barcode/net/new-releases/aspose.barcode-for-.net-26.3/).

{{% /alert %}}
## **All Changes**

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|BARCODENET-37745|Reading barcodes from PDF - barcode is not recognized|Bug|
|BARCODENET-38384|Recognition of EAN barcodes while barcode read type is set to UPC|Bug|
|BARCODENET-38386|Reader detects fragments of Code39Extended instead of VIN |Bug|
|BARCODENET-38387|Add option to BarCodeReader to recognize only required barcode types|Enhancement|

## Public API changes and New Features

### OnlyRequestedTypes property for strict barcode type filtering
The ***OnlyRequestedTypes*** property has been added to ***BarcodeSettings***.

When enabled, ***BarCodeReader*** returns only barcode types explicitly specified in the decoding settings. Compatible or equivalent barcode types are excluded from the results, even if they can be successfully recognized.

When disabled, compatible and equivalent barcode types may be returned according to internal type mapping (for example, EAN-13 may also be returned when UPC-A is specified as the decoding type).

```cs
//generate EAN13 barcode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN13, "2383823482894"))
    generator.Save(@"c:\test.png");
//recognize only UPCA barcodes (no results, because source is EAN13)
using (BarCodeReader reader = new BarCodeReader(@"c:\test.png", DecodeType.UPCA))
{
    reader.BarcodeSettings.OnlyRequestedTypes = true;
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("BarCode CodeText: " + result.CodeText);
}
//recognize compatible types: EAN13, UPCA, ISSN, ISMN, ISBN (EAN13 will be returned as UPCA-equivalent)
using (BarCodeReader reader = new BarCodeReader(@"c:\test.png", DecodeType.UPCA))
{
    reader.BarcodeSettings.OnlyRequestedTypes = false;
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("BarCode CodeText: " + result.CodeText);
}
```
