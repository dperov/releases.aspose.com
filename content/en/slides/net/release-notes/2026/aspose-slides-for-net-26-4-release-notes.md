---
id: "aspose-slides-for-net-26-4-release-notes"
slug: "aspose-slides-for-net-26-4-release-notes"
linktitle: "Aspose.Slides for .NET 26.4 Release Notes"
title: "Aspose.Slides for .NET 26.4 Release Notes"
weight: 45
description: "Aspose.Slides for .NET 26.4 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Slides for .NET 26.4 Release Notes"
---

{{% alert color="primary" %}}

This page contains release notes for [ Aspose.Slides for .NET 26.4](https://www.nuget.org/packages/Aspose.Slides.NET/).

{{% /alert %}}

## New Features and Improvements
|**Key**|**Summary**|**Category**|**Related Documentation**|
| :- | :- | :- | :- |
|SLIDESNET-45287|Accessing IChartSeries.Name.AsCells getter modifies a chart|Bug|<https://docs.aspose.com/slides/net/chart-workbook/>|
|SLIDESNET-45331|Embedded Japanese fonts are rendered as garbled text when converting slides to images|Bug|<https://docs.aspose.com/slides/net/embedded-font/>|
|SLIDESNET-45345|Slide layout ColorMapOverride is not applied to Master slide shapes when rendering|Bug|<https://docs.aspose.com/slides/net/convert-powerpoint-to-png/>|
|SLIDESNET-45328|Dashed lines on a chart are displayed incorrectly when converting PPTX to PDF|Bug||
|SLIDESNET-45346|PptxReadException occurs when loading a PPTX file|Bug|<https://docs.aspose.com/slides/net/open-presentation/>|
|SLIDESNET-45338|Vertical text incorrectly rotated when converting PPTX to PDF|Bug|<https://docs.aspose.com/slides/net/convert-powerpoint-to-pdf/>|
|SLIDESNET-45252|PowerPoint → PDF/UA-1: Table header options (Header Row / First Column) not mapped correctly|Bug|<https://docs.aspose.com/slides/net/convert-powerpoint-to-pdf/>|
|SLIDESNET-45299|Converting a shape to an image throws a NullReferenceException|Bug||
|SLIDESNET-45251|Incorrect List Tag Structure after PowerPoint to PDF Conversion (PDF/UA)|Bug|<https://docs.aspose.com/slides/net/convert-powerpoint-to-pdf/>|
|SLIDESNET-45302|XPS export breaks layout|Bug||
|SLIDESNET-45253|PowerPoint → PDF/UA: Paragraph split into multiple <P> tags |Investigation|<https://docs.aspose.com/slides/net/convert-powerpoint-to-pdf/>|
|SLIDESNET-45329|Images cause a presentation to fail to load|Bug|<https://docs.aspose.com/slides/net/open-presentation/>|
|SLIDESNET-45230|WordArt objects are displayed incorrectly when converting PPTX to PDF|Bug|<https://docs.aspose.com/slides/net/convert-powerpoint-to-pdf/#accessibility-and-compliance-standards-for-pdf>|
|SLIDESNET-44132|Text layouting is changed when loading and saving a PPT file|Bug|<https://docs.aspose.com/slides/net/save-presentation/>|
|SLIDESNET-44130|Font size is increased when loading and saving a PPT file|Bug|<https://docs.aspose.com/slides/net/save-presentation/>|
|SLIDESNET-45254|PowerPoint → PDF/UA: PAC crash on internal links using Named Actions|Bug|<https://docs.aspose.com/slides/net/convert-powerpoint-to-pdf/>|
|SLIDESNET-45177|Number format of chart data labels changes when converting a slide to an image|Bug||
|SLIDESNET-45307|A legacy 16-bit WMF file fails to render|Bug||


## Public API Changes

### Added New Enumeration: Aspose.Slides.Charts.WorkbookType

The new `WorkbookType` enumeration has been added. This enumeration specifies the type of Open XML workbook file.

```csharp
public enum WorkbookType
{
    /// <summary>
    /// The workbook type is not defined.
    /// </summary>
    NotDefined = -1,

    /// <summary>
    /// Excel workbook (*.xlsx).
    /// </summary>
    Workbook,

    /// <summary>
    /// Excel macro-enabled workbook (*.xlsm).
    /// </summary>
    WorkbookMacro,

    /// <summary>
    /// Excel template (*.xltx).
    /// </summary>
    Template,

    /// <summary>
    /// Excel macro-enabled template (*.xltm).
    /// </summary>
    TemplateMacro,

    /// <summary>
    /// Excel binary macro-enabled workbook (*.xlsb).
    /// </summary>
    WorkbookBinaryMacro
}
```

### Added New Property: IChartData.EmbeddedWorkbookType

The new `EmbeddedWorkbookType` property has been added to the `IChartData` interface and `ChartData` class. It allows you to get the type of the chart embedded workbook.

```csharp
/// <summary>
/// Gets the type of the embedded workbook.
/// Returns <see cref="WorkbookType.NotDefined"/> if <see cref="DataSourceType"/> is 
/// <see cref="ChartDataSourceType.ExternalWorkbook"/>.
/// Read-only <see cref="WorkbookType"/>.
/// </summary>
WorkbookType EmbeddedWorkbookType { get; }
```

**Usage Example**

Aspose.Slides does not support the Excel binary macro-enabled workbook (*.xlsb) format.
The following code example shows how to check whether a chart workbook format is supported before working with chart data:

```csharp
using (var presentation = new Presentation("charts.pptx"))
{
    foreach (var shape in presentation.Slides[0].Shapes)
    {
        if (!(shape is IChart chart))
            continue;

        var chartData = chart.ChartData;

        // Skip charts whose embedded workbook format is not supported.
        if (chartData.DataSourceType == ChartDataSourceType.InternalWorkbook &&
            chartData.EmbeddedWorkbookType == WorkbookType.WorkbookBinaryMacro)
        {
            continue;
        }

        // Read or modify chart workbook data.
        Console.WriteLine(chartData.Series[0].Name.AsCells.GetHashCode());

        var cell = chartData.Series[0].DataPoints[0].Value.AsCell;
        Console.WriteLine(cell.Value);
    }

    presentation.Save("charts-out.pptx", SaveFormat.Pptx);
}
```

