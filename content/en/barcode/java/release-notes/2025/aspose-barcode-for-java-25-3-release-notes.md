---
id: "aspose-barcode-for-java-25-3-release-notes"
slug: "aspose-barcode-for-java-25-3-release-notes"
linktitle: "Aspose.BarCode for Java 25.3 Release Notes"
title: "Aspose.BarCode for Java 25.3 Release Notes"
weight: 960
description: "Aspose.BarCode for Java 25.3 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.BarCode for Java 25.3 Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes information
for [Aspose.BarCode for Java 25.3](https://releases.aspose.com/barcode/java/25-3/).

{{% /alert %}}

## **All Changes**

| **Key**           | **Summary**                                                                                   | **Category** |
|:------------------|:----------------------------------------------------------------------------------------------|:-------------|
| BARCODENET-37360  | Add QualitySettings support to PBase processor                                                | Enhancement  |
| BARCODENET-39209  | Make generation of BarCodeImageFormat.Pdf format system independent                           | Bug          |
| BARCODEJAVA-1329  | While processing the license for .NET the exception message and exception class are incorrect | Bug          |

## Public API changes and backwards compatibility

### Recognition quality and speed of 1D processors
The recognition quality and speed of ***PBase*** processors have been improved.
These improvements apply to the following symbologies: PatchCode, Pharmacode.
The recognition speed of most 1D processors has been improved with updates to the 1D recognition engine.

### Barcode region detection
Fixed a bug with incorrect barcode region detection when the
[Image](https://learn.microsoft.com/dotnet/api/system.drawing.image) property [RotateFlipType](https://learn.microsoft.com/dotnet/api/system.drawing.rotatefliptype)
changes the picture orientation.

### PDF encoder
Fixed a bug with differences in created PDF files that depended on system localization.

```java
public void generatePDF() throws IOException
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "Aspose");
    generator.save("code128.pdf", BarCodeImageFormat.PDF);
}
```