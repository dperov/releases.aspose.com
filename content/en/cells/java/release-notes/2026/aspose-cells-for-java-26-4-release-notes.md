---
id: "aspose-cells-for-java-26-4-release-notes"
slug: "aspose-cells-for-java-26-4-release-notes"
linktitle: "Aspose.Cells for Java 26.4 Release Notes"
title: "Aspose.Cells for Java 26.4 Release Notes"
weight: 9
description: "Aspose.Cells for Java 26.4 Release Notes - the latest updates and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.Cells for Java 26.4 Release Notes"
---

{{% alert color="primary" %}}

This page contains release notes for [Aspose.Cells for Java 26.4](https://releases.aspose.com/cells/java/26-4/).

{{% /alert %}}

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
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

### **Adds new property CopyOptions.UpdateInvalidReferencesToTargetSheet.**

Indicates whether to refer to target worksheet if the referred worksheet is not copied.

### **Adds new member ErrorCellValueType.Value.**

Represents the value of a cell containing a `#VALUE!` error.

### **Adds new member ErrorCellValueType.Ref.**

Represents the value of a cell containing a `#REF!` error.

### **Adds new member ErrorCellValueType.NA.**

Represents the value of a cell containing a `#N/A` error.