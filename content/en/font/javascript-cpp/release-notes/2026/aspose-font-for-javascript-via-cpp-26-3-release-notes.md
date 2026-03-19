---
id: "aspose-font-for-javascript-via-cpp-26-3-release-notes"
slug: "aspose-font-for-javascript-via-cpp-26-3-release-notes"
linktitle: "Aspose.Font for JavaScript via C++ 26.3 Release Notes"
title: "Aspose.Font for JavaScript via C++ 26.3 Release Notes"
description: Javascript APIs to manipulate font files. This page contains new Aspose.Font for JavaScript via C++ features, enhancement, and bug fixes in 2025, version 26.3.
productName: "Aspose.Font for JavaScript via C++"
weight: 100
type: "repository"
layout: "release"
hideChildren: false
toc: true
family_listing_page_title: "Aspose.Font for JavaScript via C++ 26.3 Release Notes"
---

{{% alert color="primary" %}}

This page contains Release Notes for **Aspose.Font for JavaScript via C++ 26.3**

{{% /alert %}}

## Improvements and Changes

Added new functions AsposeFontGetGlyphCount and AsposeFontGetMetrics


## Public API and Backwards Incompatible Changes
### Added APIs
- [**AsposeFontGetMetrics**](https://reference.aspose.com/font/javascript-cpp/glyph/asposefontgetmetrics/)
- [**AsposeFontGetGlyphCount**](https://reference.aspose.com/font/javascript-cpp/glyph/asposefontgetglyphcount/)

{{< highlight js >}}

```html
  var ffileFontGetMetrics = function (e) {
    const file_reader = new FileReader();
    file_reader.onload = (event) => {
      const json = AsposeFontGetMetrics(event.target.result, e.target.files[0].name);
      if (json.errorCode == 0) {
        document.getElementById('output').textContent = 
            "Font metrics: "
            + "\nascent:"               + json.metrics.ascent
            + "\ndescet:"               + json.metrics.descet
            + "\nlineGap:"              + json.metrics.lineGap
            + "\nadvanceWidthMax:"      + json.metrics.advanceWidthMax
            + "\nminLeftSideBearing:"   + json.metrics.minLeftSideBearing
            + "\nminRightSideBearing:"  + json.metrics.minRightSideBearing
            + "\nxMaxExtent:"           + json.metrics.xMaxExtent;
      }
      else document.getElementById('output').textContent = json.errorText;
    }
    file_reader.readAsArrayBuffer(e.target.files[0]);
  }

  var ffileFontGetGlyphCount = function (e) {
    const file_reader = new FileReader();
    file_reader.onload = (event) => {
      const json = AsposeFontGetGlyphCount(event.target.result, e.target.files[0].name);
      if (json.errorCode == 0) {
        document.getElementById('output').textContent = "Glyph count: " + json.glyphCount;
      }
      else document.getElementById('output').textContent = json.errorText;
    }
    file_reader.readAsArrayBuffer(e.target.files[0]);
  }
```
{{< /highlight >}}



