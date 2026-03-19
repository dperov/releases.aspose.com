---
id: "aspose-slides-for-android-via-java-26-3-release-notes"
slug: "aspose-slides-for-android-via-java-26-3-release-notes"
linktitle: "Aspose.Slides for Android via Java 26.3 Release Notes"
title: "Aspose.Slides for Android via Java 26.3 Release Notes"
weight: 100
description: "Aspose.Slides for Android via Java 26.3 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Slides for Android via Java 26.3 Release Notes"
---

{{% alert color="primary" %}} 

This page contains release notes for [Aspose.Slides for Android via Java 26.3](https://releases.aspose.com/java/repo/com/aspose/aspose-slides/26.3/)

{{% /alert %}} 

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|SLIDESANDROID-518|[Use Aspose.Slides for Java 26.3 features](/slides/java/release-notes/2026/aspose-slides-for-java-26-3-release-notes/)|Enhancement|


## Public API Changes ##

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

    RectF visualBounds = shape.getVisualBounds();

    System.out.println(
            "Visual bounds: X=" + visualBounds.left + ", Y=" + visualBounds.top +", " +
                    "Width=" + visualBounds.right +", Height=" + visualBounds.bottom);
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

### Extended Enum: SourceFormat

The `SourceFormat` enumeration has been extended with the following values: 

```java
/**
 * <p>
 * Microsoft PowerPoint 97-2003 Presentation (*.ppt).
 * </p>
 */
public static final int Ppt = 0;

/**
 * <p>
 * Microsoft Office Open XML Presentation (*.pptx).
 * </p>
 */
public static final int Pptx = 1;

/**
 * <p>
 * OpenDocument Presentation (*.odp).
 * </p>
 */
public static final int Odp = 2;

/**
 * <p>
 * Microsoft Office Open XML Macro-enabled Presentation (*.pptm).
 * </p>
 */
public static final int Pptm = 3;

/**
 * <p>
 * Microsoft Office Open XML SlideShow (*.ppsx).
 * </p>
 */
public static final int Ppsx = 4;

/**
 * <p>
 * Microsoft Office Open XML Macro-enabled SlideShow (*.ppsm).
 * </p>
 */
public static final int Ppsm = 5;

/**
 * <p>
 * Microsoft Office Open XML Template (*.potx).
 * </p>
 */
public static final int Potx = 6;

/**
 * <p>
 * Microsoft Office Open XML Macro-enabled Template (*.potm).
 * </p>
 */
public static final int Potm = 7;

/**
 * <p>
 * Microsoft PowerPoint 97-2003 SlideShow (*.pps).
 * </p>
 */
public static final int Pps = 8;

/**
 * <p>
 * Microsoft PowerPoint 97-2003 Template (*.pot).
 * </p>
 */
public static final int Pot = 9;

/**
 * <p>
 * OpenDocument Presentation Template (*.otp).
 * </p>
 */
public static final int Otp = 10;

/**
 * <p>
 * Flat XML ODF Presentation (*.fodp).
 * </p>
 */
public static final int Fodp = 11;

/**
 * <p>
 * PowerPoint XML Presentation (*.xml).
 * </p>
 */
public static final int Xml = 12;
```

> **Note:** The `.ppt`, `.pps`, and `.pot` file types use the same binary PowerPoint file format. They differ only in file extension, which indicates the intended document usage (presentation, slideshow, or template). The internal file structure is identical for all three formats.

### Added New Method: SlideUtil.ToSaveFormat

The new `ToSaveFormat` method has been added to the `SlideUtil` class. It converts a source file format to the corresponding `SaveFormat` value.

```java
/**
 * <p>
 * Converts a source file format to the corresponding {@link SaveFormat}.
 * </p>
 * @return The corresponding {@link SaveFormat} value.
 * @exception ArgumentException 
 * @param format The source file format.
 */
public static int toSaveFormat(int format)
```

**Usage Example**

The following code shows how to modify a presentation and save it to a stream in its original format:

```java
Presentation sourcePresentation = new Presentation("SomePresentation.pptm");
try {
    // Modify the presentation as you need
    sourcePresentation.getSlides().addClone(sourcePresentation.getSlides().get_Item(0));

    // Save the presentation to the stream in its original format
    ByteArrayOutputStream stream = new ByteArrayOutputStream();
    sourcePresentation.save(stream, SlideUtil.toSaveFormat(sourcePresentation.getSourceFormat()));
} finally {
    if (sourcePresentation != null) sourcePresentation.dispose();
}
```

### Added New Properties: ShapeElement.PathPoints and ShapeElement.PathTypes

The new `PathPoints` and `PathTypes` properties have been added to the `ShapeElement` class. These properties return the graphics path information from the ShapeElement.

```java
/**
 * <p>
 * Gets an array of points that define the geometry of the element's path.
 * </p>
 */
public final PointF[] getPathPoints() 

/**
 * <p>
 * Gets an array of byte values that specify the type of each point in the element's path. 
 * <p><b>0</b> Indicates that the point is the start of a figure.</p>
 * <p><b>1</b> Indicates that the point is one of the two endpoints of a line.</p>
 * <p><b>3</b> Indicates that the point is an endpoint or control point of a cubic Bezier spline.</p>
 * <p><b>7</b> Masks all bits except for the three low-order bits, which indicate the point type.</p>
 * <p><b>16</b> Specifies that the corresponding segment is dashed.</p>
 * <p><b>32</b> Specifies that the point is a marker.</p>
 * <p><b>128</b> Specifies that the point is the last point in a closed subpath (figure).</p>
 * <p><b>129</b> Indicates a data point that is both a line segment endpoint and the last point of a closed subpath.</p>
 * </p>
 */
public final byte[] getPathTypes() 
```

**Usage examples**

The following code snippet shows how to print the graphics path information from the first slide `AutoShape`:

```java
Presentation pres = new Presentation("shape.pptx");
try {
    AutoShape autoShape = (AutoShape)pres.getSlides().get_Item(0).getShapes().get_Item(0);

    IShapeElement[] elements = autoShape.createShapeElements();
    for (int e = 0 ; e < elements.length; e++)
    {
        System.out.println("Start element");
        ShapeElement element = (ShapeElement)elements[e];

        byte[] types = element.getPathTypes();
        PointF[] points = element.getPathPoints();
        for (int i = 0; i < types.length; i++)
        {
            switch (types[i] & 0xFF)
            {
                case 0:
                    System.out.println("Start point " + points[i]);
                    break;
                case 1:
                    System.out.println("LineTo point " + points[i]);
                    break;
                case 3:
                    System.out.println("Bezier spline point " + points[i]);
                    break;
                case 128:
                    System.out.println("Close subpath point " + points[i]);
                    break;
                case 129:
                    System.out.println("End point " + points[i]);
                    break;
            }
        }
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Support for the Sensitivity labels

#### Added New Enumeration: SensitivityLabelAssignmentType

The new `SensitivityLabelAssignmentType` enumeration has been added. This enumeration represents the assignment method for the sensitivity label.

```java
/**
 * <p>
 * Represents the assignment method for the sensitivity label.
 * </p>
 */
public final class SensitivityLabelAssignmentType
{
    /**
     * <p>
     * Use for any sensitivity label that was not directly applied by the user. 
     * This includes any default labels, automatically applied labels.
     * </p>
     */
    public static final int Standard = 0;
    /**
     * <p>
     * Use for any sensitivity label that was directly applied by the user. 
     * This includes any manually applied sensitivity labels as well as recommended
     * or mandatory labeling or any feature where the user decides which sensitivity label to apply.
     * </p>
     */
    public static final int Privileged = 1;

}
```

#### Added New Enumeration: SensitivityLabelContentType

The new `SensitivityLabelContentType` enumeration has been added. This enumeration represents the types of content marking that ought to be applied to a presentation document.

```java
/**
 * <p>
 * Represents the types of content marking that ought to be applied to a document.
 * </p>
 */
public final class SensitivityLabelContentType
{
    /**
     * <p>
     * Implies that the label is applied by default or automatically.
     * </p>
     */
    public static final int None = 0;
    /**
     * <p>
     * Implies that the label was manually applied.
     * Use for any sensitivity label that was directly applied by the user.
     * </p>
     */
    public static final int Header = 1;
    /**
     * <p>
     * Implies that the label was manually applied.
     * Use for any sensitivity label that was directly applied by the user.
     * </p>
     */
    public static final int Footer = 2;
    /**
     * <p>
     * Implies that the label was manually applied.
     * Use for any sensitivity label that was directly applied by the user.
     * </p>
     */
    public static final int Watermark = 4;
    /**
     * <p>
     * Implies that the label was manually applied.
     * Use for any sensitivity label that was directly applied by the user.
     * </p>
     */
    public static final int Encryption = 8;
}
```

#### Added New Class: SensitivityLabel

The new `SensitivityLabel` class and `ISensitivityLabel` interface have been added. It represents the sensitivity label from Microsoft Purview Information Protection.

```java
/**
 * <p>
 * Represents the sensitivity label from Microsoft Purview Information Protection.
 * </p>
 */
public interface ISensitivityLabel
{
    /**
     * <p>
     * Returns or sets the id of sensitivity label.
     * Read/write {@link String}.
     * </p>
     */
    public String getId();
    
    /**
     * <p>
     * Returns or sets the id of sensitivity label.
     * Read/write {@link String}.
     * </p>
     */
    public void setId(String value);

    /**
     * <p>
     * Returns or sets the Azure Active Directory (Azure AD) site identifier 
     * corresponding to the sensitivity label policy which describes the sensitivity label.
     * Read/write {@link java.util.UUID}.
     * </p>
     */
    public java.util.UUID getSiteId();

    /**
     * <p>
     * Returns or sets the Azure Active Directory (Azure AD) site identifier 
     * corresponding to the sensitivity label policy which describes the sensitivity label.
     * Read/write {@link java.util.UUID}.
     * </p>
     */
    public void setSiteId(java.util.UUID value);

    /**
     * <p>
     * Indicates whether the sensitivity label is enabled.
     * </p>
     */
    public boolean isEnabled();
    
    /**
     * <p>
     * Indicates whether the sensitivity label is enabled.
     * </p>
     */
    public void setEnabled(boolean value);

    /**
     * <p>
     * Indicates whether the sensitivity label was removed.
     * </p>
     */
    public boolean isRemoved();
    
    /**
     * <p>
     * Indicates whether the sensitivity label was removed.
     * </p>
     */
    public void setRemoved(boolean value);

    /**
     * <p>
     * Returns or sets the assignment method for the sensitivity label.
     * Read/write {@link SensitivityLabelAssignmentType}.
     * </p>
     */
    public int getAssignmentMethodType();
    
    /**
     * <p>
     * Returns or sets the assignment method for the sensitivity label.
     * Read/write {@link SensitivityLabelAssignmentType}.
     * </p>
     */
    public void setAssignmentMethodType(int value);

    /**
     * <p>
     * Returns the list of types of content marking that ought to be applied to a file.
     * </p>
     * @return A list of content types {@link SensitivityLabelContentType}
     */
    public IGenericList<Integer> getContentMarkTypes();
}
```

#### Added New Class: SensitivityLabelCollection

The new `SensitivityLabelCollection` class and `ISensitivityLabelCollection` interface have been added for storing the collection of sensitivity labels applied to the document.

```java
/**
 * <p>
 * Represents a collection of sensitivity labels applied to the document.
 * </p>
 */
public interface ISensitivityLabelCollection
{
    /**
     * <p>
     * Returns the sensitivity label by index.
     * Read-only {@link ISensitivityLabel}.
     * </p>
     */
    public ISensitivityLabel get_Item(int index);

    /**
     * <p>
     * Adds the sensitivity label at the end of the collection.
     * </p>
     * @param id The id of sensitivity label.
     * @param siteId The Azure Active Directory (Azure AD) site identifier.
     * @param isEnabled Flag indicates whether the sensitivity label is enabled.
     * @param methodType The assignment method for the sensitivity label.
     */
    public ISensitivityLabel add(String id, java.util.UUID siteId, boolean isEnabled, int methodType);

    /**
     * <p>
     * Adds a SensitivityLabel to the collection.
     * </p>
     * @return The index at which the SensitivityLabel was added.
     * @exception ArgumentException 
     * Thrown when the sensitivity label with the same Id has already been added.
     * @param label The SensitivityLabel object to be added at the end of the collection.
     */
    public int add(ISensitivityLabel label);

    /**
     * <p>
     * Removes the sensitivity label at the specified index.
     * </p>
     * @param index Index of the sensitivity label that should be deleted.
     */
    public void removeAt(int index);

    /**
     * <p>
     * Removes all elements from the collection.
     * </p>
     */
    public void clear();

    /**
     * <p>
     * Gets the number of all elements in the collection.
     * Read-only {@code int}.
     * </p>
     */
    public int getCount();
}
```

#### Added New Property: Presentation.SensitivityLabels

The new `SensitivityLabels` property has been added to the `IPresentation` interface and `Presentation` class. It returns the collection of sensitivity labels applied to the presentation document.

```java
/**
 * <p>
 * Returns the collection of sensitivity labels applied to the presentation document.
 * Read-only {@link ISensitivityLabelCollection}.
 * </p>
 */
public final ISensitivityLabelCollection getSensitivityLabels()
```

**Usage example**

The following code shows how to print the sensitivity labels applied to the presentation document:
```java
Presentation pres = new Presentation("SomePresentation.pptx");
try {
    ISensitivityLabelCollection sensitivityLabels = pres.getSensitivityLabels();

    for (int i = 0; i < sensitivityLabels.getCount(); i++)
        System.out.println("Label Id " + sensitivityLabels.get_Item(i).getId() + " from Azure AD site " + sensitivityLabels.get_Item(i).getSiteId());
} finally {
    if (pres != null) pres.dispose();
}
```

This code demonstrates how to add the new sensitivity label to the presentation document:
```java
Presentation pres = new Presentation("SomePresentation.pptx");
try {
    ISensitivityLabelCollection sensitivityLabels = pres.getSensitivityLabels();

    // Add the new label
    String labelIdString = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"; // Get the sensitivity label Id from the policy
    UUID siteIdGuid = UUID.fromString("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"); // Get the Azure AD site identifier from the policy
    ISensitivityLabel label = sensitivityLabels.add(labelIdString, siteIdGuid, true, SensitivityLabelAssignmentType.Privileged);
    label.getContentMarkTypes().addItem(SensitivityLabelContentType.Footer);

    pres.save("SensitivityLabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

#### Added New Method: DocumentProperties.getSensitivityLabels()

The new `GetSensitivityLabels` method has been added to the `IDocumentProperties` interface and `DocumentProperties` class. This method gets an array of sensitivity labels from the custom document properties (Microsoft Information Protection SDK Metadata).

```java
/**
 * <p>
 * Gets an array of sensitivity labels from the custom document properties (Microsoft Information Protection SDK Metadata).
 * </p>
 */
public final ISensitivityLabel[] getSensitivityLabels()
```

**Usage example**

The following code shows how to move the sensitivity labels information from the custom document properties to the modern SensitivityLabels collection:

```java
Presentation pres = new Presentation("SomePresentation.pptx");
try {
    // Get sensitivity labels from the custom document properties
    ISensitivityLabel[] mipSensitivityLabels = pres.getDocumentProperties().getSensitivityLabels();

    ISensitivityLabelCollection sensitivityLabels = pres.getSensitivityLabels();
    for (int i = 0; i < mipSensitivityLabels.length; i++)
    {
        // Add label to the collection
        // Here you can add a check for the validity of the label information (the label is available, etc)
        sensitivityLabels.add(mipSensitivityLabels[i]);
    }

    pres.save("SensitivityLabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

