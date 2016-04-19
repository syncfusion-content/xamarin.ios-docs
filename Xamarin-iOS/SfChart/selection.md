---
layout: post
title: Data Point Selection | SFChart | Xamarin.iOS | Syncfusion
description: How to select the data point in Essential SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Data Point Selection

You can select a data point by tapping on it. To enable the selection feature, set `EnableDataPointSelection` property as `True` for series. 

{% highlight c# %}

SFColumnSeries series           = new SFColumnSeries ();

series.EnableDataPointSelection = true; 

{% endhighlight %}


![](selection_images/selection_img1.png)

Following properties are used to configure the selection feature,

* `SelectedDataPointIndex` – used to programmatically select a data point
* `SelectedDataPointColor` – used to change the selected data point color

{% highlight c# %}

SFColumnSeries series           = new SFColumnSeries ();

series.EnableDataPointSelection = true;

series.SelectedDataPointIndex   = 2;

series.SelectedDataPointColor   = UIColor.Red; 

{% endhighlight %}


![](selection_images/selection_img2.png)


N> For Accumulation series like pie, doughnut, pyramid and funnel, when you select a data point, the corresponding legend item also will be selected.

## Delegates


We need to implement delegate to deal with the user interactions in chart for data point selection. In order to do this,you need to adopt the `SFChartDelegate` protocol through the class extension as shown below.

{% highlight c# %}

public override void ViewDidLoad ()
{
    chart.Delegate = new ChartDelegate ();
}

public class ChartDelegate : SFChartDelegate
{
    public override void DidDataPointSelect (SFChart chart, SFChartSelectionInfo info)
    {

    }
}

{% endhighlight %}



**WillDataPointSelect**

This delegate is called when the series datapoint selection operation has been started and it returns the following values.

* `SFChartSelectionChangingInfo` – used to get the selection state.


**DidDataPointSelect**

This delegate is called when the series datapoint selection operation has been finished and it returns the following values.

* `SFChartSelectionInfo` – used to get the selection state.