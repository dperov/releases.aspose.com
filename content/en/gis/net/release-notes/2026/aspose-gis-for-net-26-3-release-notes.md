---
id: "aspose-gis-for-net-26-3-release-notes"
slug: "aspose-gis-for-net-26-3-release-notes"
linktitle: "Aspose.GIS for .NET 26.3 Release Notes"
title: "Aspose.GIS for .NET 26.3 Release Notes"
weight: 90
description: "Aspose.GIS for .NET 26.3 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.GIS for .NET 26.3 Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes information for [Aspose.GIS for .NET 26.3](https://www.nuget.org/packages/Aspose.GIS/26.3.0).

{{% /alert %}}

## **Full List of Issues Covering all Changes in this Release**

|**Key**    |**Summary**                                                                                           |**Category**|
|:--------- |:-----------------------------------------------------------------------------------------------------|:-----------|
|GISNET-1973|Support MultiPolygon Geometry Type For EsriJson Format on conversions                                 |Feature     |
|GISNET-1984|Incorrect Count Of Layers For Gpx Format in NET Core 3.1                                              |Bug         |
|GISNET-1976|Using of "WritePolygonsAsLines" Option For Gpx Format                                                 |Example     |

## **Public API and Backward Incompatible Changes**
Following members have been added:

* None

Following members have been removed:

* None


# **Usage examples:**


**GISNET-1973. Support MultiPolygon Geometry Type For EsriJson Format on conversions**
{{< highlight csharp >}}
// EsriJson doesn't support "MultiPolygon" geometry type by design.
// It uses Exterior and Interiors rings instead.
// So, we implemented correct conversions on that automatically replace the MultiPolygon with supported Rings

var multiPolygon = new MultiPolygon
{
	new Polygon(new LinearRing(new [] { new Point(0, 0), new Point(10, 0), new Point(10, 10), new Point(0, 10), new Point(0, 0)}),
	new List() {new LinearRing(new[] { new Point(3, 3), new Point(3, 6), new Point(6, 6), new Point(6, 3), new Point(3, 3) }) }),
	new Polygon(new LinearRing(new [] { new Point(30, 0), new Point(40, 0), new Point(40, 10), new Point(30, 10), new Point(30, 0)}),
	new List() {new LinearRing(new[] { new Point(33, 3), new Point(33, 6), new Point(36, 6), new Point(36, 3), new Point(33, 3) }) })
};
using (var layer = VectorLayer.Create(fileName, Drivers.EsriJson, options))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = multiPolygon ;
	layer.Add(feature);
}
{{< /highlight >}}

**GISNET-1984. Incorrect Count Of Layers For Gpx Format in NET Core 3.1**
{{< highlight csharp >}}
	 var options = new ConversionOptions();
	 options.DestinationDriverOptions = new GpxOptions() { WritePolygonsAsLines = true };

	 string sourcePath = "daniSample.shp";
	 string destinationPath = "output.gpx";
	 VectorLayer.Convert(sourcePath, Drivers.Shapefile, destinationPath, Drivers.Gpx, options);
	 using (var layer = VectorLayer.Open(destinationPath, Drivers.Gpx))
	 {
		 Assert.AreEqual(6, layer.Count);
		 Assert.AreEqual(23, layer.Attributes.Count);
	 }
{{< /highlight >}}

**GISNET-1976. Using of "WritePolygonsAsLines" Option For Gpx Format**
{{< highlight csharp >}}
// GpxDriver doesn't support 'Polygon' and 'MultiPolygon' geometry type by design
// But you can use option WritePolygonsAsLines = true for conversions to avoid this

var options = new ConversionOptions();
options.DestinationDriverOptions = new GpxOptions() { WritePolygonsAsLines = true };

string sourcePath = Path.Combine("set the path to file");
string destinationPath = GetOutputPath(".gpx");
VectorLayer.Convert(sourcePath, Drivers.Shapefile, destinationPath, Drivers.Gpx, options);
{{< /highlight >}}
