---
id: "aspose-cells-for-php-via-java-26-4-release-notes"
slug: "aspose-cells-for-php-via-java-26-4-release-notes"
linktitle: "Aspose.Cells for PHP via Java 26.4 Release Notes"
title: "Aspose.Cells for PHP via Java 26.4 Release Notes"
weight: 12
description: "Aspose.Cells for PHP via Java 26.4 Release Notes – the latest enhancements, new features, and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Cells for PHP via Java 26.4 Release Notes"
keywords: "Aspose.Cells for PHP via Java 26.4 Release Notes, Aspose.Cells for PHP via Java 26.4 updates and fixes"
---

{{% alert color="primary" %}}

This page contains release notes for [Aspose.Cells for PHP via Java 26.4](https://releases.aspose.com/cells/php/new-releases/aspose.cells-for-php-via-java-26.4/).

{{% /alert %}}

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|CELLSJAVA-46648|Excel shape with curved text path converts to straight path when converted into an image|Bug
|CELLSJAVA-46643|Custom number format using Arabic locale is not formatted as expected|Bug
|CELLSJAVA-46631|The page break is wrong while converting workbook to pdf|Bug
|CELLSJAVA-46612|Html to Excel rowspan issue|Bug
|CELLSJAVA-46651|Excel to HTML export: Fixed panes partially covered after scrolling|Bug
|CELLSJAVA-46652|Incorrect picture rotation in Excel-to-HTML conversion|Bug
|CELLSJAVA-46659|Cast Exception while saving workbook meta data|Exception
|CELLSJAVA-46660|NumberFormatException while opening workbook|Exception
|CELLSJAVA-46577|Support object stream in the generated pdf|Enhancement
|CELLSJAVA-46601|Formula cell value is read "`#VALUE!`" |Bug
|CELLSJAVA-46623|Waterfall chart Data labels are not getting removed|Bug
|CELLSJAVA-46624|Excel to HTML conversion - Content has some orphan "`</style>`" tag |Bug
|CELLSJAVA-46627|Difference in formula calculations by Aspose.Cells formula calculation engine compared to Excel|Bug
|CELLSJAVA-46632|"`#VALUE!`" for formula cells in template file was read as "`#UNKNOWN!`"|Bug
|CELLSJAVA-46578|Support REGEXTEST function|New Feature
|CELLSJAVA-46682|Support to decrypt encrypted ods with odf 1.4 specification |New Feature
|CELLSJAVA-46686|"CellsException: Corrupted file. (ExceptionType.IO)" on Workbook constructor when using incorrect password for ODS/OTS files|Enhancement
|CELLSJAVA-46683|Detect the file format of encrypted odf1.4 file|Enhancement
|CELLSJAVA-46692|XLOOKUP returns incorrect result when mixing TEXT and BOOLEAN values|Bug
|CELLSJAVA-46690|The settings for individual data points that affected the NumberFormat|Bug
|CELLSJAVA-46629|Some shapes missing in Excel to PDF conversion|Bug
|CELLSJAVA-46680|Nullpointer when opening password protected Open Office ods file|Exception

## **Public API and Backwards Incompatible Changes**

The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Cells for Java. If you have concerns about any change listed, please raise it on the Aspose.Cells support forum.

### **Adds new property HtmlLoadOptions.ParagrahLayoutMode.**

Specifies how `<p>` elements are rendered when loading HTML.

### **Obsoletes ChartFrame.BackgroundMode property.**

Please use ChartFrame.Area.FillFormat.FillType property instead.

### **Adds new enum HtmlParagraphLayoutMode.**

Represents how `<p>` elements are rendered during HTML load.

### **Adds new method TableStyle.Create(System.String, WorksheetCollection).**

Creates a TableStyle instance with the specified name for the given worksheets collection.

### **Adds new member TableStyleElementType.GrandTotalColumnHeader.**

Represents a style element that applies to the header of a pivot table’s grand total column.

### **Adds new member TableStyleElementType.GrandTotalRowHeader.**

Represents a style element that applies to the header of a pivot table’s grand total row.

### **Adds new property PivotOptions.ShowExpandCollapseFieldButtons.**

Supports to get or set a value indicating whether to show expand/collapse field buttons.

### **Adds new property Picture.IsPlacedInCell.**

Indicates whether to place the image in a cell or over cells.

### **Obsoletes Picture.PlaceInCell().**

Please use IsPlacedInCell property instead.

### **Adds new property NumbersLoadOptions.PreserveTableName.**

Indicates whether to preserve table names when importing from Numbers.

### **Adds new enum member OpenDocumentFormatVersionType.Odf14.**

Support ODF Version 1.4.

### **Adds new property PivotTable.PivotTableStyle.**

Gets or sets the table style settings of this pivot table.

### **Adds new property PivotTable.TopRightArea.**

Represents the blank area at the top-right of the PivotTable (top-left for RTL sheets).

### **Adds new property PivotTable.FilterArea.**

Gets the region of the filter area.

### **Adds new method PivotTable.GetButtonArea(PivotFieldType axisType).**

Gets the button area for a specified axis type.

### **Adds new method Worksheet.GetAllPictures().**

Gets all pictures including images embedded in cells and over the cells.

### **Adds new property CopyOptions.UpdateInvalidReferencesToTargetSheet.**

Indicates whether to refer to target worksheet if the referred worksheet is not copied.

### **Adds new member ErrorCellValueType.Value.**

Represents the value of a cell containing a `#VALUE!` error.

### **Adds new member ErrorCellValueType.Ref.**

Represents the value of a cell containing a `#REF!` error.

### **Adds new member ErrorCellValueType.NA.**

Represents the value of a cell containing a `#N/A` error.