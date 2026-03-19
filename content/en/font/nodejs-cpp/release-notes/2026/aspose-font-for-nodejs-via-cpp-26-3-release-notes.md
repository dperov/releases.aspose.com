---
id: "aspose-font-for-nodejs-via-cpp-26-3-release-notes"
slug: "aspose-font-for-nodejs-via-cpp-26-3-release-notes"
linktitle: "Aspose.Font for Node.js via C++ 26.3 Release Notes"
title: "Aspose.Font for Node.js via C++ 26.3 Release Notes"
description: Javascript APIs to manipulate font files. This page contains new Aspose.Font for Node.js via C++ features, enhancement, and bug fixes in 2025, version 26.3.
productName: "Aspose.Font for Node.js via C++"
weight: 100
type: "repository"
layout: "release"
hideChildren: false
toc: true
family_listing_page_title: "Aspose.Font for Node.js via C++ 26.3 Release Notes"
---

{{% alert color="primary" %}}

This page contains Release Notes for **Aspose.Font for Node.js via C++ 26.3**

{{% /alert %}}

## Improvements and Changes

Added new functions AsposeFontGetGlyphCount and AsposeFontGetMetrics


## Public API and Backwards Incompatible Changes
### Added APIs
- [**AsposeFontGetMetrics**](https://reference.aspose.com/font/nodejs-cpp/glyph/asposefontgetmetrics/)
- [**AsposeFontGetGlyphCount**](https://reference.aspose.com/font/nodejs-cpp/glyph/asposefontgetglyphcount/)

{{< highlight js >}}

```html
    json = AsposeFontModule.AsposeFontGetMetrics(font_file);
    console.log("AsposeFontGetMetrics => %O",  json.errorCode == 0 ? JSON.parse(JSON.stringify(json).replace('"errorCode":0,"errorText":"",','')) : json.errorText);

    json = AsposeFontModule.AsposeFontGetGlyphCount(font_file);
    console.log("AsposeFontGetGlyphCount => %O",  json.errorCode == 0 ? "Glyph count:" + json.glyphCount : json.errorText);
```
{{< /highlight >}}



