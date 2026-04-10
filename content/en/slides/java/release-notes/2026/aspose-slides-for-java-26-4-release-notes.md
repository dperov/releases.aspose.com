---
id: "aspose-slides-for-java-26-4-release-notes"
slug: "aspose-slides-for-java-26-4-release-notes"
linktitle: "Aspose.Slides for Java 26.4 Release Notes"
title: "Aspose.Slides for Java 26.4 Release Notes"
weight: 90
description: "Aspose.Slides for Java 26.4 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Slides for Java 26.4 Release Notes"
---

{{% alert color="primary" %}} 

This page contains release notes for [Aspose.Slides for Java 26.4](https://releases.aspose.com/java/repo/com/aspose/aspose-slides/26.4/)

{{% /alert %}} 

|**Key**|**Summary**|**Category**|**Related Documentation**|
| :- | :- | :- | :- |
|SLIDESJAVA-39587|[Use Aspose.Slides for Net 26.4 features](/slides/net/release-notes/2026/aspose-slides-for-net-26-4-release-notes/)|Enhancement||
|SLIDESJAVA-39274|Text layouting is changed when loading and saving a PPT file|Bug|https://docs.aspose.com/slides/java/save-presentation/|
|SLIDESJAVA-39275|Font size is increased when loading and saving a PPT file|Bug|https://docs.aspose.com/slides/java/save-presentation/|
|SLIDESJAVA-39788|ISlide.getImage(RenderingOptions, Dimension) returns lower quality image than ISlide.getImage(Dimension)|Bug|https://docs.aspose.com/slides/java/convert-powerpoint-to-png/|
|SLIDESJAVA-39792|Missing chart data labels after loading and saving a PPTX file (CELLREF)|Bug|https://docs.aspose.com/slides/java/save-presentation/|
|SLIDESJAVA-39794|Axis labels and legend on a Stacked Area chart are not displayed when converting PPTX to PDF|Bug|https://docs.aspose.com/slides/java/convert-powerpoint-to-pdf/|
|SLIDESJAVA-39795|Data labels on a Doughnut chart are displayed incorrectly when converting PPTX to PDF|Bug|https://docs.aspose.com/slides/java/convert-powerpoint-to-pdf/|
|SLIDESJAVA-39797|NullPointerException when resizing Notes slide with shapes that don’t have placeholders|Bug|https://docs.aspose.com/slides/java/presentation-notes/|
|SLIDESJAVA-39810|NullPointerException is thrown when loading presentation files|Bug|https://docs.aspose.com/slides/java/open-presentation/|

## ⚠ IMPORTANT DEPRECATION NOTICE

Starting with version 26.10, support for JDK 1.6 and JDK 1.7 will be completely discontinued.

**What is changing:**

- The minimum supported Java version will be JDK 1.8 (Java 8) or higher.
- JDK 1.6 and JDK 1.7 will no longer be compatible with the product.

**Recommended actions:**

Please plan to migrate your environments and deployment scripts to JDK 1.8 or higher to avoid failures when upgrading to version 26.10.

*The current version (up to 26.9 inclusive) continues to work with JDK 1.6 and 1.7, but we strongly recommend starting the migration process now.*

## Public API Changes

### Added New Enumeration: Charts.WorkbookType

The new `WorkbookType` enumeration has been added. This enumeration specifies the type of Open XML workbook file.

```java
/**
 * <p>
 * Specifies the type of Open XML workbook file.
 * </p>
 */
public final class WorkbookType
{
    /**
     * <p>
     * The workbook type is not defined.
     * </p>
     */
    public static final int NotDefined = -1;

    /**
     * <p>
     * Excel workbook (*.xlsx).
     * </p>
     */
    public static final int Workbook = 0;

    /**
     * <p>
     * Excel macro-enabled workbook (*.xlsm).
     * </p>
     */
    public static final int WorkbookMacro = 1;

    /**
     * <p>
     * Excel template (*.xltx).
     * </p>
     */
    public static final int Template = 2;

    /**
     * <p>
     * Excel macro-enabled template (*.xltm).
     * </p>
     */
    public static final int TemplateMacro = 3;

    /**
     * <p>
     * Excel binary macro-enabled workbook (*.xlsb).
     * </p>
     */
    public static final int WorkbookBinaryMacro = 4;
}
```

### Added New Property: ChartData.EmbeddedWorkbookType

The new `EmbeddedWorkbookType` property has been added to the `IChartData` interface and `ChartData` class. It allows you to get the type of the chart embedded workbook.

```java
/**
 * <p>
 * Gets the type of the embedded workbook.
 * Returns {@link WorkbookType#NotDefined} if {@link #getDataSourceType} is 
 * {@link ChartDataSourceType#ExternalWorkbook}.
 * Read-only {@link WorkbookType}.
 * </p>
 */
public int getEmbeddedWorkbookType();
```

**Usage Example**

Aspose.Slides does not support the Excel binary macro-enabled workbook (*.xlsb) format.
The following code example shows how to check whether a chart workbook format is supported before working with chart data:

```java
Presentation presentation = new Presentation("charts.pptx");
try {
    for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
    {
        if (!(shape instanceof IChart))
            continue;

        IChart chart = (IChart)shape;
        IChartData chartData = chart.getChartData();

        // Skip charts whose embedded workbook format is not supported.
        if (chartData.getDataSourceType() == ChartDataSourceType.InternalWorkbook &&
                chartData.getEmbeddedWorkbookType() == WorkbookType.WorkbookBinaryMacro)
        {
            continue;
        }

        // Read or modify chart workbook data.
        System.out.println(chartData.getSeries().get_Item(0).getName().getAsCells().hashCode());

        IChartDataCell cell = chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell();
        System.out.println(cell.getValue());
    }

    presentation.save("charts-out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

