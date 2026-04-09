---
id: "aspose-words-for-cpp-26-3-release-notes"
slug: "aspose-words-for-cpp-26-3-release-notes"
linktitle: "Aspose.Words for C++ 26.3 Release Notes"
title: "Aspose.Words for C++ 26.3 Release Notes"
weight: 60
description: "Aspose.Words for C++ 26.3 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.Words for C++ 26.3 Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes for [Aspose.Words for C++ 26.3](https://www.nuget.org/packages/Aspose.Words.Cpp/26.3.0).

{{% /alert %}}

{{% alert color="primary" %}}

A comprehensive description of all classes, methods, and properties, along with code examples, is available on the [API reference pages](https://reference.aspose.com/words/cpp/).

{{% /alert %}}

## Major Features

There are most notable improvements and fixes in this regular monthly release:

- **AI Integration:** Added the ability to create an instance of the [OpenAiModel](https://reference.aspose.com/words/cpp/aspose.words.ai/openaimodel/) class directly.
- **Document Optimization:** Extended the functionality of the [JoinRunsWithSameFormatting](https://reference.aspose.com/words/cpp/aspose.words/document/joinrunswithsameformatting/) method for more comprehensive content merging.
- **Rendering and Fonts:** Improved the MS Office font fallback table for the CJK Unified Ideographs Extension G range.

## Full List of Issues Covering all Changes in this Release

<details>

<summary>Expand to view the full list of reported issues.</summary>

1. Allow to create instance of OpenAiModel class directly
2. Support MSO properties during import tabs
3. MathML: mmultiscripts is incorrectly imported
4. Incorrect rendering of SVG when the gradient is specified with 'objectBoundingBox' and exceeds the path bounds
5. InvalidOperationException is thrown upon saving document as DOCX
6. SVG gradient in userSpaceOnUse coordinates is rendered incorrectly
7. Unexpected DocumentBuilder behavior when moving inside SDT
8. Import of MsoHtml lists differs from MS Word's result
9. List items are imported from MsoHtml as normal paragraphs
10. DOCX to PDF: Headers and footers disappear after section break
11. FileCorruptedException is thrown upon loading '.wml' document
12. ArgumentOutOfRangeException is thrown upon using AutoFitBehavior.AutoFitToWindow
13. SVG color gradients are corrupted when exporting to DOC
14. SVG color gradients are corrupted when exporting to PDF
15. Compare result does not match MS Word
16. NullReferenceException is thrown upon building document layout
17. Layout issue when converting DOCX to PDF
18. RTF to PDF: Converting the file raises an exception
19. Chinese character is rendered as missed character
20. TOC is split into two parts in the document structure
21. Gradient is lost after rendering SVG
22. Metafile is rendered incorrectly in Vector mode
23. IndexOutOfRangeException is thrown upon building document layout
24. Numbering is changed after exporting to HTML
25. Document.AcceptAllRevisions does not accept all revisions
26. ODT file fails to load with FileCorruptedException
27. NullReferenceException is thrown upon exporting to HTML with ExportListLabels.ByHtmlTags
28. DOCX to PDF: Additional spacing at the start of paragraph
29. JoinRunsWithSameFormatting does not join runs
30. Remove obsolete TableStyle.Bidi property
31. Table is slightly shifted right after rendering
32. Exporting list labels by HTML tags does not work

</details>

## Limitations and API Differences

Aspose.Words for C++ has some differences as compared to its equivalent .NET version of the API. This section contains information about all such functionality that is not available in the current release. The missing features will be added in future releases.

- The current release does not support Metered license.
- The current release does not support LINQ and Reporting features.
- The current release does not support OpenGL 3D Shapes rendering.
- The current release does not support loading PDF documents.
- The current release does not support printing.
- The current release has limited support for database features. C++ doesn't have a common API for DB like .NET System.Data.
- The current release supports Microsoft Visual C++ version 2019 or higher.
- The current release supports Clang 3.9.1 or higher on Linux and only for the x86_x64 platform.
- The current release supports macOS Monterey or later (12.0+) for the 64-bit Intel Mac platform.
