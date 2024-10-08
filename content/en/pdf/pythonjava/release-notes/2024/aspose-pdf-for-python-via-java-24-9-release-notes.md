---
id: "aspose-pdf-for-python-via-java-24-9-release-notes"
slug: "aspose-pdf-for-python-via-java-24-9-release-notes"
linktitle: "Aspose.PDF for Python via Java 24.9 Release Notes"
title: "Aspose.PDF for Python via Java 24.9 Release Notes"
weight: 120
description: "Aspose.PDF for Python via Java 24.9 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
family_listing_page_title: "Aspose.PDF for Python via Java 24.9 Release Notes"
lastmod: "2024-09-17"
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.PDF for Python via Java 24.9.

{{% /alert %}}
## **Improvements and Changes**

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|PDFPYTHONJAVA-121|Create public API structure for python with all enums from version for Java|Feature|
|PDFPYTHONJAVA-122|Create public API structure for python with all classes from version for Java|Feature|

## **Public API and Backwards Incompatible Changes**

**Added new package of 964 classes in asposepdf.pdf that mirrors classes from com.aspose.pdf package in java**

- all enum from Public API in java are ported to python with elements and description
- all classes in base version with int fields and constants are ported to python

**Changes in BaseJavaClass class**

- method names was changed from def getJavaClass to  def get_java_object
- method names was changed from  def setJavaClass to def set_java_object
- method names was changed from  def isNull to def is_null
- added method def set_java_object(self, java_object)
- added methods def get_java_class_name(self)

