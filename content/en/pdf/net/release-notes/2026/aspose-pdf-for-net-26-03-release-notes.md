---
id: "aspose-pdf-for-net-26-3-release-notes"
slug: "aspose-pdf-for-net-26-3-release-notes"
linktitle: "Aspose.PDF for .NET 26.3"
title: "Aspose.PDF for .NET 26.3"
weight: 120
description: "This page contains new Aspose.PDF for .NET features, enhancements, and bug fixes in 2026, version 26.3."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.PDF for .NET 26.3"
lastmod: "2026-03-13"
sitemap:
  changefreq: "monthly"
  priority: 0.7
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.PDF for .NET 26.3.

{{% /alert %}}

## Improvements and Changes

### Features and Enhancements

#### Lossless Image Stream Recompression During PDF Optimization

Aspose.PDF for .NET 26.3 enhances PDF optimization by recompressing lossless image streams. As a follow-up to the previously resolved issue `PDFNET-61177`, the `OptimizationOptions.CompressAllContentStreams` property now also compresses image XObject streams with the lossless `FlateDecode` filter when no other filter has already been applied to an image.

This enhancement addresses `PDFNET-61251` and helps further reduce optimized PDF file size while preserving image quality. It was introduced to narrow the optimization gap observed when comparing Aspose.PDF output with qpdf in lossless compression scenarios, especially for documents containing PNG, TIFF, RAW, and similar image streams.

Here is an example of how to use this enhancement:

```csharp
// For complete examples and data files, visit https://github.com/aspose-pdf/Aspose.PDF-for-.NET
private static void OptimizePdfWithLosslessImageStreamRecompression()
{
    // The path to the documents directory
    var dataDir = RunExamples.GetDataDir_AsposePdf_WorkingDocuments();

    // Open PDF document
    using (var document = new Aspose.Pdf.Document(dataDir + "input.pdf"))
    {
        // Configure optimization options
        var optimizeOptions = new Aspose.Pdf.Optimization.OptimizationOptions
        {
            SubsetFonts = true,
            AllowReusePageContent = true,
            CompressObjects = true,
            LinkDuplicateStreams = true,
            RemoveUnusedObjects = true,
            RemoveUnusedStreams = true,
            // Compress content streams and eligible image streams
            CompressAllContentStreams = true,
        };

        // Optimize PDF document
        document.OptimizeResources(optimizeOptions);

        // Save optimized PDF document
        document.Save(dataDir + "output.pdf");
    }
}
```

#### Image Compression Encoding During PDF Optimization

Aspose.PDF for .NET 26.3 improves image optimization behavior by encoding images in accordance with the value specified in `ImageCompressionOptions.Encoding`. This enhancement addresses `PDFNET-61163`, where optimized output images were previously stored as JPEG even when `Jpeg2000` or `Flate` had been requested.

With this change, image recompression is now aligned with the selected encoding during optimization, making the results more predictable when resizing images, limiting resolution, and tuning quality settings.

Here is an example of how to use this enhancement:

```csharp
// For complete examples and data files, visit https://github.com/aspose-pdf/Aspose.PDF-for-.NET
private static void OptimizePdfImagesWithSelectedEncoding()
{
    // The path to the documents directory
    var dataDir = RunExamples.GetDataDir_AsposePdf_WorkingDocuments();

    // Open PDF document
    using (var pdf = new Aspose.Pdf.Document(dataDir + "input.pdf"))
    {
        // Configure optimization options
        var optimizeOptions = new Aspose.Pdf.Optimization.OptimizationOptions
        {
            AllowReusePageContent = false,
            CompressObjects = true,
            LinkDuplicateStreams = false,
            RemoveUnusedObjects = true,
            RemoveUnusedStreams = true,
            ImageCompressionOptions =
            {
                CompressImages = true,
                ResizeImages = true,
                MaxResolution = 150,
                ImageQuality = 90,
                Encoding = Aspose.Pdf.Optimization.ImageEncoding.Flate,
                Version = Aspose.Pdf.Optimization.ImageCompressionVersion.Mixed
            }
        };

        // Optimize PDF document resources
        pdf.OptimizeResources(optimizeOptions);

        // Save optimized PDF document
        pdf.Save(dataDir + "output.pdf");
    }
}
```

