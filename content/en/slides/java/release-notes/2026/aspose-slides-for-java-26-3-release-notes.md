---
id: "aspose-slides-for-java-26-3-release-notes"
slug: "aspose-slides-for-java-26-3-release-notes"
linktitle: "Aspose.Slides for Java 26.3 Release Notes"
title: "Aspose.Slides for Java 26.3 Release Notes"
weight: 100
description: "Aspose.Slides for Java 26.3 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Slides for Java 26.3 Release Notes"
---

{{% alert color="primary" %}} 

This page contains release notes for [Aspose.Slides for Java 26.3](https://releases.aspose.com/java/repo/com/aspose/aspose-slides/26.3/)

{{% /alert %}} 

|**Key**|**Summary**|**Category**|**Related Documentation**|
| :- | :- | :- | :- |
|SLIDESNET-45284|Support opening text disguised as .ppt/.pps as text-imported presentations|Feature||
|SLIDESNET-45135|Getting the size and rotation of SmartArt shape|Enhancement||
|SLIDESNET-45298|Failed to find a way to determine an inherited scheme color|Enhancement|https://docs.aspose.com/slides/net/presentation-theme/|
|SLIDESJAVA-39587|[Use Aspose.Slides for Net 26.3 features](/slides/net/release-notes/2026/aspose-slides-for-net-26-3-release-notes/)|Enhancement||
|SLIDESJAVA-39774|Fonts are changed while converting PPTX to PDF|Bug|https://docs.aspose.com/slides/java/convert-powerpoint-to-pdf/|
|SLIDESJAVA-39784|Text glow effect appears when converting PPTX to PDF|Bug|https://docs.aspose.com/slides/java/convert-powerpoint-to-pdf/|
|SLIDESJAVA-39791|Color of chart data labels is changed after loading and saving a PPTX file|Bug|https://docs.aspose.com/slides/java/save-presentation/|
|SLIDESJAVA-39781|Parts of math equations are replaced with empty spaces when converting PPTX to PDF|Bug|https://docs.aspose.com/slides/java/convert-powerpoint-to-pdf/|
|SLIDESJAVA-39722|Getting the width and height of the shape content|Feature||
|SLIDESJAVA-39754|X-axis values of a chart change when converting PPTX to PDF|Bug|https://docs.aspose.com/slides/java/convert-powerpoint-to-pdf/|

## Public API Changes

### Added New Method: Shape.getVisualBounds()

A new `getVisualBounds()` method has been added to the `Shape` class. This method returns the actual visual bounds of a shape as it appears on the slide after rendering.  
Unlike the model bounds (`Shape.getX()`, `Shape.getY()`, `Shape.getWidth()`, `Shape.getHeight()`), the visual bounds represent the final rendered appearance and may extend beyond the shape’s original geometry.  
The returned bounds take into account rendering-time factors such as rotation, stroke width, text overflow, SmartArt layout, and grouping.

**Usage Example**

The following code snippet demonstrates how to retrieve and print the visual bounds of a shape on the first slide:

```java
Presentation presentation = new Presentation("example.pptx");
try
{
    Shape shape = (Shape)presentation.getSlides().get_Item(0).getShapes().get_Item(0);

    Rectangle2D.Float visualBounds = shape.getVisualBounds();

    System.out.println(
            "Visual bounds: X=" + visualBounds.getX() + ", Y=" + visualBounds.getY() +", " +
                    "Width=" + visualBounds.getWidth() +", Height=" + visualBounds.getHeight());
}
finally 
{
    if (presentation != null) presentation.dispose();    
}
```

### Added New Property: IFillFormatEffectiveData.SolidFillSchemeColor

A new `SolidFillSchemeColor` property has been added to the `IFillFormatEffectiveData` interface. This property allows retrieving the fill color defined by the presentation’s color scheme.

**Usage Example**

The following code snippet demonstrates how to print the effective fill colors of the shapes on the first slide:

```java
Presentation presentation = new Presentation("FillColor.pptx");
try
{
    for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
    {
        IFillFormatEffectiveData fillFormat = shape.getFillFormat().getEffective();
        System.out.println("Fill color: " + fillFormat.getSolidFillColor());
        System.out.println("Fill scheme color: " + fillFormat.getSolidFillSchemeColor());
    }
}
finally
{
    if (presentation != null) presentation.dispose();
}
```
