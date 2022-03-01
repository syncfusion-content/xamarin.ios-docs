---
layout: post
title: Getting Started with Syncfusion TreeMap control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion TreeMap control for Xamarin.iOS platform.
platform: Xamarin.iOS
control: SfTreeMap
documentation: ug
---

# Getting Started

This section explains the steps required to configure the TreeMap control and provides a walk-through on some of the customization features available in the TreeMap control.

## Adding SfTreeMap reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders.

{Syncfusion Installed location} \Essential Studio\17.2.0.28\lib

Add the following TreeMap assembly reference in the Xamarin.iOS project :ios-unified\Syncfusion.SfTreeMap.iOS.dll
   
## Initializing TreeMap

Import the TreeMap namespace as shown in the following code sample.

{% tabs %}  

{% highlight c# %}

using Syncfusion.SfTreeMap.iOS;

{% endhighlight %}

{% endtabs %}  

You can initialize the SfTreeMap control with the required optimal name by using the included namespace.

{% tabs %}  

{% highlight c# %}

public override void ViewDidLoad()
        {
            base.ViewDidLoad();
            SfSFTreeMap treeMap = new SFTreeMap();
            this.View.Add(treeMap);
        }

{% endhighlight %}

{% endtabs %}  

## Populating TreeMap with data

Treemap items can be populated using the DataSource property by setting the defined view model data. To render leaf nods for the underlying data, levels and leaf item settings must be specified.

{% tabs %}  

{% highlight c# %}

 SFTreeMap treeMap = new SFTreeMap();
            treeMap.WeightValuePath = (NSString)"Population";
            treeMap.ColorValuePath = (NSString)"Growth";

            SFLeafItemSetting leafItemSetting = new SFLeafItemSetting();
            leafItemSetting.Gap = 2;
            leafItemSetting.LabelPath = (NSString)"Region";
            leafItemSetting.BorderColor = UIColor.FromRGB(169, 217, 247);
            leafItemSetting.ShowLabels = true;
            treeMap.LeafItemSettings = leafItemSetting;

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

            GetPopulationData();
            treeMap.DataSource = PopulationDetails;
            treeMap.ShowTooltip = true;

            treeMap.Frame = new CoreGraphics.CGRect(View.Frame.Left, View.Frame.Top + 50, View.Frame.Width, View.Frame.Height - 100);

            this.View.Add(treeMap);

{% endhighlight %}

{% endtabs %}

The following code snippet explains the underlying view model data to render TreeMap.

{% tabs %} 

{% highlight c# %}

void GetPopulationData()
        {
            NSMutableArray array = new NSMutableArray();
            array.Add(getDictionary("Asia", "Indonesia", 3, 237641326));
            array.Add(getDictionary("Asia", "Russia", 2, 152518015));
            array.Add(getDictionary("North America", "United States", 4, 315645000));
            array.Add(getDictionary("North America", "Mexico", 2, 112336538));
            array.Add(getDictionary("North America", "Canada", 1, 35056064));
            array.Add(getDictionary("South America", "Colombia", 1, 47000000));
            array.Add(getDictionary("South America", "Brazil", 3, 193946886));
            array.Add(getDictionary("Africa", "Nigeria", 2, 170901000));
            array.Add(getDictionary("Africa", "Egypt", 1, 83661000));
            array.Add(getDictionary("Europe", "Germany", 1, 81993000));
            array.Add(getDictionary("Europe", "France", 1, 65605000));
            array.Add(getDictionary("Europe", "UK", 1, 63181775));
            PopulationDetails = array;
        }

NSDictionary getDictionary(string continent, string region, double growth, double population)
        {

            object[] objects = new object[4];
            object[] keys = new object[4];
            keys.SetValue("Continent", 0);
            keys.SetValue("Region", 1);
            keys.SetValue("Growth", 2);
            keys.SetValue("Population", 3);
            objects.SetValue((NSString)continent, 0);
            objects.SetValue((NSString)region, 1);
            objects.SetValue(growth, 2);
            objects.SetValue(population, 3);
            return NSDictionary.FromObjectsAndKeys(objects, keys);
        }

        public NSMutableArray PopulationDetails
        {
            get;
            set;
        }

{% endhighlight %}

{% endtabs %}  

## Grouping TreeMap items using levels

You can group TreeMapItems using the following two types of levels:

* TreeMap flat level
* TreeMap hierarchical level

Add either flat level or hierarchical level to the [`Levels`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMap.html#Syncfusion_SfTreeMap_iOS_SFTreeMap_Levels) collection in TreeMap.
Each level will be formed based on the property specified in the [`GroupPath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMapFlatLevel.html#Syncfusion_SfTreeMap_iOS_SFTreeMapFlatLevel_GroupPath), and each rectangle size will be calculated based on the [`WeightValuePath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMap.html#Syncfusion_SfTreeMap_iOS_SFTreeMap_WeightValuePath) property.

## Customizing the appearance of TreeMap by range

You can differentiate the nodes based on their values and colors using [`RangeColorMapping`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFRangeColorMapping.html). You can define the color value range using the [`From`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFRange.html#Syncfusion_SfTreeMap_iOS_SFRange_From) and [`To`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFRange.html#Syncfusion_SfTreeMap_iOS_SFRange_To) properties in Range. The values of the From and To properties depend on underlying data bound to the [`ColorValuePath`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMap.html#Syncfusion_SfTreeMap_iOS_SFTreeMap_ColorValuePath) property.

{% tabs %} 

{% highlight c# %}

SFRangeColorMapping colorMapping = new SFRangeColorMapping();

            SFRange range1 = new SFRange();
            range1.LegendLabel = (NSString)"1 % Growth";
            range1.From = 0;
            range1.To = 1;
            range1.Color = UIColor.FromRGB(119, 216, 216);

            SFRange range2 = new SFRange();
            range2.LegendLabel = (NSString)"2 % Growth";
            range2.From = 0;
            range2.To = 2;
            range2.Color = UIColor.FromRGB(174, 217, 96);

            SFRange range3 = new SFRange();
            range3.LegendLabel = (NSString)"3 % Growth";
            range3.From = 0;
            range3.To = 3;
            range3.Color = UIColor.FromRGB(255, 175, 81);

            SFRange range4 = new SFRange();
            range4.LegendLabel = (NSString)"4 % Growth";
            range4.From = 0;
            range4.To = 4;
            range4.Color = UIColor.FromRGB(243, 210, 64);

            colorMapping.Ranges.Add(range1);
            colorMapping.Ranges.Add(range2);
            colorMapping.Ranges.Add(range3);
            colorMapping.Ranges.Add(range4);

            treeMap.LeafItemColorMapping = colorMapping;

{% endhighlight %}

{% endtabs %}  

## LeafItemSetting

You can customize the leaf nodes of  TreeMap using [`LeafItemSettings`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFTreeMap.html#Syncfusion_SfTreeMap_iOS_SFTreeMap_LeafItemSettings).

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

## Enabling legends

The color value of leaf nodes can be tracked using TreeMap legend. The legend support is applicable only for the TreeMap whose leaf nodes are colored using RangeColorMapping. Set the value of [`ShowLegend`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFLegendSetting.html#Syncfusion_SfTreeMap_iOS_SFLegendSetting_ShowLegend) property to “True” to make legends visible.

## Labels for legends

You can customize the labels of legend items using the [`LegendLabel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfTreeMap.iOS.SFRange.html#Syncfusion_SfTreeMap_iOS_SFRange_LegendLabel) property in RangeColorMapping. 

{% tabs %} 

{% highlight c# %}

 SFLegendSetting legendSetting = new SFLegendSetting();
            legendSetting.ShowLegend = true;
            legendSetting.Size = new CoreGraphics.CGSize(500, 45);
            treeMap.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}

The following code sample is used to reproduce the output.

{% tabs %} 

{% highlight c# %}

 SFTreeMap treeMap = new SFTreeMap();
            treeMap.WeightValuePath = (NSString)"Population";
            treeMap.ColorValuePath = (NSString)"Growth";

            SFLeafItemSetting leafItemSetting = new SFLeafItemSetting();
            leafItemSetting.Gap = 2;
            leafItemSetting.LabelPath = (NSString)"Region";
            leafItemSetting.BorderColor = UIColor.FromRGB(169, 217, 247);
            leafItemSetting.ShowLabels = true;
            treeMap.LeafItemSettings = leafItemSetting;

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

            SFLegendSetting legendSetting = new SFLegendSetting();
            legendSetting.ShowLegend = true;
            legendSetting.Size = new CoreGraphics.CGSize(500, 45);
            treeMap.LegendSettings = legendSetting;

            SFRangeColorMapping colorMapping = new SFRangeColorMapping();

            SFRange range1 = new SFRange();
            range1.LegendLabel = (NSString)"1 % Growth";
            range1.From = 0;
            range1.To = 1;
            range1.Color = UIColor.FromRGB(119, 216, 216);

            SFRange range2 = new SFRange();
            range2.LegendLabel = (NSString)"2 % Growth";
            range2.From = 0;
            range2.To = 2;
            range2.Color = UIColor.FromRGB(174, 217, 96);

            SFRange range3 = new SFRange();
            range3.LegendLabel = (NSString)"3 % Growth";
            range3.From = 0;
            range3.To = 3;
            range3.Color = UIColor.FromRGB(255, 175, 81);

            SFRange range4 = new SFRange();
            range4.LegendLabel = (NSString)"4 % Growth";
            range4.From = 0;
            range4.To = 4;
            range4.Color = UIColor.FromRGB(243, 210, 64);

            colorMapping.Ranges.Add(range1);
            colorMapping.Ranges.Add(range2);
            colorMapping.Ranges.Add(range3);
            colorMapping.Ranges.Add(range4);

            treeMap.LeafItemColorMapping = colorMapping;

            GetPopulationData();
            treeMap.DataSource = PopulationDetails;
            treeMap.ShowTooltip = true;
            treeMap.Frame = new CoreGraphics.CGRect(View.Frame.Left, View.Frame.Top + 50, View.Frame.Width, View.Frame.Height - 100);

            this.View.AddSubview(treeMap);

{% endhighlight %}

{% endtabs %}

You can find the complete getting-started sample in the following link: [Getting-started](https://github.com/SyncfusionExamples/TreeMap_GettingStarted_iOS).

The following screenshot illustrates the output of SfTreeMap.

![Output of SfTreeMap](TreeMap_Images/GettingStarted.png)
