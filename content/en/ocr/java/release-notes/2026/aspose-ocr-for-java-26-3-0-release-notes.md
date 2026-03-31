---
date: "2026-03-30"
id: "aspose-ocr-for-java-26-3-0-release-notes"
slug: "aspose-ocr-for-java-26-3-0-release-notes"
linktitle: "Aspose.OCR for Java 26.3 - Release Notes"
title: "Aspose.OCR for Java 26.3 - Release Notes"
author: "Anna Pylaieva"
weight: 101
description: "A summary of recent changes, enhancements and bug fixes in Aspose.OCR for Java 26.3 (March 2026) release."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.OCR for Java 26.3 - Release Notes"
keywords:
- "2026"
- "March"
- "new"
- "release"
- "changelog"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}
This article contains a summary of recent changes, enhancements and bug fixes in **Aspose.OCR for Java 26.3 (March 2026)** release.

GPU version: **23.10.1**
{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------
OCRJAVA&#8209;460 | Performance and Memory Consumption issue: add enableMemoryPattern and enableCpuMemArena to configure ONNX Runtime. | Enhancement

## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for Java 26.3** that may affect the code of existing applications.

### Added public APIs:

_No changes._

### Updated public APIs:

The following public APIs have been updated in this release:

#### `Aspose.OCR.OnnxRuntimeSessionOptions`

{{% alert color="info" %}}
**Compatibility: fully backward compatible.** See details below.
{{% /alert %}}

Added property ['enableMemoryPattern'](https://reference.aspose.com/ocr/java/com.aspose.ocr.models/onnxruntimesessionoptions/#enableMemoryPattern)

Added property ['enableCpuMemArena'](https://reference.aspose.com/ocr/java/com.aspose.ocr.models/onnxruntimesessionoptions/#enableCpuMemArena)

### Removed public APIs:

_No changes._

## Examples

The code samples below illustrate the changes introduced in this release:


### Detect and recognize tables
```java
import com.aspose.ocr.models.*;

// When enabled saves memory usage but increases execution time
OnnxRuntimeSessionOptions.enableMemoryPattern = true;
OnnxRuntimeSessionOptions.enableCpuMemArena = true;

// Initialize recognition API
AsposeOCR api = new AsposeOCR();

// Add an image to OcrInput object
com.aspose.ocr.OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("source.png");

// Recognize image
com.aspose.ocr.OcrOutput results = api.Recognize(input, set);
```