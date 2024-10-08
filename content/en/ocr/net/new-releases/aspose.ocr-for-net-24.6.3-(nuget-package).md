---

title: "Aspose.OCR .NET 24.6.3 | US Passport OCR & More (NuGet)"
description: "Extract US passport details & embed custom fonts in PDFs with Aspose.OCR for .NET 24.6.3 for API developers.  Download NuGet for .NET platforms."
keywords: ""
page_type: single_release_page
folder_link: "/ocr/net/new-releases/aspose.ocr-for-net-24.6.3-(nuget-package)/"
folder_name: "Aspose.OCR for NET 24.6.3 (NuGet package)"
download_link: "/ocr/net/new-releases/aspose.ocr-for-net-24.6.3-(nuget-package)/843caeec63250dce140eb14025d25508-28-11136"
download_text: "Download"
intro_text: "MemoryPack support (updated)"
image_link: "/resources/img/random-file-icon.png"
download_count: " 2/7/2024 Downloads: 1  Views: 1 "
file_size: "File Size: 135.08MB"
parent_path: "ocr/net"
section_parent_path: "ocr/net"

tags: "OCR, NET"
release_notes_url: "https://releases.aspose.com/ocr/net/release-notes/2024/aspose-ocr-for-net-24-6-0-release-notes/"
weight: 358

---

{{< Releases/ReleasesWapper >}}
  {{< Releases/ReleasesHeading H2txt="Aspose.OCR for NET 24.6.3 (NuGet package)" imagelink="/resources/img/random-file-icon.png">}}
  {{< Releases/ReleasesButtons >}}
    {{< Releases/ReleasesSingleButtons text="Download" link="/ocr/net/new-releases/aspose.ocr-for-net-24.6.3-(nuget-package)/843caeec63250dce140eb14025d25508-28-11136" >}}
    {{< Releases/ReleasesSingleButtons text="Support Forum" link="https://forum.aspose.com/c/ocr" >}}
  {{< Releases/ReleasesButtons >}}
  {{< Releases/ReleasesFileArea >}}
    {{< Releases/ReleasesHeading h4txt="File Details">}}
    {{< Releases/ReleasesDetailsUl >}}
      {{< Common/li >}} Downloads: {{< /Common/li >}}
      {{< Common/li class="downloadcount" id="dwn-update-843caeec63250dce140eb14025d25508-28-11136" >}} 1 {{< /Common/li >}}
      {{< Common/li >}} File Size: {{< /Common/li >}}
      {{< Common/li id="size-update-843caeec63250dce140eb14025d25508-28-11136" >}} 135.08MB {{< /Common/li >}}

      {{< Common/li >}} Date Added: {{< /Common/li >}}
      {{< Common/li id="added-update-843caeec63250dce140eb14025d25508-28-11136" >}}2/7/2024 {{< /Common/li >}}
    {{< /Releases/ReleasesDetailsUl >}}

  {{< Releases/ReleasesFileFeatures >}}
      <h4>Release Notes</h4><div><a href='https://releases.aspose.com/ocr/net/release-notes/2024/aspose-ocr-for-net-24-6-0-release-notes/'>https://releases.aspose.com/ocr/net/release-notes/2024/aspose-ocr-for-net-24-6-0-release-notes/</a></div>
  {{< /Releases/ReleasesFileFeatures >}}
  {{< Releases/ReleasesFileFeatures >}}
      <h4>Description</h4><div class="HTMLDescription">It contains Aspose.OCR for .NET 24.6.3 (NuGet package) release.</div>
  {{< /Releases/ReleasesFileFeatures >}}

{{< Releases/ReleasesHeading h4txt="Notable Features">}}
{{< Common/wrapper class="HTMLDescription">}}
{{% Releases/ReleasesFileFeatures %}}  

### US Passport OCR
The latest NuGet package version of Aspose.OCR for .NET 24.6.3 introduces a feature that allows API developers to extract crucial information such as names, numbers, and dates of birth from US passport images.

Here is a code example illustrating how to extract details from the US passport image: 

```c#

Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add scanned passport to recognition batch
OcrInput passports = new OcrInput(InputType.SingleImage);
passports.Add("us_passport_sample.png");
// Explicitly specify that you are processing US passport
var recognitionSettings = new PassportRecognitionSettings();
recognitionSettings.Country = Aspose.OCR.Country.USA;
// Recognize passport
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizePassport(passports, recognitionSettings);
// Parse passport data and output essential details along with image regions they were found in
var details = results[0].GetKeywords();
foreach (var item in details)
{
	Console.WriteLine($"{item.Key}: {item.Value.TextInLine}");
	Console.WriteLine($"Left: {item.Value.Line.X}; top: {item.Value.Line.Y}; size: {item.Value.Line.Width} x {item.Value.Line.Height}");
}

```
*[Source\*](https://releases.aspose.com/ocr/net/release-notes/2024/aspose-ocr-for-net-24-6-0-release-notes/)*

### Custom Fonts in PDF
We have added support for embedding custom `TrueType` or `OpenType` fonts into PDF documents generated from OCR results with this .NET OCR API release.

Font embedding code example: 

```c#

Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Recognize images
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input);
// Save results as text-only PDF in Adobe Ming font
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.PdfNoImg, results, "fonts/AdobeMingStd-Light.otf");

```
*[Source\*](https://releases.aspose.com/ocr/net/release-notes/2024/aspose-ocr-for-net-24-6-0-release-notes/)*

### Deprecation Update
`Aspose.OCR.Country.UNIVERSAL` has been replaced by `Aspose.OCR.Country.NONE`. The legacy codes will continue to run and will be supported until January 2025.

### Public API Changes

- Updated API: Added `Aspose.OCR.Country.NONE` for skipping the parsing of passport details.
- Updated Method: `RecognitionResult.Save()` and `AsposeOcr.SaveMultipageDocument()` now support an `embeddedFontPath` parameter for font embedding.


> You can view the list of all new features, enhancements, and bug fixes introduced in this release by visiting [Aspose.OCR for .NET 24.6.3 Release Notes](https://releases.aspose.com/ocr/net/release-notes/2024/aspose-ocr-for-net-24-6-0-release-notes/).


{{% /Releases/ReleasesFileFeatures %}}

{{< /Common/wrapper >}}
{{< /Releases/ReleasesFileFeatures >}}

 {{< /Releases/ReleasesFileArea >}}
{{< /Releases/ReleasesWapper >}}


