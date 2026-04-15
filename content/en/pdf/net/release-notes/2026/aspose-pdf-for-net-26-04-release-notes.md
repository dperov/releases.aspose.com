---
id: "aspose-pdf-for-net-26-4-release-notes"
slug: "aspose-pdf-for-net-26-4-release-notes"
linktitle: "Aspose.PDF for .NET 26.4"
title: "Aspose.PDF for .NET 26.4"
weight: 120
description: "This page contains new Aspose.PDF for .NET features, enhancements, and bug fixes in 2026, version 26.4."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.PDF for .NET 26.4"
lastmod: "2026-04-14"
sitemap:
  changefreq: "monthly"
  priority: 0.7
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.PDF for .NET 26.4.

{{% /alert %}}



## Improvements and Changes

### Features and Enhancements

#### Improved PDF to Image Conversion Performance

Aspose.PDF for .NET 26.4 includes significant performance improvements for PDF to image conversion. This enhancement addresses `PDFNET-41182`, where converting PDF pages to JPEG images had been reported as taking too long, with each page requiring several seconds to process.

With this update, the same scenario shows a much faster conversion time, making high-volume image export workflows more efficient when rasterizing PDF pages to JPEG format.

Here is an example of how to use this enhancement:

```csharp
// For complete examples and data files, visit https://github.com/aspose-pdf/Aspose.PDF-for-.NET
private static void ConvertPdfToJpeg()
{
    // The path to the documents directory
    var dataDir = RunExamples.GetDataDir_AsposePdf_DocumentConversion();

    // Open PDF document
    using (var pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf"))
    {
        for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
        {
            using (var imageStream = new System.IO.FileStream(
                dataDir + string.Format("page{0}.jpg", pageCount),
                System.IO.FileMode.Create))
            {
                // Create Resolution object
                var resolution = new Aspose.Pdf.Devices.Resolution(300);

                // Create JPEG device with specified resolution
                var jpegDevice = new Aspose.Pdf.Devices.JpegDevice(resolution);

                // Convert a particular page and save the image to stream
                jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            }
        }
    }
}
```

#### PDF/UA Structure Tree Processing Performance Improvement

Aspose.PDF for .NET 26.4 improves the performance of `PdfUaConvertStrategy.Process_7_1_structureTree` when working with large PDF documents. This enhancement addresses issue `PDFNET-61884`, where CPU profiling identified the `pageMCIDs.Contains(key)` call as the primary performance bottleneck during structure tree processing.

By replacing the `List<string>` lookup with a `HashSet<ulong>` and introducing a composite key instead of relying on string formatting, this update delivers a significant performance boost when converting large PDF documents to PDF/UA format.

Here is an example of how to use this enhancement:

```csharp
// For complete examples and data files, visit https://github.com/aspose-pdf/Aspose.PDF-for-.NET
private static void ConvertToPdfUa()
{
    // The path to the documents directory
    var dataDir = RunExamples.GetDataDir_AsposePdf_DocumentConversion();

    // Open PDF document
    using (var document = new Aspose.Pdf.Document(dataDir + "input.pdf"))
    {
        // Convert to PDF/UA format
        document.Convert(dataDir + "log.xml", Aspose.Pdf.PdfFormat.PDF_UA_1, Aspose.Pdf.ConvertErrorAction.Delete);

        // Save converted document
        document.Save(dataDir + "output.pdf");
    }
}
```

