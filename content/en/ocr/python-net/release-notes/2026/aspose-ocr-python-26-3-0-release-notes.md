---
date: "2026-03-30"
id: "aspose-ocr-python-26-3-0-release-notes"
slug: "aspose-ocr-python-26-3-0-release-notes"
linktitle: "Aspose.OCR for Python via .NET 26.3 - Release Notes"
title: "Aspose.OCR for Python via .NET 26.3 - Release Notes"
author: "Anna Pylaieva"
weight: 101
description: "A summary of recent changes, enhancements and bug fixes in Aspose.OCR for Python via .NET 26.3 (March 2026) release."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.OCR for Python via .NET 26.3 - Release Notes"
keywords:
- "2026"
- "March"
- "new"
- "release"
- "changelog"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}
This article contains a summary of recent changes, enhancements and bug fixes in **Aspose.OCR for Python via .NET 26.3 (March 2026)** release.
{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------
OCRNET&#8209;1199 | Performance and Memory Consumption issue: add set_enable_memory_pattern and set_enable_cpu_mem_arena to configure ONNX Runtime. | Enhancement

 ## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for Python via .NET 26.3** that may affect the code of existing applications.

### Added public APIs:

_No changes._

### Updated public APIs:

The following public APIs have been updated in this release:

#### `Aspose.OCR.OnnxRuntimeSessionOptions`

{{% alert color="info" %}}
**Compatibility: fully backward compatible.** See details below.
{{% /alert %}}

Added property ['set_enable_memory_pattern'](https://reference.aspose.com/ocr/python-net/aspose.ocr/onnxruntimesessionoptions/)

Added property ['set_enable_cpu_mem_arena'](https://reference.aspose.com/ocr/python-net/aspose.ocr/onnxruntimesessionoptions/)


### Removed public APIs:

_No changes._

## Examples

The code samples below illustrate the changes introduced in this release:

### OnnxRuntimeSessionOptions

```python
from aspose.ocr.models import *


# Initialize recognition API
api = new AsposeOcr()

# ONNX runtime settings
OnnxRuntimeSessionOptions.set_intra_op_num_threads(1)
OnnxRuntimeSessionOptions.set_graph_optimization_level(GraphOptimizationLevelOnnx.ORT_ENABLE_EXTENDED)
OnnxRuntimeSessionOptions.set_execution_mode(ExecutionModeOnnx.ORT_SEQUENTIAL)
OnnxRuntimeSessionOptions.set_inter_op_num_threads(1)

# When enabled saves memory usage but increases execution time
OnnxRuntimeSessionOptions.set_enable_memory_pattern(True)
OnnxRuntimeSessionOptions.set_enable_cpu_mem_arena(True)

# Add an image to OcrInput object
input = new OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")

# Recognize image
results = api.recognize(input)

```