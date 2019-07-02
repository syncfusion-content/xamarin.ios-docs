---
layout: post
title: Layout in Syncfusion TreeMap control for Xamarin.iOS
description: Learn how to add and customize the layout in Syncfusion TreeMap control
platform: Xamarin.iOS
control: TreeMap
documentation: ug
---

# Layout

You can decide the visual representation of nodes belonging to all the TreeMap levels using the [`LayoutType`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~LayoutType.html) property of TreeMap.

The following four different types of layouts available in TreeMap:

* Squarified
* SliceAndDiceAuto
* SliceAndDiceHorizontal
* SliceAndDiceVertical

## Squarified

The **Squarified** layout creates rectangles with best aspect ratio.

{% tabs %}  

{% highlight C# %} 
      
    treeMap.LayoutType = Com.Syncfusion.Treemap.Enums.LayoutType.Squarified;

{% endhighlight %}

{% endtabs %}  

![Squarified layout](Getting-Started_images/Squarified.png)

## SliceAndDiceAuto

The **SliceAndDiceAuto** layout creates rectangles with high aspect ratio and displays them sorted both horizontally and vertically.

{% tabs %} 

{% highlight C# %} 

   treeMap.LayoutType = Com.Syncfusion.Treemap.Enums.LayoutType.SliceAndDiceAuto;

{% endhighlight %}

{% endtabs %}  

![SliceAndDiceAuto layout](Getting-Started_images/SliceAndDiceAuto.png)

## SliceAndDiceHorizontal

The **SliceAndDiceHorizontal** layout creates rectangles with high aspect ratio and displays them sorted horizontally.

{% tabs %}  

{% highlight C# %} 

       treeMap.LayoutType = Com.Syncfusion.Treemap.Enums.LayoutType.SliceAndDiceHorizontal;

{% endhighlight %}

{% endtabs %}  

![SliceAndDiceHorizontal layout](Getting-Started_images/SliceAndDiceHorizontal.png)

## SliceAndDiceVertical

The **SliceAndDiceVertical** layout creates rectangles with high aspect ratio and displays them sorted vertically.

{% tabs %}  

{% highlight C# %} 

      treeMap.LayoutType = Com.Syncfusion.Treemap.Enums.LayoutType.SliceAndDiceVertical;

{% endhighlight %}

{% endtabs %}  

![SliceAndDiceVertical layout](Getting-Started_images/SliceAndDiceVertical.png)

The following is the complete code for squarified layout type.

{% tabs %}  

{% highlight C# %} 

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
