---
date: "2026-04-07"
id: "aspose-ocr-python-26-4-0-release-notes"
slug: "aspose-ocr-python-26-4-0-release-notes"
linktitle: "Aspose.OCR for Python via .NET 26.4 - Release Notes"
title: "Aspose.OCR for Python via .NET 26.4 - Release Notes"
author: "Anna Pylaieva"
weight: 91
description: "A summary of recent changes, enhancements and bug fixes in Aspose.OCR for Python via .NET 26.4 (April 2026) release."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.OCR for Python via .NET 26.4 - Release Notes"
keywords:
- "2026"
- "April"
- "new"
- "release"
- "changelog"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}
This article contains a summary of recent changes, enhancements and bug fixes in **Aspose.OCR for Python via .NET 26.4 (April 2026)** release.
{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------
OCRNET&#8209;108 | Started table-detection model integration: model selection, ONNX conversion, Python via .NET validation, and preprocessing setup. Added `detect_tables` API for table region detection. | New feature

## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for Python via .NET 26.4** that may affect the code of existing applications.

### Added public APIs:

The following public APIs have been introduced in this release:

#### `aspose.ocr.AsposeOcr.detect_tables` - a new method

Detects table regions in input images and returns a list of `RectangleOutput` objects.

**New Methods**
| Method                  | Description                                  |
| ----------------------- | -------------------------------------------- |
| `detect_tables(images)` | Detects tables and returns `list[RectangleOutput]`. |

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

```python
import os
from aspose.ocr import *
from aspose.ocr.models import *

lic = License()
lic.set_license(self.licPath)

# // Initialize an instance of AsposeOcr
api = AsposeOcr()

# // Detect table regions
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("table.jpg")

results = api.detect_tables(input)

for result in results:
    for rect in result.rectangles:
        print(rect)
```
