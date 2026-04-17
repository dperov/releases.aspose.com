---
id: "aspose-page-for-nodejs-cpp-26-4-release-notes"
slug: "aspose-page-for-nodejs-cpp-26-4-release-notes"
linktitle: "Aspose.Page for Node.js via C++ Release Notes"
title: "Aspose.Page for Node.js via C++ Release Notes"
description: Node.js APIs to manipulate and PS, EPS, and XPS files. This page contains new Aspose.Page for Node.js C++ features.
productName: "Aspose.Page for Node.js via C++"
weight: 10
type: "repository"
layout: "release"
hideChildren: false
toc: true
family_listing_page_title: "Aspose.Page for Node.js via C++ Release Notes"
---

{{% alert color="primary" %}}

This page contains release notes information for **Aspose.Page for Node.js via C++ 26.4**.

{{% /alert %}}


## Major Features

Added a function `AsposePSGetBoundingBox` tat extract bounding box of eps image, and `AsposePSExtractText` that extract text from PS-document.


## Public API and Backwards Incompatible Changes
### Added APIs
- [**AsposePSGetBoundingBox**](https://reference.aspose.com/page/nodejs-cpp/ps/psgetboundingbox/) - Get bounds of PS file.
- [**AsposePSExtractText**](https://reference.aspose.com/page/nodejs-cpp/ps/psextracttext/) - Extract text from PS file.

```
const AsposePage = require('asposepagenodejs');

const xps_file = "./data/example.xps";
const ps_file = "./data/program_20.ps";

console.log("Aspose.Page for Node.js via C++ examples.");

AsposePage().then(AsposePageModule => {

    let json = AsposePageModule.AsposePageAbout();
    console.log("AsposePageAbout => %O",  json.errorCode == 0 ? JSON.parse(JSON.stringify(json).replace('"errorCode":0,"errorText":"",','')) : "error:" + json.errorText);

    json = AsposePageModule.AsposePSGetBoundingBox(ps_file);
    console.log("PSGetBoundingBox => %O",  json.errorCode == 0 ? JSON.parse(JSON.stringify(json).replace('"errorCode":0,"errorText":"",','')) : json.errorText);

    json = AsposePageModule.AsposePSExtractText(ps_file);
    console.log("PSExtractText => %O",  json.errorCode == 0 ? JSON.parse(JSON.stringify(json).replace('"errorCode":0,"errorText":"",','')) : json.errorText);

},
    reason => {console.log(`The unknown error has occurred: ${reason}`);}
);
```

For more details see [Aspose.Page for Node.js Documentation](https://docs.aspose.com/page/nodejs-cpp/).

