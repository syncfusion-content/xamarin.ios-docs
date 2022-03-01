---
layout: post
title: Populate Data of syncfusion maps control for Xamarin.iOS
description: How to populate the datasource
platform: Xamarin.iOS
control: SfMaps 
documentation: ug
---

# Populate Data

This section describes on how to populate shape data for providing Data input to the Map control and usage of DataSource property.

## Data Binding

The Maps control supports data binding with the DataSource property in the shape layers.

The following properties in shape layers are used for binding data in Maps control,

* DataSource
* ShapeIdPath
* ShapeIdTableField

### ItemsSource

The [`DataSource`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfMaps.iOS.SFShapeFileLayer.html#Syncfusion_SfMaps_iOS_SFShapeFileLayer_DataSource) property accepts the collection values as input. 

### ShapeIdPath

The [`ShapeIDPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfMaps.iOS.SFShapeFileLayer.html#Syncfusion_SfMaps_iOS_SFShapeFileLayer_ShapeIDPath) property refers the data ID in DataSource.

### ShapeIdTableField

The [`ShapeIDTableField`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfMaps.iOS.SFShapeFileLayer.html#Syncfusion_SfMaps_iOS_SFShapeFileLayer_ShapeIDTableField) property is similar to the `ShapeIDPath` that refers to the column name in the data property of shape layers to identify the shape. When the values of the `ShapeIDPath` property in the DataSource property and the values of `ShapeIDTableField` in the data property match, the associated object from the DataSource is bound to the corresponding shape.

{% tabs %}

{% highlight c# %}

SFShapeFileLayer layer = new SFShapeFileLayer();

layer.Uri = (NSString)NSBundle.MainBundle.PathForResource("usa_state", "shp");

layer.DataSource = GetDataSource();

layer.ShapeIDTableField = (NSString)"STATE_NAME";

layer.ShapeIDPath = (NSString)"State";

map.Layers.Add(layer);

{% endhighlight %}

{% endtabs %}

Refer the following USA Election data which is used as items source.

{% highlight c# %}

NSMutableArray GetDataSource()

{

NSMutableArray array = new NSMutableArray();

array.Add(getDictionary("Alabama", "Romney", 9));

array.Add(getDictionary("Alaska", "Romney", 3));

array.Add(getDictionary("Arizona", "Romney", 11));

array.Add(getDictionary("Arkansas", "Romney", 6));

array.Add(getDictionary("California", "Romney", 55));

array.Add(getDictionary("Colorado", "Obama", 9));

array.Add(getDictionary("Connecticut", "Obama", 7));

array.Add(getDictionary("Delaware", "Obama", 3));

array.Add(getDictionary("District of Columbia", "Obama", 3));

array.Add(getDictionary("Florida", "Obama", 29));

array.Add(getDictionary("Georgia", "Obama", 16));

array.Add(getDictionary("Hawaii", "Romney", 4));

array.Add(getDictionary("Idaho", "Obama", 4));

array.Add(getDictionary("Illinois", "Romney", 20));

array.Add(getDictionary("Indiana", "Obama", 11));

array.Add(getDictionary("Iowa", "Romney", 6));

array.Add(getDictionary("Kansas", "Obama", 6));

array.Add(getDictionary("Kentucky", "Romney", 8));

array.Add(getDictionary("Louisiana", "Romney", 8));

array.Add(getDictionary("Maine", "Romney", 4));

array.Add(getDictionary("Maryland", "Obama", 10));

array.Add(getDictionary("Massachusetts", "Obama", 11));

array.Add(getDictionary("Michigan", "Obama", 16));

array.Add(getDictionary("Minnesota", "Obama", 10));

array.Add(getDictionary("Mississippi", "Obama", 6));

array.Add(getDictionary("Missouri", "Obama", 10));

array.Add(getDictionary("Montana", "Romney", 3));

array.Add(getDictionary("Nebraska", "Romney", 5));

array.Add(getDictionary("Nevada", "Romney", 6));

array.Add(getDictionary("New Hampshire", "Obama", 4));

array.Add(getDictionary("New Jersey", "Obama", 14));

array.Add(getDictionary("New Mexico", "Obama", 5));

array.Add(getDictionary("New York", "Obama", 29));

array.Add(getDictionary("North Carolina", "Romney", 15));

array.Add(getDictionary("North Dakota", "Romney", 3));

array.Add(getDictionary("Ohio", "Obama", 18));

array.Add(getDictionary("Oklahoma", "Romney", 7));

array.Add(getDictionary("Oregon", "Obama", 7));

array.Add(getDictionary("Pennsylvania", "Obama", 20));

array.Add(getDictionary("Rhode Island", "Obama", 4));

array.Add(getDictionary("South Carolina", "Romney", 9));

array.Add(getDictionary("South Dakota", "Romney", 3));

array.Add(getDictionary("Tennessee", "Romney", 11));

array.Add(getDictionary("Texas", "Romney", 38));

array.Add(getDictionary("Utah", "Romney", 6));

array.Add(getDictionary("Vermont", "Obama", 3));

array.Add(getDictionary("Virginia", "Obama", 13));

array.Add(getDictionary("Washington", "Obama", 12));

array.Add(getDictionary("West Virginia", "Romney", 5));

array.Add(getDictionary("Wisconsin", "Obama", 10));

array.Add(getDictionary("Wyoming", "Romney", 3));

return array;
}

NSDictionary getDictionary(string name, string type, int index)

{

NSString name1 = (NSString)name;

object[] objects = new object[3];

object[] keys = new object[3];

keys.SetValue("State", 0);

keys.SetValue("Candidate", 1);

keys.SetValue("Electors", 2);

objects.SetValue(name1, 0);

objects.SetValue(type, 1);

objects.SetValue(index, 2);

return NSDictionary.FromObjectsAndKeys(objects, keys);

}

{% endhighlight %}