#### Render Comments When Saving as Image or HTML

Aspose.PDF for .NET 26.3 now supports rendering comments when saving PDF documents as an image or HTML. This new feature addresses `PDFNET-42693` and makes it possible to preserve comment visibility in exported output formats instead of limiting them to PDF viewers only.

This feature is useful for review workflows where annotated documents need to be shared as PNG images or HTML pages while keeping comment information visible in the exported result.

Here is an example of how to use this feature:

```csharp
// For complete examples and data files, visit https://github.com/aspose-pdf/Aspose.PDF-for-.NET
private static void RenderCommentsToImageAndHtml()
{
    // The path to the documents directory
    var dataDir = RunExamples.GetDataDir_AsposePdf_Annotations();

    // Open PDF document
    using (var pdfDoc = new Aspose.Pdf.Document(dataDir + "pdf_with_comments.pdf"))
    {
        // Save the first page to PNG with comments rendered
        var device = new Aspose.Pdf.Devices.PngDevice();
        device.Process(pdfDoc.Pages[1], dataDir + "comments_out.png");

        // Save the first page to HTML with comments rendered
        var options = new Aspose.Pdf.HtmlSaveOptions
        {
            ExplicitListOfSavedPages = new[] { 1 },
            UseZOrder = true
        };

        pdfDoc.Save(dataDir + "comments_out.html", options);
    }
}
```

#### Improved PDF to TIFF Rendering Performance

Aspose.PDF for .NET 26.3 includes performance improvements for PDF to TIFF rendering. This enhancement addresses `PDFNET-40575`, where TIFF conversion had been reported as significantly slower than alternative tools for the provided sample document.

With this update, the same scenario shows a much faster conversion time in local verification, making high-volume rasterization workflows more efficient when exporting PDF pages to bitonal TIFF images.

Here is an example of how to use this enhancement:

```csharp
// For complete examples and data files, visit https://github.com/aspose-pdf/Aspose.PDF-for-.NET
private static void ConvertPdfToTiff()
{
    // The path to the documents directory
    var dataDir = RunExamples.GetDataDir_AsposePdf_DocumentConversion();

    // Open PDF document
    var pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");

    // Create Resolution object
    var resolution = new Aspose.Pdf.Devices.Resolution(300);

    // Create TiffSettings object
    var tiffSettings = new Aspose.Pdf.Devices.TiffSettings
    {
        Compression = Aspose.Pdf.Devices.CompressionType.CCITT4,
        Shape = Aspose.Pdf.Devices.ShapeType.None,
        SkipBlankPages = false,
        Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp
    };

    // Create TIFF device
    var tiffDevice = new Aspose.Pdf.Devices.TiffDevice(resolution, tiffSettings);

    for (int i = 1; i <= pdfDocument.Pages.Count; i++)
    {
        string targetFilename = dataDir + "Asposeout-" + i + ".tif";
        tiffDevice.Process(pdfDocument, i, i, targetFilename);
    }
}
```

### Other Notable Enhancements

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
| PDFNET-40691 | High memory usage with RemoveUnusedStreams optimization property | Enhancement |

