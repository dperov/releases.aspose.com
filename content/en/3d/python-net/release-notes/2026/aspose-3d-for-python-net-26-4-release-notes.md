---
id: "aspose-3d-for-python-net-26-4-release-notes"
slug: "aspose-3d-for-python-net-26-4-release-notes"
linktitle: "Aspose.3D for Python via .NET 26.4 Release Notes"
title: "Aspose.3D for Python via .NET 26.4 Release Notes"
weight: 9
description: "Aspose.3D for Python via .NET 26.4 Release Notes - the latest updates and fixes."
type: "repository"
layout: "release"
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.3D for Python via .NET 26.4.

{{% /alert %}}
## **Improvements and Changes**
|**Key**|**Summary**|**Category**|
| :- | :- | :- |
| THREEDNET-1760 | Expose more animation related information | Improvement |
| THREEDNET-1757 | Matrix Decompose causes negative scaling | Bug fixing |

## API Changes ##

### Added members to class **aspose.threed.animation.BindPoint**:

{{< highlight python >}}
	@property
	def channels(self) -> Iterable[aspose.threed.animation.AnimationChannel]
{{< /highlight >}}

`Channels` exposed all internal channels from `BindPoint`.


### Added members to class **aspose.threed.Property**:

{{< highlight python >}}
	@property
	def owner(self) -> aspose.threed.A3DObject
	@property
	def bind_points(self) -> Iterable[aspose.threed.animation.BindPoint]
{{< /highlight >}}

**Sample code**
{{< highlight python >}}
{{< /highlight >}}


