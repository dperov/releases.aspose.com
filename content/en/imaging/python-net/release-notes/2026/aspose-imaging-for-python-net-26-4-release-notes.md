---
id: aspose-imaging-for-python-net-26-4-release-notes
slug: aspose-imaging-for-python-net-26-4-release-notes
linktitle: Aspose.Imaging for Python via .NET 26.4 - Release notes
title: Aspose.Imaging for Python via .NET 26.4 - Release notes
weight: 46
description: Aspose.Imaging for Python via .NET 26.4 - Release notes the latest updates and fixes.
type: repository
layout: release
hideChildren: false
toc: false
family_listing_page_title: Aspose.Imaging for Python via .NET 26.4 - Release notes
menuItemWithNoContent: false
---

## Competitive features:

- **Implement partial GDIRendering**

| **Key**         | **Summary**                                                                                                                                                              | **Category** |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| IMAGINGPYTHONNET-490 | Fix bug on export to Pdf for images without own stream | Enhancement | 
| IMAGINGPYTHONNET-489 | Implement partial GDIRendering | Feature | 
| IMAGINGPYTHONNET-488 | CDR to WEBP IndexOutOfRangeException | Enhancement | 
| IMAGINGPYTHONNET-487 | MemMgr crushes at the moment of its finalization | Enhancement | 
| IMAGINGPYTHONNET-486 | JPG file colors are incorrectly read | Enhancement | 
| IMAGINGPYTHONNET-485 | CDR to PDF - Image Loading Failed | Enhancement | 

## Public API changes:


## Usage Examples:

**IMAGINGPYTHONNET-490 Fix bug on export to Pdf for images without own stream**

{{< highlight python >}}

PNG to PDF conversion:
import io
from aspose.imaging.fileformats.png import PngImage, PngColorType
from aspose.imaging.imageoptions import PdfOptions

with PngImage(32, 32, PngColorType.TRUECOLOR_WITH_ALPHA) as image:
	with io.BytesIO() as output_stream:
		image.save(outputStream, PdfOptions())

{{< /highlight >}}

**IMAGINGPYTHONNET-489 Implement partial GDIRendering**

{{< highlight python >}}

from aspose.imaging import Image
from aspose.imaging.imageoptions import CdrRasterizationOptions, PngOptions, PositioningTypes

with Image.load("test.cdr") as image:
	cdr_options = CdrRasterizationOptions()
	cdr_options.positioning = PositioningTypes.RELATIVE
	png_options = PngOptions()
	png_options.vector_rasterization_options = cdr_options
	image.save("test.png", png_options)

{{< /highlight >}}

**IMAGINGPYTHONNET-488 CDR to WEBP IndexOutOfRangeException**

{{< highlight python >}}

from aspose.imaging import Image, IMultipageImage
from aspose.imaging.imageoptions import CdrRasterizationOptions, WebPOptions
from aspose.pycore import cast

file_name = "sample.cdr"
with Image.load(file_name) as image:
	pages = cast(IMultipageImage, image).pages
	i:int = 0
	for page in pages:
		rasterization_options = CdrRasterizationOptions()
		rasterization_options.page_width = page.width
		rasterization_options.page_height = page.height
		
		webp_options = WebPOptions()
		webp_options.lossless = True
		webp_options.vector_rasterization_options = rasterization_options

		page.save(fileName + "." + str(i) + ".webp", webp_options)
		i += 1

{{< /highlight >}}

**IMAGINGPYTHONNET-487 MemMgr crushes at the moment of its finalization**

{{< highlight python >}}

from aspose.imaging import Image, ImageOptionsBase
from aspose.imaging.imageoptions import PngOptions
import threading


def convert(input_path, output_path, options, semaphore):
	with semaphore:
		with Image.load(input_path) as image:
			image.save(output_path, options)


def convert_all(input_paths: list, output_paths:list, options:ImageOptionsBase):
    if len(input_paths) != len(output_paths):
        raise AssertError("Input and output length.")

    semaphore = threading.Semaphore(2)
	threads = []
	
	for i in range(len(input_paths)):
		t = threading.Thread(target=convert, args=(input_paths[i], output_paths[i], options.clone(), semaphore,))
        threads.append(t)
        t.start()

    for t in threads:
        t.join()

# Run test

in_path = ["file1.tiff", "file2.bmp", "file3.cdr"]
out_path = ["outfile1.tiff.png", "outfile2.bmp.png", "outfile3.cdr.png"]

convert_all(in_path, out_path, PngOptions())


{{< /highlight >}}

**IMAGINGPYTHONNET-486 JPG file colors are incorrectly read**

{{< highlight python >}}

from aspose.imaging import Image

input_path = "input.jpg"
with Image.load(input_path) as image:
	image.save(input_path + ".png")

{{< /highlight >}}

**IMAGINGPYTHONNET-485 CDR to PDF - Image Loading Failed**

{{< highlight python >}}

from aspose.imaging import Image
from os.path import join as path_combine

baseFolder = "D:\\"
fileName = "2020 BCF Golf Program.cdr"
inputFilePath = path_combine(baseFolder, fileName)
outputFilePath = inputFilePath + ".pdf"
with Image.load(inputFilePath) as image:
   image.save(outputFilePath)

{{< /highlight >}}

