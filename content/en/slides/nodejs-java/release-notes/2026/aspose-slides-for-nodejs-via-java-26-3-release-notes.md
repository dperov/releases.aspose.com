---
id: "aspose-slides-for-nodejs-via-java-26-3-release-notes"
slug: "aspose-slides-for-nodejs-via-java-26-3-release-notes"
linktitle: "Aspose.Slides for Node.js via Java 26.3 Release Notes"
title: "Aspose.Slides for Node.js via Java 26.3 Release Notes"
weight: 100
description: "Aspose.Slides for Node.js via Java 26.3 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Slides for Node.js via Java 26.3 Release Notes"
---

{{% alert color="primary" %}} 

This page contains release notes for [Aspose.Slides for Node.js via Java](https://www.npmjs.com/package/aspose.slides.via.java)

{{% /alert %}} 

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|SLIDESNODEJS-118|[Use Aspose.Slides for Java 26.3 features](/slides/java/release-notes/2026/aspose-slides-for-java-26-3-release-notes/)|Enhancement|


## Public API Changes

### Added New Method: Shape.getVisualBounds()

A new `getVisualBounds()` method has been added to the `Shape` class. This method returns the actual visual bounds of a shape as it appears on the slide after rendering.  
Unlike the model bounds (`Shape.getX()`, `Shape.getY()`, `Shape.getWidth()`, `Shape.getHeight()`), the visual bounds represent the final rendered appearance and may extend beyond the shape’s original geometry.  
The returned bounds take into account rendering-time factors such as rotation, stroke width, text overflow, SmartArt layout, and grouping.

**Usage Example**

The following code snippet demonstrates how to retrieve and print the visual bounds of a shape on the first slide:

```java
let presentation = null;
try {
    presentation = new aspose.slides.Presentation("Shape.pptx");
    
    const shape = presentation.getSlides().get_Item(0).getShapes().get_Item(0);
    
    const visualBounds = shape.getVisualBounds();
    
    console.log(
        "Visual bounds: X=" + visualBounds.getX() + 
        ", Y=" + visualBounds.getY() + 
        ", Width=" + visualBounds.getWidth() + 
        ", Height=" + visualBounds.getHeight()
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Added New Property: IFillFormatEffectiveData.SolidFillSchemeColor

A new `SolidFillSchemeColor` property has been added to the `IFillFormatEffectiveData` interface. This property allows retrieving the fill color defined by the presentation’s color scheme.

**Usage Example**

The following code snippet demonstrates how to print the effective fill colors of the shapes on the first slide:

```java
let presentation = null;
try {
    presentation = new aspose.slides.Presentation("FillColor.pptx");
    
    const shapes = presentation.getSlides().get_Item(0).getShapes();
    const shapesArray = shapes.toArray();
    
    for (let i = 0; i < shapesArray.length; i++) {
        const shape = shapesArray[i];
        const fillFormat = shape.getFillFormat().getEffective();
        
        console.log("Fill color: " + fillFormat.getSolidFillColor());
        console.log("Fill scheme color: " + fillFormat.getSolidFillSchemeColor());
    }
} finally {
    if (presentation != null) presentation.dispose();
}
```
