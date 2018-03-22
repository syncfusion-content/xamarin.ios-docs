---
layout: post
title: Multiple series and combination of series | SFChart | Xamarin.iOS | Syncfusion
description: How to add multiple series and combination series in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Chart Series

## Multiple Series

You can add multiple series to [`Series`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Series.html) property of [`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html) class.

{% highlight c# %}

SFChart chart = new SFChart();
...

SFColumnSeries columnSeries = new SFColumnSeries() { 
    
    ItemsSource = Data, 
    XBindingPath = "Country", 
    YBindingPath = "Value" 

};

SFColumnSeries columnSeries1 = new SFColumnSeries() { 

    ItemsSource = Data1, 
    XBindingPath = "Country", 
    YBindingPath = "Value" 
    
};

SFColumnSeries columnSeries2 = new SFColumnSeries() { 

    ItemsSource = Data2, 
    XBindingPath = "Country", 
    YBindingPath = "Value" 
    
};

chart.Series.Add(columnSeries);

chart.Series.Add(columnSeries1);

chart.Series.Add(columnSeries2);
{% endhighlight %}


![](ChartSeries_images/MultipleSeries.png)

## Combination Series

[`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html) allows you to render the combination of different types of series.

{% highlight c# %}

SFChart chart = new SFChart();

...

SFColumnSeries columnSeries = new SFColumnSeries() { 
    
    ItemsSource = Data, 
    XBindingPath = "Month",
    YBindingPath = "Value" 
    
};

SFLineSeries lineSeries = new SFLineSeries() { 
    
    ItemsSource = Data1, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
    
}; 

chart.Series.Add(columnSeries);

chart.Series.Add(lineSeries);
{% endhighlight %}


![](ChartSeries_images/CombinationSeries.png)

**Limitation of Combination Chart**

* Bar, StackingBar, and StackingBar100 cannot be combined with the other Cartesian type series
* Cartesian type series cannot be combined with accumulation series (pie, doughnut, funnel, and pyramid) and radar & polar series

When the combination of Cartesian and accumulation series types are added to the [`Series`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~Series.html) property, the series which are similar to the first series will be rendered and other series will be ignored. Following code snippet illustrates this.

{% highlight c# %}

SFChart chart = new SFChart();
...

SFLineSeries lineSeries = new SFLineSeries() { 

    ItemsSource = Data, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
    
};

SFPieSeries pieSeries = new SFPieSeries() { 

    ItemsSource = Data1, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
    
};

chart.Series.Add(lineSeries);

chart.Series.Add(pieSeries);
{% endhighlight %}

![](ChartSeries_images/Limitation.png)

## Animation

[`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html) provides animation support for series. Series will be animated on loading data points and whenever the items source changes. Animation can be enabled by setting the [`EnableAnimation`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~EnableAnimation.html) property as true and the animation duration can be handled by the [`AnimationDuration`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~AnimationDuration.html) property, which are available in [`SFSeries`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries.html).

{% highlight c# %}

SFColumnSeries series       = new SFColumnSeries ();
series.EnableAnimation      = true;
series.AnimationDuration    = 0.8;

{% endhighlight %}

# Vertical Chart

Vertical chart is used to show the CartesianSeries vertically which helps to view the data in different
perceptive using [`IsTransposed`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFCartesianSeries~IsTransposed.html) property. 


{% highlight c# %}

SFLineSeries series   = new SFLineSeries ();

series.IsTransposed   = true;

{% endhighlight %}

![](ChartSeries_images/VerticalChart.png)