---
id: "aspose-3d-for-java-26-4-release-notes"
slug: "aspose-3d-for-java-26-4-release-notes"
linktitle: "Aspose.3D for Java 26.4 Release Notes"
title: "Aspose.3D for Java 26.4 Release Notes"
weight: 9
description: "Aspose.3D for Java 26.4 Release Notes - the latest updates and fixes."
type: "repository"
layout: "release"
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.3D for Java 26.4.

{{% /alert %}}
## **Improvements and Changes**
|**Key**|**Summary**|**Category**|
| :- | :- | :- |
| THREEDNET-1760 | Expose more animation related information | Improvement |
| THREEDNET-1757 | Matrix Decompose causes negative scaling | Bug fixing |

## API Changes ##

### Added members to class **com.aspose.threed.BindPoint**:

{{< highlight java >}}
	public java.util.Collection getChannels()
{{< /highlight >}}

`getChannels` exposed all internal channels from `BindPoint`.

### Added members to class **com.aspose.threed.Property**:

{{< highlight java >}}
	public com.aspose.threed.A3DObject getOwner()
	public java.util.Collection getBindPoints()
{{< /highlight >}}

**Sample code**
{{< highlight java >}}
        private static List<BindPoint> getBindPointsFor(A3DObject obj)
        {
            List<BindPoint> ret = new ArrayList<>();
            for(var prop : obj.getProperties())
            {
                for(var bp : prop.getBindPoints())
                {
                    ret.add(bp);
                }
            }
            return ret;
        }
        var scene = Scene.fromFile("scene.FBX");
        //get property owner from property
        var obj = scene.getAnimationClips().get(0).getAnimations().get(0).getBindPoints().get(0).getProperty().getOwner();
        var node = scene.getRootNode().selectSingleObject("Bip01");
        for(var bindPoint : getBindPointsFor(obj))
        {
            //list all channels from bind point
            for(var ch : bindPoint.getChannels())
            {
                System.out.println(bindPoint.getName() + "." + ch.getName());
            }
        }

{{< /highlight >}}


