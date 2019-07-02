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

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,
{Syncfusion Installed location} \Essential Studio\17.2.0.28\lib

Add the following TreeMap assembly reference in the Xamarin.iOS project,
ios-unified\Syncfusion.SfTreeMap.iOS.dll
   
## Initializing TreeMap

Import the TreeMap namespace as shown below

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

## Populate TreeMap with data

Treemap items can be populated using the DataSource property by setting the defined view model data.
To render leaf nods for the underlying data, levels and leaf item settings must be specified.

{% tabs %}  

{% highlight c# %}

 SFTreeMap treeMap = new SFTreeMap();
            treeMap.WeightValuePath = (NSString)"Population";
            treeMap.ColorValuePath = (NSString)"Growth";

            SFLeafItemSetting leafItemSetting = new SFLeafItemSetting();
            leafItemSetting.Gap = 2;
            leafItemSetting.LabelPath = (NSString)"Country";
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

            treeMap.EnableDrilldown = true;
            treeMap.Frame = new CoreGraphics.CGRect(View.Frame.Left, View.Frame.Top + 50, View.Frame.Width, View.Frame.Height - 100);

            this.View.Add(treeMap);

{% endhighlight %}

{% endtabs %}

Below code snippet explains the underlying view model data to render tree map.

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

* TreeMap Flat Level
* TreeMap Hierarchical Level

Add the levels either flat level or hierarchical level to the [`Levels`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~Levels.html) collection in treemap.
Each level will be formed based on the property specified in the [`GroupPath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMapFlatLevel~GroupPath.html) and each rectangle size will be calculated based on the [`WeightValuePath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~WeightValuePath.html) property.

## Customizing the appearance of TreeMap by range

You can differentiate the nodes based on their values and colors using [`RangeColorMapping`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRangeColorMapping.html). You can define the color value range using the [`From`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRange~From.html) and [`To`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRange~To.html) properties in Range. The values of From and To properties depend on underlying data bound to the [`ColorValuePath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~ColorValuePath.html) property.

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

You can customize the tree map leaf nodes using [`LeafItemSettings`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~LeafItemSettings.html).

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

The color value of leaf nodes can be tracked using tree map legend. The legend support is applicable only for the TreeMap whose leaf nodes are colored using RangeColorMapping. Set the value of [`ShowLegend`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFLegendSetting~ShowLegend.html) property to “True” to make legends visible.

## Labels for legends

You can customize the labels of legend items using the [`LegendLabel`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRange~LegendLabel.html) property in RangeColorMapping. 

{% tabs %} 

{% highlight c# %}

 SFLegendSetting legendSetting = new SFLegendSetting();
            legendSetting.ShowLegend = true;
            legendSetting.Size = new CoreGraphics.CGSize(500, 45);
            treeMap.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}

The following code sample helps you reproduce the output.

{% tabs %} 

{% highlight c# %}

 SfTreeMap treeMap = new SfTreeMap(this);
            treeMap.ColorValuePath = "Growth";
            treeMap.WeightValuePath = "Population";
            treeMap.LayoutType = Com.Syncfusion.Treemap.Enums.LayoutType.Squarified;
            treeMap.ShowTooltip = true;

            LeafItemSetting leafItemSetting = new LeafItemSetting();
            leafItemSetting.ShowLabels = true;
            leafItemSetting.Gap = 2;
            leafItemSetting.LabelPath = "Country";
            treeMap.LeafItemSettings = leafItemSetting;

            TreeMapFlatLevel flatLevel = new TreeMapFlatLevel();
            flatLevel.HeaderHeight = 20;
            flatLevel.GroupPath = "Continent";
            flatLevel.GroupGap = 5;
            flatLevel.ShowHeader = true;
            flatLevel.GroupStrokeColor = Color.Gray;
            flatLevel.GroupStrokeWidth = 1;
            flatLevel.HeaderStyle = new Style() { TextColor = Color.Black };
            treeMap.Levels.Add(flatLevel);

            LegendSetting legendSettings = new LegendSetting();
            legendSettings.ShowLegend = true;
            legendSettings.LegendSize = new Size(700, 45);
            legendSettings.LabelStyle = new Style() { TextColor = Color.Black };
            treeMap.LegendSettings = legendSettings;

            RangeColorMapping rangeColorMapping = new RangeColorMapping();

            Range range1 = new Range();
            range1.From = 0;
            range1.To = 1;
            range1.Color = Color.ParseColor("#77D8D8");
            range1.LegendLabel = "1 % Growth";

            Range range2 = new Range();
            range2.From = 0;
            range2.To = 2;
            range2.Color = Color.ParseColor("#AED960");
            range2.LegendLabel = "2 % Growth";

            Range range3 = new Range();
            range3.From = 0;
            range3.To = 3;
            range3.Color = Color.ParseColor("#FFAF51");
            range3.LegendLabel = "3 % Growth";

            Range range4 = new Range();
            range4.From = 0;
            range4.To = 4;
            range4.Color = Color.ParseColor("#F3D240");
            range4.LegendLabel = "4 % Growth";

            rangeColorMapping.Ranges.Add(range1);
            rangeColorMapping.Ranges.Add(range2);
            rangeColorMapping.Ranges.Add(range3);
            rangeColorMapping.Ranges.Add(range4);

            treeMap.LeafItemColorMapping = rangeColorMapping;
            treeMap.DataSource = GetDataSource();

            SetContentView(treeMap);

{% endhighlight %}

{% endtabs %}

You can find the complete getting-started sample in the following link: [Getting-started sample]().

The following screenshot illustrates the output of SfTreeMap.

![Output of SfTreeMap](Getting-Started_images/GettingStarted.jpg)
