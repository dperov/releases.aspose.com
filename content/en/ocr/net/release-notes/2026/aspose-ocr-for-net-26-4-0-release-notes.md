---
date: "2026-04-07"
id: "aspose-ocr-for-net-26-4-0-release-notes"
slug: "aspose-ocr-for-net-26-4-0-release-notes"
linktitle: "Aspose.OCR for .NET 26.4 - Release Notes"
title: "Aspose.OCR for .NET 26.4 - Release Notes"
author: "Anna Pylaieva"
weight: 91
description: "A summary of recent changes, enhancements and bug fixes in Aspose.OCR for .NET 26.4 (April 2026) release."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.OCR for .NET 26.4 - Release Notes"
keywords:
- "2026"
- "April"
- "new"
- "release"
- "changelog"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}
This article contains a summary of recent changes, enhancements and bug fixes in [**Aspose.OCR for .NET 26.4 (April 2026)**](https://www.nuget.org/packages/Aspose.OCR/26.4.0) release.

GPU version: **26.4.0**
{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------

#OCRNET&#8209;1201 | Initial table-detection model integration: model selection, ONNX conversion, .NET validation, and preprocessing setup. Added `DetectTables` API for table region detection. | New feature

## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for .NET 26.4** that may affect the code of existing applications.

### Added public APIs:

The following public APIs have been introduced in this release:

#### [`Aspose.OCR.AsposeOcr.DetectTables`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/detecttables/) - a new method

Detects table regions in input images and returns their bounding rectangles as a list of `RectangleOutput`.

**New Methods**
| Method                         | Description                                              |
| ------------------------------ | -------------------------------------------------------- |
| [`public List<RectangleOutput> DetectTables(OcrInput images)`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/detecttables/)| Detects tables and returns `List<RectangleOutput>`.      |

{{% alert color="info" %}}
**Compatibility: fully backward compatible.** See details below.
{{% /alert %}}

### Updated public APIs:

_No changes._


### Removed public APIs:

_No changes._

## Examples

The code samples below illustrate the changes introduced in this release:

### Detect table regions
```csharp

Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");

// Detect table regions
System.Collections.Generic.List<Aspose.OCR.RectangleOutput> tables = recognitionEngine.DetectTables(input);

// Print result
Console.WriteLine($"Detected table regions: {tables.Count}");
```

### Recognize text in detected table regions
```csharp

using Drawing = System.Drawing;

Aspose.OCR.AsposeOcr api = new Aspose.OCR.AsposeOcr();
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");

List<Drawing.Rectangle> tables = api.DetectTables(input)[0].Rectangles;
var res = api.Recognize(input, new Aspose.OCR.RecognitionSettings { RecognitionAreas = tables });
```
