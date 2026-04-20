---
id: "aspose-psd-for-net-26-4-release-notes"
slug: "aspose-psd-for-net-26-4-release-notes"
linktitle: "Aspose.PSD for .NET 26.4 - Release Notes"
title: "Aspose.PSD for .NET 26.4 - Release Notes"
weight: -4
description: "Aspose.PSD for .NET 26.4 - Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.PSD for .NET 26.4 - Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes for [Aspose.PSD for .NET 26.4](https://www.nuget.org/packages/Aspose.PSD/)

{{% /alert %}}

| **Key**     | **Summary**                                                                               | **Category** |
|:------------|:------------------------------------------------------------------------------------------|:-------------|
| PSDNET-2701 | Implement rendering of Gradient with Smooth method.                                       | Feature      |
| PSDNET-2606 | Update Aspose.Drawing to 26.2 version.                                                    | Enhancement  |
| PSDNET-548  | Add support for a resource containing effects in a group layer.                           | Bug          |
| PSDNET-2710 | PSD files with adjusted Hue/Saturation will throw the exception PsdImageArgumentException - Invalid Hue2 Resource data. | Bug |


## **Public API Changes**
# **Added APIs:**
- T:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.InterpolationMethod
- F:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.InterpolationMethod.Classic
- F:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.InterpolationMethod.Perceptual
- F:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.InterpolationMethod.Linear
- F:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.InterpolationMethod.Smooth
- F:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.InterpolationMethod.Stripes
- P:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.IGradientFillSettings.InterpolationMethod
- P:Aspose.PSD.FileFormats.Psd.Layers.LayerResources.GdFlResource.InterpolationMethod
- P:Aspose.PSD.FileFormats.Psd.Layers.LayerResources.GrdmResource.InterpolationMethod
- P:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.GradientFillSettings.InterpolationMethod
- P:Aspose.PSD.FileFormats.Psd.Layers.FillSettings.GradientMapSettings.InterpolationMethod
- T:Aspose.PSD.FileFormats.Psd.Layers.LayerResources.IfxsResource
- M:Aspose.PSD.FileFormats.Psd.Layers.LayerResources.IfxsResource.#ctor
- F:Aspose.PSD.FileFormats.Psd.Layers.LayerResources.IfxsResource.TypeToolKey

# **Removed APIs:**
- None


## **Usage examples:**

**PSDNET-548. Add support for a resource containing effects in a group layer.**

{{< highlight csharp >}}
string sourceFile = Path.Combine(baseFolder, "example.psd");
string outputFile = Path.Combine(outputFolder, "export.psd");

var loadOptions = new PsdLoadOptions()
{
	LoadEffectsResource = true,
};

using (var psdImage = (PsdImage)Image.Load(sourceFile, loadOptions))
{
	// Example has 2 group layers with effects
	// Group layer with one effect
	LayerGroup layerGroupOne = (LayerGroup)psdImage.Layers[2];

	// Group layer with many effects
	LayerGroup layerGroupMany = (LayerGroup)psdImage.Layers[5];

	// Get the number of effects and verify their quantity
	int effectCountOne = layerGroupOne.BlendingOptions.Effects.Length;
	int effectCountMany = layerGroupMany.BlendingOptions.Effects.Length;

	// One effect in the group layer is in resource 'IfxsResource'
	IfxsResource ifxsResource = (IfxsResource)layerGroupOne.Resources[0];

	// Two or more effects in a group layer are in resource 'ImfxResource'
	ImfxResource imfxResource = (ImfxResource)layerGroupMany.Resources[0];

	// Add a third shadow to a group layer with multiple effects
	layerGroupMany.BlendingOptions.AddDropShadow();

	psdImage.Save(outputFile);
}
{{< /highlight >}}

**PSDNET-2701. Implement rendering of Gradient with Smooth method.**

{{< highlight csharp >}}
string sourceFile = Path.Combine(baseFolder, "GradientOverlay.psd");
string outputFile = Path.Combine(outputFolder, "output_GradientOverlay.psd");
string outputFilePng = Path.Combine(outputFolder, "output_GradientOverlay.png");

var srcMethod = InterpolationMethod.Linear;
var newMethod = InterpolationMethod.Smooth;

var opt = new PsdLoadOptions()
{
    LoadEffectsResource = true,
};

using (var image = (PsdImage)Image.Load(sourceFile, opt))
{
    // Read
    var effect = image.Layers[1].BlendingOptions.Effects[0] as GradientOverlayEffect;
    var gradientSettings = effect.Settings;
    AssertAreEqual(srcMethod, gradientSettings.InterpolationMethod);

    // Change
    gradientSettings.InterpolationMethod = newMethod;

    image.Save(outputFile);
    image.Save(outputFilePng, new PngOptions() { ColorType = PngColorType.TruecolorWithAlpha });
}

// Check saved data
using (var image = (PsdImage)Image.Load(outputFile, opt))
{
    var effect = image.Layers[1].BlendingOptions.Effects[0] as GradientOverlayEffect;
    var gradientSettings = effect.Settings;

    AssertAreEqual(newMethod, gradientSettings.InterpolationMethod);
}

void AssertAreEqual(object expected, object actual, string message = null)
{
    if (!object.Equals(expected, actual))
    {
        throw new Exception(message ?? "Objects are not equal.");
    }
}
{{< /highlight >}}

**PSDNET-2710. PSD files with adjusted Hue/Saturation will throw the exception PsdImageArgumentException - Invalid Hue2 Resource data.**

{{< highlight csharp >}}
var hue2 = new Hue2Resource(new byte[136]);
{{< /highlight >}}
