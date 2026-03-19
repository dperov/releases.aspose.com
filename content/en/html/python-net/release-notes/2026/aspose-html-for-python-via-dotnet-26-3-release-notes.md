---
id: "aspose-html-for-python-via-dotnet-26-3-release-notes"
slug: "aspose-html-for-python-via-dotnet-26-3-release-notes"
linktitle: "Aspose.HTML for Python via .NET 26.3 Release Notes"
title: "Aspose.HTML for Python via .NET 26.3 Release Notes"
weight: 100
description: "Enhanced HTML to PDF conversion with tag support, improved grid alignment, expanded MHTML attachments API, SVG text attributes fixes, and rendering upgrades."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.HTML for Python via .NET 26.3 Release Notes"
menuItemWithNoContent: false
---
{{% alert color="primary" %}}
This page contains release notes information for Aspose.HTML for Python via .NET 26.3.
{{% /alert %}}

As per the regular monthly update process of all APIs being offered by Aspose, we are honored to announce the March release of Aspose.HTML for Python via .NET.

In this release, the conversion to PDF with tag support has been improved, and the alignment of the grid layout has been improved. The API for working with attachments in MHTML format has also been expanded, and attributes of text elements in SVG format have been fixed. In addition, this release includes numerous improvements to the rendering engine when calculating the layout for blocks, tables, flexbox, and grid layouts.

**Package references**<br>
Aspose.HTML for .NET 26.3.0 [NuGet](https://www.nuget.org/packages/Aspose.Html)<br>
Aspose.HTML.Drawing for .NET 26.3.0 [NuGet](https://www.nuget.org/packages/Aspose.Html.Drawing)<br>
Aspose.HTML for Python via .NET  26.3.0 [PyPI](https://pypi.org/project/aspose-html-net/)


## **Improvements and Changes**

| **Key**      | **Summary**                                                                            | **Category** |
| ------------ | -------------------------------------------------------------------------------------- | ------------ |
| HTMLNET-6528 | MHTML: Ability to select and render specific attachments | Feature |
| HTMLNET-6205 | MHT to PDF - embedded images are missing in the output | Bug |
| HTMLNET-6967 | HTML-to-Tagged-PDF: <dl>/<dt>/<dd> definition lists incorrectly mapped to L/LI structure elements — PDF/UA “inappropriate LI” warning (v26.x) | Bug |

## **Public API Changes**

###  ** Added APIs **

| Module / Class | Member |
|----------------|--------|
| `aspose.html.rendering.MhtmlAttachmentInfo` | `.MhtmlAttachmentInfo()` method |
| `aspose.html.rendering.MhtmlAttachmentInfo` | `.url` property |
| `aspose.html.rendering.MhtmlAttachmentInfo` | `.content_type` property |
| `aspose.html.rendering.MhtmlAttachmentInfo` | `.content_location` property |
| `aspose.html.rendering.MhtmlAttachmentInfo` | `.content_id` property |
| `aspose.html.rendering.MhtmlAttachmentInfo` | `.file_name` property |
| `aspose.html.rendering.MhtmlAttachmentInfo` | `.size` property |
| `aspose.html.rendering.MhtmlAttachments` | `.get_attachment_urls(source_stream)` method |
| `aspose.html.rendering.MhtmlAttachments` | `.get_attachment_info(source_stream)` method |
