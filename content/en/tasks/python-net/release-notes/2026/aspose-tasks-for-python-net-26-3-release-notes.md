---
id: "aspose-tasks-for-python-net-26-3-release-notes"
slug: "aspose-tasks-for-python-net-26-3-release-notes"
linktitle: "Aspose.Tasks for Python via .NET 26.3 Release Notes"
title: "Aspose.Tasks for Python via .NET 26.3 Release Notes"
weight: 98
description: "The page contains the release notes for Aspose.Tasks for Python via .NET 26.3."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.Tasks for Python via .NET 26.3 Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes information for [Aspose.Tasks for Python via .Net 26.3](https://pypi.org/project/aspose-tasks/26.3.0/).

{{% /alert %}}

## **All Changes**

|**Key**|**Summary**|**Issue Type**|
| :- | :- | :- |
| TASKSNET-11596 | Fix CalendarException.ToDate property setter logic | Enhancement |
| TASKSNET-11682 | Fix writing of EarnedValueMethod and PhysicalPercentComplete fields to MPP format | Bug |
| TASKSNET-11680 | Fix incorrect calculation of formula with absent Date fields values | Bug |
| TASKSNET-11631 | Fix Activity Codes and User Defined Fields are not read when project is read from Primavera DB | Bug |


**Related issue: TASKSNET-11596 - Fix CalendarException.ToDate property setter logic.**

Starting with version 26.3, when a CalendarException is created and the ToDate property is specified without a time part, the ToDate property is set to the end of the day.

```py
import aspose.tasks as tasks
from datetime import datetime

p = tasks.Project()
p.set(tasks.Prj.START_DATE, datetime(2025, 10, 15, 8, 0, 0))

exc = tasks.CalendarException()
exc.day_working = False
exc.occurrences = 1
exc.type = tasks.CalendarExceptionType.DAILY
exc.period = 1
exc.entered_by_occurrences = True

exc.from_date = datetime(2025, 10, 16)
exc.to_date = datetime(2025, 10, 16) // ToDate is set to 2025-10-16 23:59:00). Prior to 26.3 it was set to 2025-10-16 00:00:00.
p.calendar.exceptions.add(exc)
```
