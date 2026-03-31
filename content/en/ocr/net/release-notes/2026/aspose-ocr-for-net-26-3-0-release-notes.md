---
date: "2026-03-30"
id: "aspose-ocr-for-net-26-3-0-release-notes"
slug: "aspose-ocr-for-net-26-3-0-release-notes"
linktitle: "Aspose.OCR for .NET 26.3 - Release Notes"
title: "Aspose.OCR for .NET 26.3 - Release Notes"
author: "Anna Pylaieva"
weight: 101
description: "A summary of recent changes, enhancements and bug fixes in Aspose.OCR for .NET 26.3 (March 2026) release."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.OCR for .NET 26.3 - Release Notes"
keywords:
- "2026"
- "March"
- "new"
- "release"
- "changelog"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}
This article contains a summary of recent changes, enhancements and bug fixes in [**Aspose.OCR for .NET 26.3 (March 2026)**](https://www.nuget.org/packages/Aspose.OCR/26.3.0) release.

GPU version: **26.3.0**
{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------

OCRNET&#8209;1199 | Performance and Memory Consumption issue: add EnableCpuMemArena and EnableMemoryPattern to configure ONNX Runtime. | Enhancement

## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for .NET 26.3** that may affect the code of existing applications.

### Added public APIs:

_No changes._

### Updated public APIs:

The following public APIs have been updated in this release:

#### `Aspose.OCR.OnnxRuntimeSessionOptions`

{{% alert color="info" %}}
**Compatibility: fully backward compatible.** See details below.
{{% /alert %}}

Added property ['EnableCpuMemArena'](https://reference.aspose.com/ocr/net/aspose.ocr/onnxruntimesessionoptions/enablecpumemarena/)

Added property ['EnableMemoryPattern'](https://reference.aspose.com/ocr/net/aspose.ocr/onnxruntimesessionoptions/enablememorypattern/)


### Removed public APIs:

_No changes._

## Examples

The code samples below illustrate the changes introduced in this release:

### OnnxRuntimeSessionOptions
```csharp

// When enabled saves memory usage but increases execution time
Aspose.OCR.OnnxRuntimeSessionOptions.EnableCpuMemArena = true;
Aspose.OCR.OnnxRuntimeSessionOptions.EnableMemoryPattern = true;

Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Configure recognition settings if needed
Aspose.OCR.RecognitionSettings settings = new Aspose.OCR.RecognitionSettings();
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```