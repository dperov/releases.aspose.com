---
id: "aspose-cells-for-net-26-4-release-notes"
slug: "aspose-cells-for-net-26-4-release-notes"
linktitle: "Aspose.Cells for .NET 26.4 Release Notes"
title: "Aspose.Cells for .NET 26.4 Release Notes"
weight: 9
description: "Aspose.Cells for .Net 26.4 Release Notes - the latest enhancements, new features, and fixes. "
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Cells for .NET 26.4 Release Notes"
keywords: "Aspose.Cells for .Net 26.4 Release Notes, Aspose.Cells for .Net 26.4 updates and fixes"
---

{{% alert color="primary" %}}

This page contains release notes for [Aspose.Cells for .NET 26.4](https://www.nuget.org/packages/Aspose.Cells/26.4.0).

{{% /alert %}}

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|CELLSNET-59903|Support to calculate REGEXEXTRACT function|New Feature
|CELLSNET-59904|Support to calculate REGEXREPLACE function|New Feature
|CELLSNET-59975|Support to expend table when copying ranges|New Feature
|CELLSNET-59989|Support to decrypt encrypted ods with odf 1.4 specification in .NetFramwork4.8, .net6, .net8 or above|New Feature
|CELLSNET-59964|Support to copy one rich value from another workbook|Enhancement
|CELLSNET-59976|Shift formulas after insert cut ranges|Enhancement
|CELLSNET-60018|Support to format a whole row or column of pivot table|Enhancement
|CELLSNET-60023|Support to export total label of table column to xls file|Enhancement
|CELLSNET-59982|Final punctuation mark "。" missing in the output PDF - Excel to PDF conversion|Bug
|CELLSNET-60002|Fail to set font color for shape|Bug
|CELLSNET-60005|Shape.Id changed after save|Bug
|CELLSNET-59952|NullPointerException was thrown when setting dynamic array formula for a cell with custom values|Bug
|CELLSNET-59953|Array formula with volatile functions is not saved properly when saving xlsx file|Bug
|CELLSNET-59985|CalculateFormula fails on chained dynamic array formulas|Bug
|CELLSNET-60011|AND function in shared formula was calculated incorrectly|Bug
|CELLSNET-60012|INDEX function in shared formula was calculated incorrectly|Bug
|CELLSNET-60028|Defined Name staring with a pair of square brackets and enclosed content is taken as invalid|Bug
|CELLSNET-60029|Setting formula failed when referencing to defined name starting with square brackets|Bug
|CELLSNET-60064|Cell.StringValue does not format the value with rich value of formatted number|Bug
|CELLSNET-60068|MAP function was calculated as #VALUE! but in ms excel it should be #CALC!|Bug
|CELLSNET-59907|Pillars incomplete when rendering image|Bug
|CELLSNET-59940|Excel chart data labels corrupted with 'CELLR' text and oversized balloons during rendering|Bug
|CELLSNET-59947|Missing label in the legend of a PivotChart on Chart.ToPdf method|Bug
|CELLSNET-59972|Abnormal "Infinity" data appears in the XPS file|Bug
|CELLSNET-59986|Chart legend incorrectly displays hidden 'Lower Bound' series and omits 'Range' series during export|Bug
|CELLSNET-59827|Indent of pivot item is not same as MS Excel|Bug
|CELLSNET-59942|Copying sheets between workbooks causes issues when textjoin is used in a formula|Bug
|CELLSNET-59950|STOCKHISTORY formula caused circular reference error in xlsb|Bug
|CELLSNET-59955|The line graph (Sparklines) under the column Trend (line) is totally different from Excel|Bug
|CELLSNET-59962|Lost data source of pivot chart|Bug
|CELLSNET-59973|Structured table references in formulas are corrupted after Cells.InsertCutCells|Bug
|CELLSNET-59983|Removing the first row of a table gives error|Bug
|CELLSNET-60007|Issue with AutoFitColumns function|Bug
|CELLSNET-60008|An extra blank row was inserted when pivot table does not contain grandtotal row.|Bug
|CELLSNET-60044|Invalid row subheading area if  blank rows are inserted for the next level pivot file|Bug
|CELLSNET-60048|Enhance the style of  pivot filter region with pagination|Bug
|CELLSNET-60066|Embedded objects becomes pictures.|Bug

## **Public API and Backwards Incompatible Changes**

The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Cells for .NET. If you have concerns about any change listed, please raise it on the Aspose.Cells support forum.

### **Adds new property CopyOptions.UpdateInvalidReferencesToTargetSheet.**

Indicates whether to refer to target worksheet if the referred worksheet is not copied.

### **Adds new member ErrorCellValueType.Value.**

Represents the value of a cell containing a `#VALUE!` error.

### **Adds new member ErrorCellValueType.Ref.**

Represents the value of a cell containing a `#REF!` error.

### **Adds new member ErrorCellValueType.NA.**

Represents the value of a cell containing a `#N/A` error.

