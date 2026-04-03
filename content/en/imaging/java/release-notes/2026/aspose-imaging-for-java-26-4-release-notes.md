---
id: aspose-imaging-for-java-26-4-release-notes
slug: aspose-imaging-for-java-26-4-release-notes
linktitle: Aspose.Imaging for JAVA 26.4 - Release notes
title: Aspose.Imaging for JAVA 26.4 - Release notes
weight: 46
description: Aspose.Imaging for JAVA 26.4 - Release notes the latest updates and fixes.
type: repository
layout: release
hideChildren: false
toc: false
family_listing_page_title: Aspose.Imaging for JAVA 26.4 - Release notes
menuItemWithNoContent: false
---

## Competitive features:

- **Implement partial GDIRendering**

| **Key**         | **Summary**                                                                                                                                                              | **Category** |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| IMAGINGJAVA-9181 | Implement partial GDIRendering                                                                                                                                  | Feature      |
| IMAGINGJAVA-9189 | Fix bug on export to Pdf for images without own stream                                                                                                                                  | Enhancement      |
| IMAGINGJAVA-9188 | MemMgr crushes at the moment of its finalization                                                                                                                                  | Enhancement      |
| IMAGINGJAVA-9182 | CDR to WEBP IndexOutOfRangeException                                                                                                                                  | Enhancement      |
| IMAGINGJAVA-9154 | JPG file colors are incorrectly read                                                                                                                                  | Enhancement      |
| IMAGINGJAVA-8551 | CDR to PDF - Image Loading Failed                                                                                                                                  | Enhancement      |

## Public API changes:

### Added APIs:

Please see corresponding cumulative [API changes for Aspose.Imaging for .NET 26.4](https://releases.aspose.com/imaging/net/release-notes/2026/aspose-imaging-for-net-26-4-release-notes/) version

### Removed APIs:

Please see corresponding cumulative [API changes for Aspose.Imaging for .NET 26.4](https://releases.aspose.com/imaging/net/release-notes/2026/aspose-imaging-for-net-26-4-release-notes/) version

## Usage Examples:

**IMAGINGJAVA-9189 Fix bug on export to Pdf for images without own stream**

{{< highlight csharp >}}

PNG to PDF conversion:
try (PngImage image = new PngImage(32, 32, PngColorType.TruecolorWithAlpha))
{
	ByteArrayOutputStream outputStream = new ByteArrayOutputStream();
	image.save(outputStream, new PdfOptions());
}

{

{{< /highlight >}}

**IMAGINGJAVA-9188 MemMgr crushes at the moment of its finalization**

{{< highlight csharp >}}

Process image conversion async:
public static void convertAll(final String[] inputPaths,final String[] outputPaths,final  ImageOptionsBase options)
{
	if (inputPaths.length != outputPaths.length)
	{
		throw new ArgumentException("Input and output length.");
	}

	Semaphore semaphore = new Semaphore(2);

	ExecutorService service = Executors.newFixedThreadPool(inputPaths.length);

	List<Future<?>> list = new ArrayList<>(inputPaths.length);

	for (int i = 0; i < inputPaths.length; i++)
	{
		final int index = i;
		list.add(service.submit(() -> {
			boolean needRelease = false;
			try
			{
				semaphore.acquire();
				needRelease = true;
				convert(inputPaths[index], outputPaths[index], options.deepClone());
			}
			catch (InterruptedException e)
			{
				throw new RuntimeException(e);
			}
			finally
			{
				if (needRelease)
				{
					semaphore.release();
				}
			}
		}));
	}

	list.forEach(it -> {
		try
		{
			it.get();
		}
		catch (InterruptedException | ExecutionException e)
		{
			throw new RuntimeException(e);
		}
	});
}

private static void convert(String inputPath, String outputPath, ImageOptionsBase options)
{
	try (Image image = Image.load(inputPath))
	{
		image.save(outputPath, options);
	}
}

{

{{< /highlight >}}

**IMAGINGJAVA-9182 CDR to WEBP IndexOutOfRangeException**

{{< highlight csharp >}}

String fileName = "sample.cdr";
try (Image image = Image.load(fileName))
{
	Image[] pages = ((IMultipageImage)image).getPages();
	for (int i = 0; i < pages.length; i++)
	{
		VectorRasterizationOptions rasterizationOptions = new CdrRasterizationOptions();
		rasterizationOptions.setPageWidth(pages[i].getWidth());
		rasterizationOptions.setPageHeight(pages[i].getHeight());
		WebPOptions webpOptions = new WebPOptions();
		webpOptions.setLossless(true);
		webpOptions.setVectorRasterizationOptions(rasterizationOptions);

		pages[i].save(fileName + "." + i + ".webp", webpOptions);
	}
}

{

{{< /highlight >}}

**IMAGINGJAVA-9181 Implement partial GDIRendering**

{{< highlight csharp >}}

try (Image image = Image.load("test.cdr"))
{
	image.save("test.png", new PngOptions(){{
		setVectorRasterizationOptions(new CdrRasterizationOptions() {{
			setPositioning(PositioningTypes.Relative); 
		}}
	}});
}

{

{{< /highlight >}}

**IMAGINGJAVA-9154 JPG file colors are incorrectly read**

{{< highlight csharp >}}

String inputPath = "input.jpg";
try (Image image = Image.load(inputPath))
{
	image.save(inputPath + ".png");
}

{

{{< /highlight >}}

**IMAGINGJAVA-8551 CDR to PDF - Image Loading Failed**

{{< highlight csharp >}}

String baseFolder = "D:\\";
String fileName = "2020 BCF Golf Program.cdr";
String inputFilePath = baseFolder + fileName;
String outputFilePath = inputFilePath + ".pdf";
try (Image image = Image.load(inputFilePath))
{
   image.save(outputFilePath);
}

{

{{< /highlight >}}

