---
layout: post
title:  Legends of Essential Xamarin.iOS SfSunburstChart
description: This section describes the legend and its customization.
platform: Xamarin.iOS
control: SfSunburstChart
documentation: ug
---

# Legend

Legends are used to represent the first level (i.e root level) of categories in the sunburst chart.

## Visibility

The visibility of legends can be controlled using the [`IsVisible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegend.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegend_IsVisible) property.

The following code shows how to control the visibility of legend.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.Legend.IsVisible = true;

{% endhighlight %}

{% endtabs %} 

![](Legend_images/Legend.jpg)


## Position

Legends can be docked at the top, right, left, or bottom position using the [`LegendPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegend.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegend_LegendPosition) property.

The following code shows customizing the legend position.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.Legend.IsVisible = true;
  sunburstChart.Legend.LegendPosition = SunburstDockPosition.Left;

{% endhighlight %}

{% endtabs %} 

![](Legend_images/LegendPosition.jpg)


## Legend icon types

Legend icon shapes can be customized using the [`IconType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegend.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegend_IconType) property. The IconType property provides several predefined shapes. The default legend icon type is circle.

The following predefined shapes are available in the IconType property:

* Circle
* Cross
* Diamond
* Pentagon
* Rectangle
* Triangle.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.Legend.IsVisible = true;
  sunburstChart.Legend.IconType = SunburstLegendIcon.Diamond;

{% endhighlight %}

{% endtabs %} 

![](Legend_images/IconType.jpg)

## Icon size customization

The size of the legend icon can be customized using the [`IconHeight`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegend.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegend_IconHeight) and [`IconWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegend.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegend_IconWidth) properties.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.Legend.IsVisible = true;
  sunburstChart.Legend.IconType = SunburstLegendIcon.Diamond;
  sunburstChart.Legend.IconWidth = 15;
  sunburstChart.Legend.IconHeight = 15;            

{% endhighlight %}

{% endtabs %} 

![](Legend_images/IconSize.jpg)

## Customization

Legend label can be customized using the following properties available in [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegend.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegend_LabelStyle):

* [`Margin`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegendLabelStyle.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegendLabelStyle_Margin): Sets the specified margin for legend labels.
* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegendLabelStyle.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegendLabelStyle_Color): Customizes the text color of the label.
* [`Font`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegendLabelStyle.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegendLabelStyle_Font): Customizes the label's font.

Background color for the legend can be changed using the [`Background`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegend.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegend_Background)Property.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.Legend.IsVisible = true;
  sunburstChart.Legend.LabelStyle.Color = UIColor.Red;
  sunburstChart.Legend.LabelStyle.Font = UIFont.FromName("Arial", 12);
  sunburstChart.Legend.LabelStyle.Margin = new UIEdgeInsets(5, 5, 5, 5);
  sunburstChart.Legend.Background = UIColor.White;

{% endhighlight %}

{% endtabs %} 

![](Legend_images/LabelStyle.jpg)


## Item margin

Margin can be set to individual legend items using the [`ItemMargin`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSunburstChart.iOS.SunburstChartLegend.html#Syncfusion_SfSunburstChart_iOS_SunburstChartLegend_ItemMargin) property.

{% tabs %} 

{% highlight C# %} 

  sunburstChart.Legend.IsVisible = true;
  sunburstChart.Legend.ItemMargin = new UIEdgeInsets(3, 3, 3, 3);          

{% endhighlight %}

{% endtabs %} 

![](Legend_images/ItemMargin.png)

