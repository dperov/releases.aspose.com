---
date: "2026-04-07"
id: "aspose-ocr-for-java-26-4-0-release-notes"
slug: "aspose-ocr-for-java-26-4-0-release-notes"
linktitle: "Aspose.OCR for Java 26.4 - Release Notes"
title: "Aspose.OCR for Java 26.4 - Release Notes"
author: "Anna Pylaieva"
weight: 91
description: "A summary of recent changes, enhancements and bug fixes in Aspose.OCR for Java 26.4 (April 2026) release."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.OCR for Java 26.4 - Release Notes"
keywords:
- "2026"
- "April"
- "new"
- "release"
- "changelog"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}
This article contains a summary of recent changes, enhancements and bug fixes in **Aspose.OCR for Java 26.4 (April 2026)** release.

GPU version: **23.10.1**
{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------
OCRJAVA&#8209;462 | Started table-detection model integration: model selection, ONNX conversion, Java validation, and preprocessing setup. Added `DetectTables` API for table region detection. | New feature

## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for Java 26.4** that may affect the code of existing applications.

### Added public APIs:

The following public APIs have been introduced in this release:

#### `Aspose.OCR.AsposeOCR.DetectTables` - a new method

Detects table regions in input images and returns a list of `RectangleOutput`.

`RectangleOutput` contains:
- `Source` - the full path to the file or URL.
- `Page` - page number.
- `Rectangles` - list of detected table rectangles.

**New Methods**
| Method                                                 | Description                                         |
| ------------------------------------------------------ | --------------------------------------------------- |
| `ArrayList<RectangleOutput> DetectTables(OcrInput images)` | Detects tables and returns `ArrayList<RectangleOutput>`. |

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
```java
import com.aspose.ocr.AsposeOCR;
import com.aspose.ocr.OcrInput;
import com.aspose.ocr.models.InputType;
import com.aspose.ocr.models.RectangleOutput;
import java.awt.Rectangle;
import java.util.ArrayList;

// Initialize recognition API
AsposeOCR api = new AsposeOCR();

// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("source.png");

// Detect table regions
ArrayList<RectangleOutput> tables = api.DetectTables(input);

// Print result
for (RectangleOutput table : tables) {
    System.out.println("Source: " + table.Source);
    System.out.println("Page: " + table.Page);
    if (table.Rectangles != null) {
        for (Rectangle rect : table.Rectangles) {
            System.out.println(
                "Rect: x=" + rect.x +
                ", y=" + rect.y +
                ", w=" + rect.width +
                ", h=" + rect.height
            );
        }
    }
}
```
