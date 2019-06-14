---
layout: post
title: Shape type in Syncfusion SfMaps control for Xamarin.Forms
description: This section describes the shape type of shape file layer on maps control.
platform: Xamarin.iOS
control: SfMaps
documentation: ug
---

# Shape Type

[`SfMaps`](https://help.syncfusion.com/xamarin/sfmaps/getting-started) allows to provide various shape type in the [`ShapeFileLayer`](https://help.syncfusion.com/xamarin/sfmaps/layers#shape-file-layer) such as Polygon, Polyline and Points.

## Polygon

A polygon is a two-dimensional surface stored as a sequence of points defining its exterior bounding ring and 0 or more interior rings. Polygons are always simple. Mostly the polygon shape type defines group of land, water bodies, and other features that have a spatial extent.

![Single selection support in Xamarin.Forms Maps](Images/polygon.jpg)

## Polyline

The polyline is shape that has a dimension of 1. It is called a simple line, if it does not intersect itself. The polylines are often used to define linear features such as roads, rivers, and power lines. Mostly the shape file layer with the polyline shape type is used as [`sublayer`](https://help.syncfusion.com/xamarin/sfmaps/sublayer#adding-sublayers-in-shapefilelayer).

The below example demonstrates the sublayer with the polyline shape type. In that roads(sublayer) of Bahrain (base layer) has been displayed using the shape file layer of maps

{% tabs %}

{% highlight c# %}

SFMap maps = new SFMap();

SFShapeFileLayer layer = new SFShapeFileLayer();

layer.Uri = (NSString)"Bahrain.shp";

SFShapeSetting layerSetting = new SFShapeSetting();
            
layerSetting.Fill = UIColor.FromRGB(188, 188, 188);

layer.ShapeSettings = layerSetting;

SFShapeFileLayer subLayer = new SFShapeFileLayer();
      
subLayer.Uri = (NSString)"roads.shp";

SFShapeSetting subLayerSetting = new SFShapeSetting();

subLayerSetting.Fill = UIColor.Black;

subLayerSetting.StrokeThickness = 2;

subLayer.ShapeSettings = subLayerSetting;

layer.Sublayers.Add(subLayer);

maps.Layers.Add(layer);

View.AddSubview(maps); 

{% endhighlight %}

{% endtabs %}

![Single selection support in Xamarin.Forms Maps](Images/polyline.jpg)

## Points

A point is shape with a dimension of 0 that occupies a single location in coordinate space. A point has a single x,y coordinate value. The points are often used to define features such as oil wells, landmarks, and elevations.

The below example demonstrates the [`sublayer`](https://help.syncfusion.com/xamarin/sfmaps/sublayer#adding-sublayers-in-shapefilelayer) with the points shape type. In that, the places (sublayer) of Australia (base layer) has been displayed using the shape file layer of maps

{% tabs %}

{% highlight c# %}

SFMap maps = new SFMap();

SFShapeFileLayer layer = new SFShapeFileLayer();
            
layer.Uri = (NSString)"australia.shp";

SFShapeSetting layerSetting = new SFShapeSetting();
            
layerSetting.Fill = UIColor.FromRGB(188, 188, 188);

layer.ShapeSettings = layerSetting;

SFShapeFileLayer subLayer = new SFShapeFileLayer();

subLayer.Uri = (NSString)"points.shp";

subLayer.MapPointIconSize = 5;

SFShapeSetting subLayerSetting = new SFShapeSetting();

subLayerSetting.Fill = UIColor.Black;

subLayer.ShapeSettings = subLayerSetting;

layer.Sublayers.Add(subLayer);
           
maps.Layers.Add(layer);

View.AddSubview(maps); 

{% endhighlight %}

{% endtabs %}

![Multiple selection in Xamarin.Forms Maps](Images/points.jpg)

### Customization of Points

The size, shape and position of the map points can be customized with the [`MapPointIconSize`], [`MapPointIcon`], [`MapPointHorizontalAlignment`] and [`MapPointVerticalAlignment`] property of shape file layer

### Map point icon

The shape of the map point has been customized using the [`MapPointIcon`] property of ShapeFileLayer. SfMap supports the following map point icon types,

*	Circle,
*	Rectangle,
*	Square,
*	Diamond,
*	Star

{% tabs %}

{% highlight c# %}

SFMap maps = new SFMap();

SFShapeFileLayer layer = new SFShapeFileLayer();

layer.Uri = (NSString)"australia.shp";

SFShapeSetting layerSetting = new SFShapeSetting();
            
layerSetting.Fill = UIColor.FromRGB(188, 188, 188);
           
layer.ShapeSettings = layerSetting;

SFShapeFileLayer subLayer = new SFShapeFileLayer();
            
subLayer.Uri = (NSString)"points.shp";
            
subLayer.MapPointIcon = SFMapPointIcon.SFMapPointIconCircle;
            
subLayer.MapPointIconSize = 15;

SFShapeSetting subLayerSetting = new SFShapeSetting();
            
subLayerSetting.Fill = UIColor.Green;
            
subLayer.ShapeSettings = subLayerSetting;

layer.Sublayers.Add(subLayer);
            
maps.Layers.Add(layer);
            
View.AddSubview(maps); 

{% endhighlight %}

{% endtabs %}

![Multiple selection in Xamarin.Forms Maps](Images/icons.png)

### Map point position

The position of the map points can be customized using the [`MapPointHorizontalAlignment`] and [`MapPointVerticalAlignment`] property of shape file layer. These properties allow us to vary the position as Near, Far and Center by considering the provided latitude ,longitude and the map point icon size.

{% tabs %}

{% highlight c# %}

SFMap maps = new SFMap();

SFShapeFileLayer layer = new SFShapeFileLayer();

layer.Uri = (NSString)"australia.shp";

SFShapeSetting layerSetting = new SFShapeSetting();

layerSetting.Fill = UIColor.FromRGB(188, 188, 188);

layer.ShapeSettings = layerSetting;

SFShapeFileLayer subLayer = new SFShapeFileLayer();

subLayer.Uri = (NSString)"points.shp";

subLayer.MapPointIcon = SFMapPointIcon.SFMapPointIconCircle;

subLayer.MapPointIconSize = 15;

subLayer.MapPointHorizontalAlignment = MarkerAlignment.Near;

subLayer.MapPointHorizontalAlignment = MarkerAlignment.Near;

SFShapeSetting subLayerSetting = new SFShapeSetting();

subLayerSetting.Fill = UIColor.Green;

subLayer.ShapeSettings = subLayerSetting;

layer.Sublayers.Add(subLayer);

maps.Layers.Add(layer);

View.AddSubview(maps); 

{% endhighlight %}

{% endtabs %}

![Multiple selection in Xamarin.Forms Maps](Images/mapAlignmnet.png)

### Map point size

The size of the map points can be customized with the [`MapPointIconSize`] property of  ShapeFileLayer

{% tabs %}

{% highlight c# %}

SFMap maps = new SFMap();

SFShapeFileLayer layer = new SFShapeFileLayer();

layer.Uri = (NSString)"australia.shp";

SFShapeSetting layerSetting = new SFShapeSetting();

layerSetting.Fill = UIColor.FromRGB(188, 188, 188);

layer.ShapeSettings = layerSetting;

SFShapeFileLayer subLayer = new SFShapeFileLayer();
            
subLayer.Uri = (NSString)"points.shp";
            
subLayer.MapPointIcon = SFMapPointIcon.SFMapPointIconCircle;

subLayer.MapPointIconSize = 15;
            
SFShapeSetting subLayerSetting = new SFShapeSetting();
            
subLayerSetting.Fill = UIColor.Orange;

subLayer.ShapeSettings = subLayerSetting;

layer.Sublayers.Add(subLayer);

maps.Layers.Add(layer);

View.AddSubview(maps); 

{% endhighlight %}

{% endtabs %}

![Multiple selection in Xamarin.Forms Maps](Images/size.jpg)

