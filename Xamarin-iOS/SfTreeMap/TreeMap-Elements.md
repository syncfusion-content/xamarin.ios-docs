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

You can set the color value of leaf nodes using the [`LegendSettings`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~LegendSettings.html) property. This legend is appropriate only for the tree map whose leaf nodes are colored using [`RangeColorMapping`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRangeColorMapping.html).

The visibility of legend can be enabled by setting the [`ShowLegend`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFLegendSetting~ShowLegend.html) property to true.

### TreeMap legends

You can set the size of legend icons by setting the [`IconSize`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFLegendSetting~ShowLegend.html) property of `LegendSettings` in TreeMap.

### Labels for legends

You can customize the labels of the legend items using the [`LegendLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRange~LegendLabel.html) property of [`RangeColorMapping`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRangeColorMapping.html). 

{% tabs %}

{% highlight c# %}

    LegendSetting legendSettings = new LegendSetting();
    legendSettings.IconSize = new Size(15, 15);
            legendSettings.ShowLegend = true;
            legendSettings.LegendSize = new Size(700, 45);
            legendSettings.LabelStyle = new Style() { TextColor = Color.Black };
            treeMap.LegendSettings = legendSettings;

{% endhighlight %}

{% endtabs %} 

![Treemap legend](Getting-Started_images/GettingStarted.jpg)

## Header

You can set headers for each level by setting the [`ShowHeader`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMapLevel~ShowHeader.html) property of each **TreeMap** level. The [`HeaderHeight`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMapLevel~HeaderHeight.html) property helps you set the height of header, and the [`GroupPath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMapFlatLevel~GroupPath.html) value determines the header value. 

{% tabs %}

{% highlight c# %}

          TreeMapFlatLevel flatLevel = new TreeMapFlatLevel();
            flatLevel.HeaderHeight = 20;
            flatLevel.GroupPath = "Continent";
            flatLevel.GroupGap = 5;
            flatLevel.ShowHeader = true;
            flatLevel.GroupStrokeColor = Color.Gray;
            flatLevel.GroupStrokeWidth = 1;
            flatLevel.HeaderStyle = new Style() { TextColor = Color.Black };
            treeMap.Levels.Add(flatLevel);

{% endhighlight %} 

{% endtabs %} 

![Treemap header](Getting-Started_images/Trim.png)

## Data labels

The [`ShowLabels`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFLeafItemSetting~ShowLabels.html) property is used to enable or disable the labels in leaf nodes. The [`LabelPath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFLeafItemSetting~LabelPath.html) property allows you to set values to labels.

{% tabs %}

{% highlight c# %}

            LeafItemSetting leafItemSetting = new LeafItemSetting();
            leafItemSetting.ShowLabels = true;
            leafItemSetting.Gap = 2;
            leafItemSetting.LabelPath = "Country";
            treeMap.LeafItemSettings = leafItemSetting;
 
{% endhighlight %}

{% endtabs %} 

![Providing Visibility for data labels in TreeMap](Getting-Started_images/Trim.png)

### Avoid overlap in data labels

The [`OverflowMode`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFLeafItemSetting~OverflowMode.html)) property aligns data labels within leaf node boundaries using the `Trim`, `Wrap`, and `Hide` options. The default value of the `OverflowMode` property is Trim.

#### Trim

You can trim the data labels inside the leaf node boundaries using the `Trim` option.

{% tabs %}

{% highlight c# %}

   treeMap.LeafItemSettings.OverflowMode = LabelOverflowMode.Trim;
 
{% endhighlight %}

{% endtabs %}

![Data label trim support in Xamarin.Forms TreeMap](Getting-Started_images/Trim.png)

#### Wrap

You can wrap the data labels inside the leaf node boundaries using the `Wrap` option.

{% tabs %}

{% highlight c# %}

    treeMap.LeafItemSettings.OverflowMode = LabelOverflowMode.Wrap;
 
{% endhighlight %}

{% endtabs %}

![Data label wrap support in Xamarin.Forms TreeMap](Getting-Started_images/Wrap.png)

#### Hide

You can hide the data labels inside the leaf node boundaries using the `Hide` option. 

{% tabs %}

{% highlight c# %}

   treeMap.LeafItemSettings.OverflowMode = LabelOverflowMode.Hide;
 
{% endhighlight %}

{% endtabs %}

![Data label hide support in TreeMap](Getting-Started_images/Hide.png)

### Customize data labels

You can customize the data labels using the [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFLeafItemSetting~LabelStyle.html) property of LeafItemSettings. The text color and font can be customized using the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFStyle~Color.html) and [`Font`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFStyle~Font.html) properties respectively.

{% tabs %}

{% highlight c# %}

         treeMap.LeafItemSettings.LabelStyle = new Style() { TextColor = Color.Red, TextSize = 12 };
 
{% endhighlight %}

{% endtabs %}

![Customizing the data labels support in TreeMap ](Getting-Started_images/LabelCustomization.png)