### Bug Fixing and Other Changes

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
| PDFNET-40078 | Incorrect Evaluation watermark text is added in PDF document | Bug |
| PDFNET-40844 | Large HTML to PDF conversion performance isuse | Bug |
| PDFNET-41019 | Page orientation changes when adding Table in Header | Bug |
| PDFNET-41212 | Oswald font is not reflecting as excepted in new generator | Bug |
| PDFNET-61886 | UB (Undefined Behaviour) in TransparentContentRemoval.AddStoredImage | Bug |
| PDFNET-39275 | HTML to PDF - Significant loss of Fidelity in resultant file | Bug |
| PDFNET-39279 | PDF to XPS: resultant XPS is missing images. | Bug |
| PDFNET-39281 | PDF to DOCX - Bottom and Right table borders do not appear | Bug |
| PDFNET-39288 | Unable to validate PDF/A_1b compliance of document | Bug |
| PDFNET-39306 | PDF to PDF/A - Resultant file is not PDF/A_2a compliant | Bug |
| PDFNET-39309 | Multithreading issue PNGDevice | Bug |
| PDFNET-39314 | XPS to PDFA: background color of some elements changed | Bug |
| PDFNET-39315 | XPS to PDFA: Image is converting partially and background color is changed | Bug |
| PDFNET-39320 | PageNumberStamp is not being displayed | Bug |
| PDFNET-39752 | save() throws out of memory when data overlaps on the footer area | Bug |
| PDFNET-39753 | PDF to PNG - Conversion process is taking much time | Bug |
| PDFNET-39758 | PDF to PDF/A - Signature appears black after conversion | Bug |
| PDFNET-39942 | PDF to PNG results into an incorrect image | Bug |
| PDFNET-39960 | Footnote layout issues when line spacing is applied | Bug |
| PDFNET-40001 | Deleting first child bookmark in nested bookmark | Bug |
| PDFNET-40094 | Open and Resave the PDF corrupts output | Bug |
| PDFNET-40116 | Pdf form fields become flatten after saving the file | Bug |
| PDFNET-40119 | Corrupted watermark when using API in trial mode | Bug |
| PDFNET-40131 | PDF to PDF/A - Text justification is changed | Bug |
| PDFNET-40147 | TIFF to PDF: conversion performance issue with large image files | Bug |
| PDFNET-40167 | PDF to HTML: throws OutOfMemoryException | Bug |
| PDFNET-40176 | PDF conversion to any format drops images | Bug |
| PDFNET-40193 | PDF stamp produces display issue of embedded fonts | Bug |
| PDFNET-40197 | PDF to PDFA2b: resultant PDFA2b document loses the annotations | Bug |
| PDFNET-40205 | PDF to PNG - Resultant image shows dark banding | Bug |
| PDFNET-40803 | PDF to HTML: resultant HTML has invalid characters | Bug |
| PDFNET-40861 | Issue in adding header/footer to PDF generated from excel | Bug |
| PDFNET-40865 | Issue in adding header/footer to PDF generated from PPTX | Bug |
| PDFNET-40877 | Form fields contents disappear after Form resize | Bug |
| PDFNET-40879 | MHT to PDF: images are missing in resultant PDF | Bug |
| PDFNET-40971 | PDF to PDFA: cuts page contents | Bug |
| PDFNET-40978 | PDF to PDFA: Object z-order issue | Bug |
| PDFNET-40979 | PDF to PDFA: Object z-order issue | Bug |
| PDFNET-40980 | PDF to PDFA: Object z-order issue | Bug |
| PDFNET-41021 | Assigning name to image corrupts the PDF file | Bug |
| PDFNET-41036 | Stamping PDF document deforms the contents | Bug |
| PDFNET-41142 | PDF to DOCX - Incorrect font name | Bug |
| PDFNET-41154 | Exception when trying to flatten PDF file | Bug |
| PDFNET-41162 | PDF to PDFA: transparent image issue | Bug |
| PDFNET-41168 | Modifying CheckBoxField border changes the checkmark size | Bug |
| PDFNET-41171 | PDF to PDF/A - Formatting issues in resultant file | Bug |
| PDFNET-41172 | Vertical text rendering issue in read only fields with same name | Bug |
| PDFNET-41174 | Vertical text is rendering as horizontal text in flatten PDF form | Bug |
| PDFNET-41175 | TIF to PDF: resultant PDF is empty | Bug |
| PDFNET-41177 | PDF to PDF/A - Image is inverted in resultant file | Bug |
| PDFNET-41197 | XPS to PDF - Missing contents in resultnat file | Bug |
| PDFNET-41204 | Fill color issue with rounded corner rectangle | Bug |
| PDFNET-41248 | Exception when trying to flatten PDF form fields | Bug |
| PDFNET-41278 | Aspose PDF printing - character encoding for nordic characters | Bug |
| PDFNET-41351 | PDF to DOCX: font issue in page footer | Bug |
| PDFNET-41366 | PDF to PDF/A - Resultant file is not compliant | Bug |
| PDFNET-41378 | PDF to PDF/A - Resultant file is not compliant | Bug |
| PDFNET-41379 | PDF to PDFA: resultant PDFA1a file does not fails PDFA conformance verification | Bug |
| PDFNET-41396 | Replacing text does not rearrange | Bug |
| PDFNET-41447 | Attachment is broken when using FileStream | Bug |
| PDFNET-41453 | API throws NullReference Exception during optimization | Bug |
| PDFNET-41458 | API hangs while saving PDF document | Bug |
| PDFNET-41483 | PDF to JPEG: PDF page images are not rendering in resultant JPEG images | Bug |
| PDFNET-60408 | Aspose.PDF 25.7: Converting a particular PDF to JPG/TIFF results in corrupted characters in the output. | Bug |
| PDFNET-61176 | Convert a PDF that contains XFA forms TO PDF and try to flatten it, the process fails and corrupts the file | Bug |
| PDFNET-61219 | PDF to TIFF: incorrect output rendering | Bug |
| PDFNET-61646 | PDF to DOCX: Converting file raises an OverflowException | Bug |
| PDFNET-61653 | Invalid font name when subsetting fonts on PDF with embedded bold font in TOC | Bug |
| PDFNET-61705 | Convert pdf to image results in notdef glyphs - .NET 10 | Bug |
| PDFNET-61777 | PDF to XPS conversion produces excessively large XPS for scanned PDFs | Bug |
| PDFNET-61900 | IncorrectFontUsageException is thrown | Bug |
| PDFNET-61931 | When opening with Acrobat document, that converted from XPS to PDF, an error message appears. | Bug |
| PDFNET-61993 | Conversion of PDF => PDF/A_2B of a particular PDF file fails | Bug |
| PDFNET-61999 | PDF TO XPS: Cannot find table 'post' in the font file. | Bug |

## Public API and Backward Incompatible Changes

### Added APIs

No addings.

### Removed APIs

No removings.


### Backward Incompatible Changes

No changes.

