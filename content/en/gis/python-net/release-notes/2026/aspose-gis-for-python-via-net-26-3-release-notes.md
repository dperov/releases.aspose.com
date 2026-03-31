---
id: "aspose-gis-for-python-via-net-26-2-release-notes"
slug: "aspose-gis-for-python-via-net-26-2-release-notes"
linktitle: "Aspose.GIS for Python via .NET 26.3 Release Notes"
title: "Aspose.GIS for for Python via .NET 26.3 Release Notes"
weight: 100
description: "Aspose.GIS for Python via .NET 26.3 Release Notes – the latest updates and fixes."
type: "repository"
layout: "release"
hideChildren: false
toc: false
family_listing_page_title: "Aspose.GIS for Python via .NET 26.3 Release Notes"
menuItemWithNoContent: false
---

{{% alert color="primary" %}}

This page contains release notes information for [Aspose.GIS for Python via .NET 26.3](https://pypi.org/project/aspose-gis-net/).

{{% /alert %}}

## **Full List of Issues Covering all Changes in this Release**

|**Key**     |**Summary**                                                                                           |**Category**|
|:---------- |:-----------------------------------------------------------------------------------------------------|:-----------|
|GISPYTHON-72|Incorrect Count Of Layers For Gpx Format in Python Version                                            |Bug         |
|GISPYTHON-70|Support MultiPolygon Geometry Type For EsriJson Format on conversions                                 |Enhancement |
|GISPYTHON-71|Using of "WritePolygonsAsLines" Option For Gpx Format                                                 |Example     |

## **Public API and Backward Incompatible Changes**
Following members have been added:

* None

Following members have been removed:

* None

## **Usage examples:**

**GISPYTHON-72. Incorrect Count Of Layers For Gpx Format in Python Version**
{{< highlight python >}}
        # Configure conversion options with polygon-to-line transformation
        options = ConversionOptions()
        options.destination_driver_options = GpxOptions()
        options.destination_driver_options.write_polygons_as_lines = True

        source_path = "daniSample.shp"
        destination_path = "output.gpx"

        # Convert Shapefile to GPX
        VectorLayer.convert(source_path, Drivers.shapefile, destination_path, Drivers.gpx, options)

        # Verify the conversion results
        with VectorLayer.open(destination_path, Drivers.gpx) as layer:
            assert layer.count == 6
            assert layer.attributes.count == 23
{{< /highlight >}}

**GISPYTHON-70. Support MultiPolygon Geometry Type For EsriJson Format on conversions**
{{< highlight python >}}
        # Create a MultiPolygon with two polygons (each with an outer ring and an inner hole)
        multi_polygon = MultiPolygon()

        # First polygon with a hole
        outer_ring1 = LinearRing([
            Point(0, 0), Point(10, 0), Point(10, 10),
            Point(0, 10), Point(0, 0)
        ])
        inner_ring1 = LinearRing([
            Point(3, 3), Point(3, 6), Point(6, 6),
            Point(6, 3), Point(3, 3)
        ])
        polygon1 = Polygon(outer_ring1, [inner_ring1])
        multi_polygon.add(polygon1)

        # Second polygon with a hole
        outer_ring2 = LinearRing([
            Point(30, 0), Point(40, 0), Point(40, 10),
            Point(30, 10), Point(30, 0)
        ])
        inner_ring2 = LinearRing([
            Point(33, 3), Point(33, 6), Point(36, 6),
            Point(36, 3), Point(33, 3)
        ])
        polygon2 = Polygon(outer_ring2, [inner_ring2])
        multi_polygon.add(polygon2)

        outputFile = "output_esrijson.json" 

        with VectorLayer.create(outputFile, Drivers.esri_json) as layer:
            feature = layer.construct_feature()
            feature.geometry = multi_polygon
            layer.add(feature)
{{< /highlight >}}

**GISPYTHON-71. Using of "WritePolygonsAsLines" Option For Gpx Format**
{{< highlight python >}}
        # Configure conversion options with polygon-to-line transformation
        options = ConversionOptions()
        options.destination_driver_options = GpxOptions()

        # Gpx doesn't support polygons but you can save it in gpx like lines
        options.destination_driver_options.write_polygons_as_lines = True

        source_path = "daniSample.shp"
        destination_path = "output.gpx"

        # Convert Shapefile to GPX
        VectorLayer.convert(source_path, Drivers.shapefile, destination_path, Drivers.gpx, options)

        with VectorLayer.open(source_path, Drivers.shapefile) as layer:
            attrCountOriginal = layer.attributes.count

        # Verify the conversion results
        with VectorLayer.open(destination_path, Drivers.gpx) as layer:
            assert layer.attributes.count > attrCountOriginal
{{< /highlight >}}