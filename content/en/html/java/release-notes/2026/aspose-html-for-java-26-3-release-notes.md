---
id: "aspose-html-for-java-26-3-release-notes"
slug: "aspose-html-for-java-26-3-release-notes"
linktitle: "Aspose.HTML for Java 26.3 Release Notes"
title: "Aspose.HTML for Java 26.3 Release Notes"
weight: 100
description: "This article contains release notes information for Aspose.HTML for .Java 26.3."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.HTML for Java 26.3 Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes for Aspose.HTML for Java 26.3

{{% /alert %}}

We are honored to announce the March release of Aspose.HTML for Java.

## Fixed behavior of `HTMLCanvasElement.width`

In this release, we fixed the calculation of the `width` value returned by `HTMLCanvasElement`.

According to the HTML specification, the `<canvas>` element supports the `width` and `height` content attributes, and both of them must be parsed as **valid non-negative integers**. If the `width` attribute is missing or contains an invalid value, the implementation must fall back to the default width of **300 CSS pixels**.

## **Improvements and Changes**

| **Key**       | **Summary**                                                   | **Category** |
|---------------|---------------------------------------------------------------|--------------|
| HTMLJAVA-2002 | ArgumentException: Incompatible unit types in HTML rendering  | Bug          |  
