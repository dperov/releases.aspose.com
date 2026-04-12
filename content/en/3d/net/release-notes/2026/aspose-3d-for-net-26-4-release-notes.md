---
id: "aspose-3d-for-net-26-4-release-notes"
slug: "aspose-3d-for-net-26-4-release-notes"
linktitle: "Aspose.3D for .NET 26.4 Release Notes"
title: "Aspose.3D for .NET 26.4 Release Notes"
weight: 9
description: "Aspose.3D for .NET 26.4 Release Notes - the latest updates and fixes."
type: "repository"
layout: "release"
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.3D for .NET 26.4.

{{% /alert %}}
## **Improvements and Changes**
|**Key**|**Summary**|**Category**|
| :- | :- | :- |
| THREEDNET-1760 | Expose more animation related information | Improvement |
| THREEDNET-1757 | Matrix Decompose causes negative scaling | Bug fixing |

## API Changes ##

### Added members to class **Aspose.ThreeD.Animation.BindPoint**:

{{< highlight csharp >}}
	public System.Collections.Generic.ICollection<Aspose.ThreeD.Animation.AnimationChannel> Channels{ get;}
{{< /highlight >}}

`Channels` exposed all internal channels from `BindPoint`.

### Added members to class **Aspose.ThreeD.Property**:

{{< highlight csharp >}}
	public Aspose.ThreeD.A3DObject Owner{ get;}
	public System.Collections.Generic.ICollection<Aspose.ThreeD.Animation.BindPoint> BindPoints{ get;}
{{< /highlight >}}

**Sample code**
{{< highlight csharp >}}
        /// <summary>
        /// Gets all bind points from specified object
        /// </summary>
        /// <param name="obj"></param>
        /// <returns></returns>
        private static IEnumerable<BindPoint> GetBindPointsFor(A3DObject obj)
        {
            foreach(var prop in obj.Properties)
            {
                foreach(var bp in prop.BindPoints)
                {
                    yield return bp;
                }
            }
        }
        var scene = Scene.FromFile(@"scene.FBX");
        //get property owner from property
        var obj = scene.AnimationClips[0].Animations[0].BindPoints[0].Property.Owner;
        var node = scene.RootNode.SelectSingleObject("Bip01");
        foreach(var bindPoint in GetBindPointsFor(obj))
        {
            //list all channels from bind point
            foreach(var ch in bindPoint.Channels)
            {
                Console.WriteLine(bindPoint.Name + "." + ch.Name);
            }
        }

{{< /highlight >}}


