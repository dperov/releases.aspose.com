---
id: "aspose-diagram-for-python-via-net-26-4-release-notes"
slug: "aspose-diagram-for-python-via-net-26-4-release-notes"
linktitle: "Aspose.Diagram for Python via .NET 26.4 Release Notes"
title: "Aspose.Diagram for Python via .NET 26.4 Release Notes"
weight: 24
description: "Aspose.Diagram for Python via .NET 26.4 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
---

{{% alert color="primary" %}} 

This page contains release notes for Aspose.Diagram for Python via .NET 26.4.

{{% /alert %}} 

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|DIAGRAMNET-53920|VST file has missing images in PDF output|Enhancement|
|DIAGRAMNET-53923|Fails to load Aspose.Drawing.Common assembly at runtime|Enhancement|
|DIAGRAMNET-53922|Problem when exporting a Visio document to HTML|Bug|
|DIAGRAMNET-53924|There’s a white strip on the left side of the PDF when first to HTML then to PDF|Bug|
|DIAGRAMNET-53925|Text and links are not renderes at right position from vsdx to pdf|Bug|
|DIAGRAMNET-53926|Duplicate chart shapes appear outside the Visio page when you convert VSD to VSDX|Bug|
|DIAGRAMNET-53931|PDF content not visible after saving as HTML|Bug|

## **Public API and Backward Incompatible Changes**
The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Diagram for .NET. If you have concerns about any change listed, please raise it on the Aspose.Diagram support forum.
### **Adds Svg in LoadFileFormat**
-  Svg file format.

{{< highlight java >}}
 Diagram diagram = new Diagram("input.svg",LoadFileFormat.Svg);
{{< /highlight >}}