### Bug Fixing and Other Changes

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
| PDFNET-40224 | Some objects are not converted to GrayScale | Bug |
| PDFNET-40233 | Document resaved corrupts the document | Bug |
| PDFNET-40245 | Flattening the PDF Form loses form field text | Bug |
| PDFNET-40267 | PDF to PDFA1b: text is missing in resultant PDFA | Bug |
| PDFNET-40282 | PDF to JPEG: resulant image is black | Bug |
| PDFNET-40314 | PDF to PDF/A - Resultant file is not PDF/A_1b compliant | Bug |
| PDFNET-40335 | PDF to XPS: font changed in resultant XPS | Bug |
| PDFNET-40338 | Exception when trying to convert Optimized PDF file to PDF/A format | Bug |
| PDFNET-40341 | Text replacement issue using regular expression | Bug |
| PDFNET-40376 | HTML to PDF conversion- display:none style is not honored | Bug |
| PDFNET-40383 | HTMl to PDF - Tooltip is not properly rendering | Bug |
| PDFNET-40386 | PDF to HTML - Text in resultant file is garbled | Bug |
| PDFNET-40390 | Validate method is showing errors when validating PDF/A_1b compliant file | Bug |
| PDFNET-40399 | PDF to PDF/A - Pages become black in resultant file | Bug |
| PDFNET-40406 | HTML to PDF - TOC is having incorrect destination for links | Bug |
| PDFNET-40431 | Loading and saving PDF document overlaps the characters | Bug |
| PDFNET-40443 | PDF to PDF/A_3b - Text formatting in resultant file | Bug |
| PDFNET-40483 | PDF to JPG conversion results in distorted images | Bug |
| PDFNET-40486 | PDF to PDF/A - Formatting issues in resultnat file | Bug |
| PDFNET-40495 | PDF to HTML: background images are missing | Bug |
| PDFNET-40503 | Header object moves lower in every subsequent PDF page | Bug |
| PDFNET-40516 | PDF to PDF_X_1A - Resultant file is not compliant | Bug |
| PDFNET-40522 | PDF to DOCX - Missing contents and misaligned fractions | Bug |
| PDFNET-40534 | HTML to PDF: Large HTML file(5MB) is not converted | Bug |
| PDFNET-40541 | PDF to XPS conversion generates invalid file | Bug |
| PDFNET-40546 | PDF to DOC conversion throws OutOfMemmory Exception | Bug |
| PDFNET-40547 | XPS to PDF: vertical text is not rendered correctly | Bug |
| PDFNET-40549 | PdfJavaScriptStripper is throwing NullReference Exception | Bug |
| PDFNET-40558 | PDF to DOCX - Formatting issues in resultant file | Bug |
| PDFNET-40576 | Slow XPS loading when using X64 as target platform | Bug |
| PDFNET-40599 | Page contents become blank during file concatenation | Bug |
| PDFNET-40635 | Text searching hangs system by consumes its whole memory | Bug |
| PDFNET-40658 | Exception when trying to concatenate PDF files generated by Aspose.Words | Bug |
| PDFNET-40697 | ResizeContents results a blank document | Bug |
| PDFNET-40714 | Incorrect page number for TOC elements | Bug |
| PDFNET-40720 | HTML to PDF - Header and Footer not appearing on subsequent pages | Bug |
| PDFNET-40729 | Concatenate method of PdfFileEditor object is throwing NullReference Exception | Bug |
| PDFNET-40738 | PDF to HTML: local hyperlinks are not rendered | Bug |
| PDFNET-40739 | PDF to HTML: bold text is being rendered as regular text | Bug |
| PDFNET-40740 | PDF to HTML: underlines are being rendered incorrectly | Bug |
| PDFNET-40751 | PDF to Excel Conversion (Merged Columns are coming as one column) | Bug |
| PDFNET-40752 | Unable to open concatenated PDF file | Bug |
| PDFNET-40767 | Error viewing document after resizing page | Bug |
| PDFNET-50318 | "Index was outside the bounds of the array." exception when open document | Bug |
| PDFNET-55002 | Mention important updates in documentation | Bug |
| PDFNET-60368 | File size increases drastically when embedding chinese fonts after filling form fields | Bug |
| PDFNET-61361 | PDF/A-2B conversion removes math characters when using OpenType MATH fonts | Bug |
| PDFNET-61455 | Overlay text with Unicode characters becomes corrupted after applying redaction annotation | Bug |
| PDFNET-61542 | Remove not used const | Bug |
| PDFNET-61707 | Harmful side effects in isolated code of Aspose.Pdf | Bug |
| PDFNET-61724 | TextFragmentAbsorber rectangle coordinates do not align with visually rotated text | Bug |
| PDFNET-61801 | Text incorrectly detected as Invisible | Bug |
| PDFNET-61808 | PDF/UA Conversion Hangs on Large PDF Files with Excessive Memory Consumption | Bug |
| PDFNET-61822 | Converting HTML to PDF Very Slow with Large HTML Text | Bug |

## Public API and Backward Incompatible Changes

### Added APIs

* Method: Aspose.Pdf.PageCollection.BeginUpdate System.Void
* Method: Aspose.Pdf.PageCollection.EndUpdate System.Void

### Removed APIs

No removings.

### Backward Incompatible Changes

* The compatibility package `Aspose.PDF for .NET Framework 4.0 (DLLs only)` is no longer published beginning with Aspose.PDF for .NET 26.3.
