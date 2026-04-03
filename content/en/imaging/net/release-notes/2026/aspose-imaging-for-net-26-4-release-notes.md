---
id: aspose-imaging-for-net-26-4-release-notes
slug: aspose-imaging-for-net-26-4-release-notes
linktitle: Aspose.Imaging for .NET 26.4 - Release notes
title: Aspose.Imaging for .NET 26.4 - Release notes
weight: 46
description: Aspose.Imaging for .NET 26.4 - Release notes the latest updates and fixes.
type: repository
layout: release
hideChildren: false
toc: false
family_listing_page_title: Aspose.Imaging for .NET 26.4 - Release notes
menuItemWithNoContent: false
---

## Competitive features:

- **Implement partial GDIRendering**

| **Key**         | **Summary**                                                                                                                                                              | **Category** |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| IMAGINGNET-7906 | Implement partial GDIRendering                                                                                                                                  | Feature      |
| IMAGINGNET-7986 | Fix bug on export to Pdf for images without own stream                                                                                                                                  | Enhancement      |
| IMAGINGNET-7872 | CDR to WEBP IndexOutOfRangeException                                                                                                                                  | Enhancement      |
| IMAGINGNET-7818 | MemMgr crushes at the moment of its finalization                                                                                                                                  | Enhancement      |
| IMAGINGNET-7747 | JPG file colors are incorrectly read                                                                                                                                  | Enhancement      |
| IMAGINGNET-4696 | CDR to PDF - Image Loading Failed                                                                                                                                  | Enhancement      |

## Public API changes:

### Added APIs:

Class    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode

Class    Aspose.Imaging.ImageFilters.FilterOptions.ImageBlendingFilterOptions

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Color

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.ColorBurn

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.ColorDodge

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Darken

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Difference

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Exclusion

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.HardLight

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Hue

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Lighten

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Luminosity

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Multiply

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Normal

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Overlay

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Saturation

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.Screen

Field/Enum    Aspose.Imaging.ImageFilters.FilterOptions.BlendingMode.SoftLight

Method    Aspose.Imaging.Exif.ExifData.#ctor(System.Byte[])

Method    Aspose.Imaging.Exif.ExifData.GetTagValue(Aspose.Imaging.Exif.ExifProperties)

Method    Aspose.Imaging.ImageFilters.FilterOptions.ImageBlendingFilterOptions.#ctor

Property    Aspose.Imaging.Exif.ExifData.XResolution

Property    Aspose.Imaging.Exif.ExifData.YResolution

Property    Aspose.Imaging.ImageFilters.FilterOptions.ConvolutionFilterOptions.BordersProcessing

Property    Aspose.Imaging.ImageFilters.FilterOptions.ConvolutionFilterOptions.IgnoreAlpha

Property    Aspose.Imaging.ImageFilters.FilterOptions.ImageBlendingFilterOptions.BlendingMode

Property    Aspose.Imaging.ImageFilters.FilterOptions.ImageBlendingFilterOptions.Image

Property    Aspose.Imaging.ImageFilters.FilterOptions.ImageBlendingFilterOptions.Opacity

Property    Aspose.Imaging.ImageFilters.FilterOptions.ImageBlendingFilterOptions.Position



### Removed APIs:

## Usage Examples:

**IMAGINGNET-7986 Fix bug on export to Pdf for images without own stream**

{{< highlight csharp >}}

Png to Pdf conversion:
using var image = new PngImage(32, 32, PngColorType.TruecolorWithAlpha);
var outputStream = new MemoryStream();
image.Save(outputStream, new PdfOptions());

{

{{< /highlight >}}

**IMAGINGNET-7906 Implement partial GDIRendering**

{{< highlight csharp >}}

using (var image = Image.Load("D:\\test.cdr"))
  {
     image.Save("D:\\test.png", new PngOptions(){VectorRasterizationOptions  = new CdrRasterizationOptions() { Positioning = PositioningTypes.Relative }});
  }

{

{{< /highlight >}}

**IMAGINGNET-7872 CDR to WEBP IndexOutOfRangeException**

{{< highlight csharp >}}

var fileName = "sample.cdr";
  using var image = Image.Load(fileName);
  var pages = (image as IMultipageImage).Pages;
  for (var i = 0; i < pages.Length; i++)
  {
      VectorRasterizationOptions rasterizationOptions = new CdrRasterizationOptions
      {
          PageWidth = Convert.ToInt32(pages[i].Width),
          PageHeight = Convert.ToInt32(pages[i].Height)
      };

      var webpOptions = new WebPOptions
      {
          Lossless = true,
          VectorRasterizationOptions = rasterizationOptions
      };

      pages[i].Save(fileName + "." + i + ".webp", webpOptions);
  }

{

{{< /highlight >}}

**IMAGINGNET-7818 MemMgr crushes at the moment of its finalization**

{{< highlight csharp >}}

Process image conversion async:
public static async Task Convert(string[] inputPaths, string[] outputPaths, ImageOptionsBase options)
{
    if (inputPaths.Length != outputPaths.Length)
    {
        throw new ArgumentException("Input and output length.");
    }

    var semaphore = new SemaphoreSlim(2); 

    var tasks = inputPaths.Select((input, i) => Task.Run(async () =>
    {
        await semaphore.WaitAsync();
        try
        {
            Convert(input, outputPaths[i], options);
        }
        finally
        {
            semaphore.Release();
        }
    }));

    await Task.WhenAll(tasks);
}

private static void Convert(string inputPath, string outputPath, ImageOptionsBase options)
{
    using var image = Image.Load(inputPath);
    image.Save(outputPath, options);
}

{

{{< /highlight >}}

**IMAGINGNET-7747 JPG file colors are incorrectly read**

{{< highlight csharp >}}

string inputPath = @"input.jpg";
using var image = Image.Load(inputPath);
image.Save(inputPath + ".png");

{

{{< /highlight >}}

**IMAGINGNET-4696 CDR to PDF - Image Loading Failed**

{{< highlight csharp >}}

var baseFolder = "D:\\";
   var fileName = "2020 BCF Golf Program.cdr";
   var inputFilePath = Path.Combine(baseFolder, fileName);
   var outputFilePath = inputFilePath + ".pdf";
   using (var image = Image.Load(inputFilePath))
   {
       image.Save(outputFilePath);
   }

{

{{< /highlight >}}

