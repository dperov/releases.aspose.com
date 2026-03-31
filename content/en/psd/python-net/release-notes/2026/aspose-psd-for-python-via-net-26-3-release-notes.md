---
id: "aspose-psd-for-python-via-net-26-3-release-notes"
slug: "aspose-psd-for-python-via-net-26-3-release-notes"
linktitle: "Aspose.PSD for Python via .NET 26.3 - Release Notes"
title: "Aspose.PSD for Python via .NET 26.3 - Release Notes"
weight: 10
description: "Aspose.PSD for Python via .NET 26.3 - Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.PSD for Python via .NET 26.3 - Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes for [Aspose.PSD for Python via .NET 26.3](https://pypi.org/project/aspose-psd/)

{{% /alert %}}

| **Key**       | **Summary**                                                                               | **Category** |
|:--------------|:------------------------------------------------------------------------------------------|:-------------|
| PSDPYTHON-290 | Update processing of parameter Technique-Softer of Outer glow effect on rendering.        | Feature      |
| PSDPYTHON-291 | Warp transformation grid is incorrect for specific cases.                                 | Bug          |
| PSDPYTHON-292 | Rendering of outer glow differs from the original PS rendering noticeable.                | Bug          |
| PSDPYTHON-293 | The warp arc algorithm must be changed.                                                   | Bug          |

## **Public API Changes**

# **Added APIs:**
- None

# **Removed APIs:**
- None

## **Usage examples:**

**PSDPYTHON-290. Update processing of parameter Technique-Softer of Outer glow effect on rendering.**
{{< highlight python >}}
sourceFile = "OuterGlow_Softer.psd"
outputFile = "output_OuterGlow_Softer.png"

loadOpt = PsdLoadOptions()
loadOpt.load_effects_resource = True

with PsdImage.load(sourceFile, loadOpt) as img:
    pngOpt = PngOptions()
    pngOpt.color_type = PngColorType.TRUECOLOR_WITH_ALPHA
    img.save(outputFile, pngOpt)
{{< /highlight >}}

**PSDPYTHON-291. Warp transformation grid is incorrect for specific cases.**
{{< highlight python >}}
sourceFile = "input.psd"
outputFile = "export.png"

loadOpt = PsdLoadOptions()
loadOpt.allow_warp_repaint = True
loadOpt.load_effects_resource = True

pngOpt = PngOptions()
pngOpt.color_type = PngColorType.TRUECOLOR_WITH_ALPHA

with PsdImage.load(sourceFile, loadOpt) as img:
    psdImage = cast(PsdImage, img)
    psdImage.save(outputFile, pngOpt)
{{< /highlight >}}

**PSDPYTHON-292. Rendering of outer glow differs from the original PS rendering noticeable.**
{{< highlight python >}}
sourceFile = "OuterGlow.psd"
outputFile = "output_OuterGlow.png"

loadOpt = PsdLoadOptions()
loadOpt.load_effects_resource = True

pngOpt = PngOptions()
pngOpt.color_type = PngColorType.TRUECOLOR_WITH_ALPHA

with PsdImage.load(sourceFile, loadOpt) as img:
    psdImage = cast(PsdImage, img)
    psdImage.save(outputFile, pngOpt)
{{< /highlight >}}

**PSDPYTHON-293. The warp arc algorithm must be changed.**
{{< highlight python >}}
arcSourceFile = "arc_warp.psd"
arcOutputFile = "arc_export.png"

loadOpt = PsdLoadOptions()
loadOpt.allow_warp_repaint = True
loadOpt.load_effects_resource = True

pngOpt = PngOptions()
pngOpt.color_type = PngColorType.TRUECOLOR_WITH_ALPHA

with PsdImage.load(arcSourceFile, loadOpt) as img:
    psdImage = cast(PsdImage, img)
    psdImage.save(arcOutputFile, pngOpt)

arcvSourceFile = "arc_v_warp.psd"
arcvOutputFile = "arc_v_export.png"

with PsdImage.load(arcvSourceFile, loadOpt) as img:
    psdImage = cast(PsdImage, img)
    psdImage.save(arcvOutputFile, pngOpt)
{{< /highlight >}}
