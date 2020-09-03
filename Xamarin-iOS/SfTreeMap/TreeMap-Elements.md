---
layout: post
title: Treemap elements in Syncfusion TreeMap control for Xamarin.iOS
description: Describes the elements in the tree map control
platform: Xamarin.iOS
control: TreeMap
documentation: ug
---

# TreeMap Elements

The TreeMap contains the following elements:

* Legends
* Headers
* Labels

## Legend

You can set the color value of leaf nodes using the [`LegendSettings`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMap.html#Syncfusion_SfTreeMap_iOS_SFTreeMap_LegendSettings) property. This legend is appropriate only for the tree map whose leaf nodes are colored using [`RangeColorMapping`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFRangeColorMapping.html).

The visibility of legend can be enabled by setting the [`ShowLegend`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFLegendSetting.html#Syncfusion_SfTreeMap_iOS_SFLegendSetting_ShowLegend) property to true.

### TreeMap legends

You can set the size of legend icons by setting the [`IconSize`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFLegendSetting.html#Syncfusion_SfTreeMap_iOS_SFLegendSetting_ShowLegend) property of `LegendSettings` in TreeMap.

### Labels for legends

You can customize the labels of the legend items using the [`LegendLabel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFRange.html#Syncfusion_SfTreeMap_iOS_SFRange_LegendLabel) property of [`RangeColorMapping`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFRangeColorMapping.html). 

{% tabs %}

{% highlight c# %}

    SFLegendSetting legendSetting = new SFLegendSetting();
            legendSetting.ShowLegend = true;
            legendSetting.Size = new CoreGraphics.CGSize(500, 45);
            treeMap.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %} 

![Treemap legend](TreeMap_Images/Squarified.png)

## Header

You can set headers for each level by setting the [`ShowHeader`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMapLevel.html#Syncfusion_SfTreeMap_iOS_SFTreeMapLevel_ShowHeader) property of each **TreeMap** level. The [`HeaderHeight`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMapLevel.html#Syncfusion_SfTreeMap_iOS_SFTreeMapLevel_HeaderHeight) property helps you set the height of header, and the [`GroupPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMapFlatLevel.html#Syncfusion_SfTreeMap_iOS_SFTreeMapFlatLevel_GroupPath) value determines the header value. 

{% tabs %}

{% highlight c# %}

 SFTreeMapFlatLevel flatLevel = new SFTreeMapFlatLevel();
            flatLevel.GroupBorderColor = UIColor.Gray;
            flatLevel.GroupBorderWidth = 1;
            flatLevel.GroupBackground = UIColor.White;
            flatLevel.HeaderHeight = 20;
            flatLevel.GroupPath = (NSString)"Continent";
            flatLevel.GroupGap = 5;
            flatLevel.HeaderStyle = new SFStyle() { Color = UIColor.Black };
            flatLevel.ShowHeader = true;
            treeMap.Levels.Add(flatLevel);

{% endhighlight %} 

{% endtabs %} 

![Treemap header](TreeMap_Images/Trim.png)

## Data labels

The [`ShowLabels`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFLeafItemSetting.html#Syncfusion_SfTreeMap_iOS_SFLeafItemSetting_ShowLabels) property is used to enable or disable the labels in leaf nodes. The [`LabelPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFLeafItemSetting.html#Syncfusion_SfTreeMap_iOS_SFLeafItemSetting_LabelPath) property allows you to set values to labels.

{% tabs %}

{% highlight c# %}

            SFLeafItemSetting leafItemSetting = new SFLeafItemSetting();
            leafItemSetting.Gap = 2;
            leafItemSetting.LabelPath = (NSString)"Region";
            leafItemSetting.BorderColor = UIColor.FromRGB(169, 217, 247);
            leafItemSetting.ShowLabels = true;
            treeMap.LeafItemSettings = leafItemSetting;
 
{% endhighlight %}

{% endtabs %} 

![Providing visibility for data labels in TreeMap](TreeMap_Images/Trim.png)

### Avoid overlap in data labels

The [`OverflowMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFLeafItemSetting.html#Syncfusion_SfTreeMap_iOS_SFLeafItemSetting_OverflowMode)) property aligns data labels within leaf node boundaries using the `Trim`, `Wrap`, and `Hide` options. The default value of the `OverflowMode` property is Trim.

#### Trim

You can trim the data labels inside the leaf node boundaries using the `Trim` option.

{% tabs %}

{% highlight c# %}

   leafItemSetting.OverflowMode = LabelOverflowMode.Trim;
 
{% endhighlight %}

{% endtabs %}

![Data label trim support in Xamarin.Forms TreeMap](TreeMap_Images/Trim.png)

#### Wrap

You can wrap the data labels inside the leaf node boundaries using the `Wrap` option.

{% tabs %}

{% highlight c# %}

    leafItemSetting.OverflowMode = LabelOverflowMode.Wrap;
 
{% endhighlight %}

{% endtabs %}

![Data label wrap support in Xamarin.Forms TreeMap](TreeMap_Images/Wrap.png)

#### Hide

You can hide the data labels inside the leaf node boundaries using the `Hide` option. 

{% tabs %}

{% highlight c# %}

  leafItemSetting.OverflowMode = LabelOverflowMode.Hide;
 
{% endhighlight %}

{% endtabs %}

![Data label hide support in TreeMap](TreeMap_Images/Hide.png)

### Customize data labels

You can customize the data labels using the [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFLeafItemSetting.html#Syncfusion_SfTreeMap_iOS_SFLeafItemSetting_LabelStyle) property of LeafItemSettings. The text color and font can be customized using the [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFStyle.html#Syncfusion_SfTreeMap_iOS_SFStyle_Color) and [`Font`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFStyle.html#Syncfusion_SfTreeMap_iOS_SFStyle_Font) properties respectively.

{% tabs %}

{% highlight c# %}

          leafItemSetting.LabelStyle = new SFStyle() { Color = UIColor.Red, Font = UIFont.SystemFontOfSize(15) };
 
{% endhighlight %}

{% endtabs %}

![Customizing the data labels support in TreeMap ](TreeMap_Images/LabelStyle.png)

