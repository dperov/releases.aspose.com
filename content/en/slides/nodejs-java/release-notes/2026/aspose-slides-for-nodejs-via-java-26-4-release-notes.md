---
id: "aspose-slides-for-nodejs-via-java-26-4-release-notes"
slug: "aspose-slides-for-nodejs-via-java-26-4-release-notes"
linktitle: "Aspose.Slides for Node.js via Java 26.4 Release Notes"
title: "Aspose.Slides for Node.js via Java 26.4 Release Notes"
weight: 90
description: "Aspose.Slides for Node.js via Java 26.4 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Slides for Node.js via Java 26.4 Release Notes"
---

{{% alert color="primary" %}} 

This page contains release notes for [Aspose.Slides for Node.js via Java](https://www.npmjs.com/package/aspose.slides.via.java)

{{% /alert %}} 

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|SLIDESNODEJS-120|[Use Aspose.Slides for Java 26.4 features](/slides/java/release-notes/2026/aspose-slides-for-java-26-4-release-notes/)|Enhancement|


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

```javascript
let presentation = new aspose.slides.Presentation("charts.pptx");
try {
    for (let i = 0; i < presentation.getSlides().get_Item(0).getShapes().size(); i++)
    {
		let shape = presentation.getSlides().get_Item(0).getShapes().get_Item(i);
        if (!java.instanceOf(shape, "com.aspose.slides.IChart"))
            continue;

        let chart = shape;
        let chartData = chart.getChartData();

        // Skip charts whose embedded workbook format is not supported.
        if (chartData.getDataSourceType() == aspose.slides.ChartDataSourceType.InternalWorkbook &&
                chartData.getEmbeddedWorkbookType() == aspose.slides.WorkbookType.WorkbookBinaryMacro)
        {
            continue;
        }

        // Read or modify chart workbook data.
        console.log(chartData.getSeries().get_Item(0).getName().getAsCells().hashCode());

        let cell = chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell();
        console.log(cell.getValue());
    }

    presentation.save("charts-out.pptx", aspose.slides.SaveFormat.Pptx);
} finally {
    presentation.dispose();
}

```

