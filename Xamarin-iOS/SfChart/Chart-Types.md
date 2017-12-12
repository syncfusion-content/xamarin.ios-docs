---
layout: post
title: Chart Types | SFChart | Xamarin.iOS | Syncfusion
description: What are all the different types of chart and it's properties in SFChart.
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Chart Types

## Line Chart

To render a line chart, create an instance of SFLineSeries and add to the Series collection property of `SFChart`. You can use the following properties to customize the appearance.

* `Color` – used to change the color of the line
* `LineWidth` – used to change the width of the line

{% highlight c# %}

SFChart chart = new SFChart();
...

SFLineSeries lineSeries = new SFLineSeries()
{
    ItemsSource = Data,
    XBindingPath = "Year",
    YBindingPath = "Value"
};
chart.Series.Add(lineSeries);

{% endhighlight %}


![](ChartTypes_images/Line.png)

### Dashed Lines

`Dashes` property of the `SFLineSeries` is used to render line series with dashes.

{% highlight c# %}
SFLineSeries series = new SFLineSeries ();
series.ItemsSource = Data; 
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
  
NSObject[] dashes       = new NSObject[2];
dashes [0]              = (NSNumber)2;
dashes [1]              = (NSNumber)3;
series.Dashes           = NSArray.FromObjects (dashes);
chart.Series.Add(series);
{% endhighlight %}

## Area Chart

To render an area chart, create an instance of `SFAreaSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFAreaSeries areaSeries = new SFAreaSeries()
{
    ItemsSource = Data,
    XBindingPath = "Year",
    YBindingPath = "Value"
};
chart.Series.Add(areaSeries);
{% endhighlight %}

![](ChartTypes_images/Area.png)

## Spline Area Chart

To render a spline area chart, create an instance of `SFSplineAreaSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the spline area appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFSplineAreaSeries splineAreaSeries = new SFSplineAreaSeries()
{
    ItemsSource = Data,
    XBindingPath = "Year",
    YBindingPath = "Value"
};
chart.Series.Add(splineAreaSeries);

{% endhighlight %}


![](ChartTypes_images/SplineArea.png)



## Stacked Area Chart

To render a stacked area chart, create an instance of `SFStackingAreaSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the stacked area appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFStackingAreaSeries stackingAreaSeries1 = new SFStackingAreaSeries() 
{ 
    ItemsSource = Data1, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};

SFStackingAreaSeries stackingAreaSeries2 = new SFStackingAreaSeries() 
{ 
    ItemsSource = Data2, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};

SFStackingAreaSeries stackingAreaSeries3 = new SFStackingAreaSeries() 
{ 
    ItemsSource = Data3, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};

chart.Series.Add(stackingAreaSeries1);
chart.Series.Add(stackingAreaSeries2);
chart.Series.Add(stackingAreaSeries3);

{% endhighlight %}

![](ChartTypes_images/StackedArea.png)

## 100% Stacked Area Chart

To render a 100% stacked area chart, create an instance of `SFStackingArea100Series` and add to the Series collection property of `SFChart`. You can use the following properties to customize the 100% stacked area appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFStackingArea100Series stackingAreaSeries1 = new SFStackingArea100Series() 
{ 
    ItemsSource = Data1, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};

SFStackingArea100Series stackingAreaSeries2 = new SFStackingArea100Series() 
{ 
    ItemsSource = Data2, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};

SFStackingArea100Series stackingAreaSeries3 = new SFStackingArea100Series() 
{ 
    ItemsSource = Data3, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};

chart.Series.Add(stackingAreaSeries1);
chart.Series.Add(stackingAreaSeries2);
chart.Series.Add(stackingAreaSeries3);
{% endhighlight %}

![](ChartTypes_images/StackedArea100.png)

## Column Chart

To render a column chart, create an instance of `SFColumnSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFColumnSeries columnSeries = new SFColumnSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Country", 
    YBindingPath = "Value" 
};
chart.Series.Add(columnSeries);
{% endhighlight %}


![](ChartTypes_images/Column.png)

## Range Column Chart

To render a range column chart, create an instance of `SFRangeColumnSeries` and add to the Series collection property of `SFChart`. 

Since the `SFRangeColumnSeries` requires two Y values for a point, your data should contain high and low values. High and low value specifies the maximum and minimum range of the point. 

{% highlight c# %}

SFChart chart = new SFChart();
...
   
SFRangeColumnSeries rangeColumnSeries = new SFRangeColumnSeries() 
{ 
    ItemsSource = Data,
    XBindingPath = "Month", 
    High = "Value1",
    Low = "Value2" 
};
chart.Series.Add(rangeColumnSeries);
{% endhighlight %}


Following properties are used to customize the range column segment appearance,

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series

![](ChartTypes_images/RangeColumn.png)

## Stacked Column Chart

To render a stacked column chart, create an instance of `SFStackingColumnSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the stacked column segment appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series

{% highlight c# %}

SFChart chart = new SFChart();
...

SFStackingColumnSeries stackingColumnSeries1 = new SFStackingColumnSeries() 
{ 
    ItemsSource = Data1, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

SFStackingColumnSeries stackingColumnSeries2 = new SFStackingColumnSeries() 
{ 
    ItemsSource = Data2, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

SFStackingColumnSeries stackingColumnSeries3 = new SFStackingColumnSeries() 
{ 
    ItemsSource = Data3, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

chart.Series.Add(stackingColumnSeries1);
chart.Series.Add(stackingColumnSeries2);
chart.Series.Add(stackingColumnSeries3);
{% endhighlight %}

![](ChartTypes_images/StackedColumn.png)

## 100% Stacked Column Chart

To render a 100% stacked column chart, create an instance of `SFStackingColumn100Series` and add to the Series collection property of `SFChart`. You can use the following properties to customize the series appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFStackingColumn100Series stackingColumn100Series1 = new SFStackingColumn100Series() 
{ 
    ItemsSource = Data1, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

SFStackingColumn100Series stackingColumn100Series2 = new SFStackingColumn100Series() 
{ 
    ItemsSource = Data2, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

SFStackingColumn100Series stackingColumn100Series3 = new SFStackingColumn100Series() 
{ 
    ItemsSource = Data3, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

chart.Series.Add(stackingColumn100Series1);
chart.Series.Add(stackingColumn100Series2);
chart.Series.Add(stackingColumn100Series3);

{% endhighlight %}


![](ChartTypes_images/StackedColumn100.png)

## Bar Chart

To render a bar chart, create an instance of `SFBarSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the bar segment appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFBarSeries barSeries = new SFBarSeries () 
{ 
    ItemsSource = Data, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};
chart.Series.Add(barSeries);
{% endhighlight %}


![](ChartTypes_images/Bar.png)

## Stacked Bar Chart

To render a stacked bar chart, create an instance of `SFStackingBarSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the stacked bar segment appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFStackingBarSeries stackingBarSeries1 = new SFStackingBarSeries() 
{ 
    ItemsSource = Data1, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

SFStackingBarSeries stackingBarSeries2 = new SFStackingBarSeries() 
{ 
    ItemsSource = Data2, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

SFStackingBarSeries stackingBarSeries3 = new SFStackingBarSeries() 
{ 
    ItemsSource = Data3, 
    XBindingPath = "Month", 
    YBindingPath = "Value" 
};

chart.Series.Add(stackingBarSeries1);
chart.Series.Add(stackingBarSeries2);
chart.Series.Add(stackingBarSeries3);

{% endhighlight %}


![](ChartTypes_images/StackedBar.png)

## 100% Stacked Bar Chart

To render a 100% stacked bar chart, create an instance of `SFStackingBar100Series` and add to the Series collection property of `SFChart`. You can use the following properties to customize the series appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFStackingBar100Series stackingBar100Series1 = new SFStackingBar100Series() 
{ 
    ItemsSource = Data1, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};

SFStackingBar100Series stackingBar100Series2 = new SFStackingBar100Series() 
{ 
    ItemsSource = Data2, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};

SFStackingBar100Series stackingBar100Series3 = new SFStackingBar100Series() 
{ 
    ItemsSource = Data3, 
    XBindingPath = "Year", 
    YBindingPath = "Value"  
};

chart.Series.Add(stackingBar100Series1);
chart.Series.Add(stackingBar100Series2);
chart.Series.Add(stackingBar100Series3);
{% endhighlight %}

![](ChartTypes_images/StackedBar100.png)

## Spline Chart

To render a spline chart, create an instance of `SFSplineSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the spline segment appearance.

* `Color` – used to change the color of the series
* `LineWidth` – used to change the line width of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFSplineSeries splineSeries = new SFSplineSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Month", 
    YBindingPath = "Value"  
};
chart.Series.Add(splineSeries);
{% endhighlight %}


![](ChartTypes_images/Spline.png)

## StepLine Chart

To render a step line chart, create an instance of `SFStepLineSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the appearance.

* `Color` – used to change the color of the line
* `LineWidth` – used to change the line width of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFStepLineSeries stepLine = new SFStepLineSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Month", 
    YBindingPath = "Value"
};
chart.Series.Add(stepLine);
{% endhighlight %}


![](ChartTypes_images/StepLine.png)

## Fast Line Chart

`SFFastLineSeries` is a line chart, but it loads faster than `SFLineSeries`. You can use this when there are large number of points to be loaded in chart. To render a fast line chart, create an instance of `SFFastLineSeries` and add to the Series collection property of SFChart. You can use the following properties to customize the fast line segment appearance.

* `Color` – used to change the color of the series
* `LineWidth` – used to change the line width of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFFastLineSeries fastLineSeries = new SFFastLineSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "XValue", 
    YBindingPath = "YValue"  
};
chart.Series.Add(fastLineSeries);
{% endhighlight %}

![](ChartTypes_images/FastLine.png)

### Dashed Lines

`Dashes` property of the `SFFastLineSeries` is used to render fast line series with dashes.

{% highlight c# %}
SFFastLineSeries series = new SFFastLineSeries ();
series.ItemsSource = Data; 
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
  
NSObject[] dashes       = new NSObject[2];
dashes [0]              = (NSNumber)2;
dashes [1]              = (NSNumber)3;
series.Dashes           = NSArray.FromObjects (dashes);
chart.Series.Add(series);
{% endhighlight %}

![](ChartTypes_images/DashedLines.png)

## Bubble Chart

To render a bubble chart, create an instance of `SFBubbleSeries` and add to the Series collection property of `SFChart`. 

Bubble chart requires 3 fields (X, Y and Size) to plot a point. Here **Size** is used to specify the size of each bubble segment. 

{% highlight c# %}

SFChart chart = new SFChart();
...

SFBubbleSeries bubbleSeries = new SFBubbleSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "XValue", 
    YBindingPath = "YValue", 
    Size = "Size” 
};
chart.Series.Add(bubbleSeries);
{% endhighlight %}

Following properties are used to customize the bubble segment appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series
* `MinimumRadius` – used to change the minimum size of the series
* `MaximumRadius` – used to change the maximum size of the series

![](ChartTypes_images/Bubble.png)

## Scatter Chart	

To render a scatter chart, create an instance of `SFScatterSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the scatter segment appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series
* `ScatterWidth` – used to change the width of the series
* `ScatterHeight` – used to change the height of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFScatterSeries scatterSeries = new SFScatterSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "XValue", 
    YBindingPath = "YValue"
};
chart.Series.Add(scatterSeries);
{% endhighlight %}

![](ChartTypes_images/Scatter.png)

## OHLC Chart

To render an OHLC chart, create an instance of `SFOHLCSeries` and add to the Series collection property of `SFChart`.

OHLC chart requires five values (X, Open, High, Low and Close) to plot a point. 

{% highlight c# %}

SFChart chart = new SFChart();
...

SFOHLCSeries hiLoOpenCloseSeries = new SFOHLCSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Year", 
    Open = "Value1", 
    High = "Value2", 
    Low = "Value3", 
    Close = "Value4" 
};
chart.Series.Add(hiLoOpenCloseSeries);

{% endhighlight %}

You can use the following properties to customize the HiLoOpenCloseSeries segment appearance.

* `Color` – used to change the color of the series
* `LineWidth` – used to change the border width of the series

![](ChartTypes_images/OHLC.png)

### Bull and Bear Color	

In OHLC chart, `BullFillColor` property is used to specify a fill color for the segments that indicates an increase in stock price in the measured time interval and `BearFillColor` property is used to specify a fill color for the segments that indicates a decrease in stock price in the measured time interval.

{% highlight c# %}

SFChart chart = new SFChart();
...

SFOHLCSeries hiLoOpenCloseSeries = new SFOHLCSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Year", 
    Open = "Value1", 
    High = "Value2", 
    Low = "Value3", 
    Close = "Value4"
    BearFillColor = UIColor.Blue,
    BullFillColor = UIColor.Purple 
};
chart.Series.Add(hiLoOpenCloseSeries);

{% endhighlight %}

![](ChartTypes_images/OHLC1.png)

## Candle Chart

To render a candle chart, create an instance of `SFCandleSeries` and add to the Series collection property of `SFChart`.

Candle chart requires five values (X, Open, High, Low and Close) to plot a point. 

{% highlight c# %}

SFChart chart = new SFChart();
...

SFCandleSeries candleSeries = new SFCandleSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Year", 
    Open = "Value1", 
    High = "Value2", 
    Low = "Value3", 
    Close = "Value4" 
};
chart.Series.Add(candleSeries);

{% endhighlight %}

You can use the following properties to customize the candle segment appearance.

* `Color`       – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series

![](ChartTypes_images/Candle.png)

### Bull and Bear Color

In Candle chart, `BullFillColor` property is used to specify a fill color for the segments that indicates an
increase in stock price in the measured time interval and `BearFillColor` property is used to specify a fill color
for the segments that indicates a decrease in stock price in the measured time interval.



{% highlight c# %}

SFCandleSeries candleSeries = new SFCandleSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Year", 
    Open = "Value1", 
    High = "Value2", 
    Low = "Value3", 
    Close = "Value4"
    BearFillColor = UIColor.Blue,
    BullFillColor = UIColor.Purple 
};
chart.Series.Add(candleSeries);
{% endhighlight %}


![](ChartTypes_images/Candle1.png)

## Radar Chart

To render a radar chart, create an instance of `SFRadarSeries` and add to the Series collection property of `SFChart`.

### Draw type

`DrawType` property is used to specify the radar series rendering type. Following are the two options you can set to this property,

* `Line` – data points are visualized as line.
* `Area` – data points are visualized as area.

{% highlight c# %}
SFRadarSeries radar = new SFRadarSeries ();
radar.ItemsSource = viewModel.RadarData;
radar.XBindingPath = "Name";
radar.YBindingPath = "Value";
radar.DrawType = SFChartPolarRadarSeriesDrawType.Line;
{% endhighlight %}

![](ChartTypes_images/Radar.png)

### Customize the appearance

You can use the following properties to customize the appearance.

* `Color` – used to change the color of the series.
* `BorderWidth` – used to change the border width of the series.
* `BorderColor` – used to change the border color of the series when draw types is set to area
* `Dashes` – used to render line with dashes when draw type is set to line.

{% highlight c# %}
SFRadarSeries radarSeries   = new SFRadarSeries();
radarSeries.Color           = UIColor.Cyan;
radarSeries.BorderWidth     = 3;
radarSeries.BorderColor     = UIColor.Blue; 

{% endhighlight %}


![](ChartTypes_images/RadarCustomization.png)

### Closed

`Closed` property is used to determine, whether to connect the first and last data point of the series. By default, the property is set to `true`.

{% highlight c# %}
SFRadarSeries radarSeries   = new SFRadarSeries();
radarSeries.Closed          = false;

{% endhighlight %}

![](ChartTypes_images/RadarClosed.png)

### Radar Start Angle for primary axis

The start position of the radar series can be set by using [`PolarAngle`](http://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis~PolarAngle.html) property of axis. Default value of [`PolarAngle`](http://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis~PolarAngle.html) property is `Rotate270`. [`PolarAngle`](http://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis~PolarAngle.html) property can be set for primary axis, secondary axis, or both axes.

{% highlight c# %}

chart.PrimaryAxis = new SFCategoryAxis()
{
    PolarAngle = ChartPolarAngle.Rotate0
};

chart.SecondaryAxis = new SFNumericalAxis();

{% endhighlight %}

![](ChartTypes_images/radarangle_img1.png)

### Radar Start Angle for secondary axis

{% highlight c# %}

chart.PrimaryAxis = new SFCategoryAxis();

chart.SecondaryAxis = new SFNumericalAxis()
{
    PolarAngle = ChartPolarAngle.Rotate0
};

{% endhighlight %}

![](ChartTypes_images/radarangle_img2.png)

### Radar Start Angle for both axis

{% highlight c# %}

chart.PrimaryAxis  = new SFCategoryAxis()
{ 
    PolarAngle = ChartPolarAngle.Rotate0 
};

chart.SecondaryAxis =  new SFNumericalAxis() 
{ 
    PolarAngle = ChartPolarAngle.Rotate0 
}; 

{% endhighlight %}

![](ChartTypes_images/radarangle_img3.png)

## Polar Chart

To render a polar chart, create an instance of `SFPolarSeries` and add to the Series collection property of `SFChart`. 

### Draw type

`DrawType` property is used to specify the polar series rendering type. Following are the two options you can set to this property,

* `Line` – data points are visualized as line.
* `Area` – data points are visualized as area.

{% highlight c# %}
SFPolarSeries polarSeries        = new SFPolarSeries();
polarSeries.DrawType             = SFChartPolarRadarSeriesDrawType.Line;

{% endhighlight %}


![](ChartTypes_images/Polar.png)

### Customize the appearance

You can use the following properties to customize the appearance.

* `Color` – used to change the color of the series.
* `BorderWidth` – used to change the border width of the series.
* `BorderColor` – used to change the border color of the series when draw types is set to area
* `Dashes` – used to render line with dashes when draw type is set to line.

{% highlight c# %}
SFPolarSeries polarSeries        = new SFPolarSeries();
polarSeries.Color                = UIColor.Cyan;
polarSeries.BorderWidth          = 3;
polarSeries.BorderColor          = UIColor.Blue; 

{% endhighlight %}


![](ChartTypes_images/PolarCustomization.png)

### Closed

`Closed` property is used to determine, whether to connect the first and last data point of the series. By default, the property is set to `true`.

{% highlight c# %}
SFPolarSeries polarSeries      = new SFPolarSeries();
polarSeries.Closed             = false;

{% endhighlight %}


![](ChartTypes_images/PolarClosed.png)

### Polar start angle for primary axis

The start position of the polar series can be set by using [`PolarAngle`](http://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis~PolarAngle.html) property of axis. Default value of [`PolarAngle`](http://help.syncfusion.com/cr/cref_files/xamarin-iOS/sfchart/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFAxis~PolarAngle.html) property is `Rotate270`. PolarAngle property can be set for primary axis, secondary axis, or both axes.

{% highlight c# %}

chart.PrimaryAxis = new SFCategoryAxis()
{
    PolarAngle = ChartPolarAngle.Rotate0
};

chart.SecondaryAxis = new SFNumericalAxis();

{% endhighlight %}

![](ChartTypes_images/polarangle_img1.png)

### Polar start angle for secondary axis

{% highlight c# %}

chart.PrimaryAxis = new SFCategoryAxis();

chart.SecondaryAxis = new SFNumericalAxis()
{
    PolarAngle = ChartPolarAngle.Rotate0
};

{% endhighlight %}

![](ChartTypes_images/polarangle_img2.png)

### Polar start angle for both axis

{% highlight c# %}

chart.PrimaryAxis  = new SFCategoryAxis()
{ 
    PolarAngle = ChartPolarAngle.Rotate0 
};

chart.SecondaryAxis =  new SFNumericalAxis() 
{ 
    PolarAngle = ChartPolarAngle.Rotate0 
}; 

{% endhighlight %}

![](ChartTypes_images/polarangle_img3.png)

## Pie Chart

To render a pie chart, create an instance of `SFPieSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the pie segment appearance.

* `Color`       – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}
SFChart chart = new SFChart();
...

SFPieSeries pieSeries = new SFPieSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Expense", 
    YBindingPath = "Value",
    CircularCoefficient = 0.5 
};
chart.Series.Add(pieSeries);
{% endhighlight %}

![](ChartTypes_images/PieCircularCoefficient.png)

### Exploding a pie segment

You can explode a pie segment using `ExplodeIndex` property and specify the explode radius using `ExplodeRadius` property of `SFPieSeries`.


{% highlight c# %}

SFPieSeries series  = new SFPieSeries ();
series.ExplodeIndex = 1;  
{% endhighlight %}

![](ChartTypes_images/PieExplodeIndex.png)

### Exploding all the segments

Using `ExplodeAll` property of `SFPieSeries`, you can explode all the pie segments.


{% highlight c# %}

SFPieSeries series = new SFPieSeries ();
series.ExplodeAll  = true;      
{% endhighlight %}

![](ChartTypes_images/PieExplodeAll.png)

### Sector of Pie

`SFChart` allows you to render all the data points/segments in semi-pie, quarter-pie or in any sector using `StartAngle` and `EndAngle` properties.


{% highlight c# %}
SFPieSeries series = new SFPieSeries ();
series.StartAngle  = 180;
series.EndAngle    = 360;            

{% endhighlight %}

![](ChartTypes_images/SemiPie.png)

## Doughnut Chart

To render a doughnut chart, create an instance of `SFDoughnutSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the doughnut segment appearance.

* `Color` – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}
SFChart chart = new SFChart();
...

SFDoughnutSeries doughnutSeries = new SFDoughnutSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Expense", 
    YBindingPath = "Value" 
};
chart.Series.Add(doughnutSeries);

{% endhighlight %}

![](ChartTypes_images/Doughnut.png)

### Changing doughnut inner radius

You can change the doughnut chart inner radius using `DoughnutCoefficient` with respect to the plot area. It ranges from 0 to 1 and the default value is `0.4`.


{% highlight c# %}
    
SFDoughnutSeries series     = new SFDoughnutSeries ();
series.DoughnutCoefficient = 0.6f;   
{% endhighlight %}

![](ChartTypes_images/DoughnutCoefficient.png)

### Changing the doughnut size

You can use the `CircularCoefficient` property to change the diameter of the doughnut chart with respect to the plot area. It ranges from 0 to 1 and the default value is 0.8.


{% highlight c# %}

SFDoughnutSeries series     = new SFDoughnutSeries ();
series.CircularCoefficient  = 0.5f;  
{% endhighlight %}

![](ChartTypes_images/DoughnutCircularCoefficient.png)

### Exploding a doughnut segment

Exploding a specific doughnut segment, you have to set the index to be exploded using `ExplodeIndex` property of the series.

{% highlight c# %}

SFDoughnutSeries series = new SFDoughnutSeries ();
series.ExplodeIndex     = 1;        
{% endhighlight %}

![](ChartTypes_images/DoughnutExplodeIndex.png)

### Exploding all the segments

To explode all the segments, you have to enable `ExplodeAll` property of the series.


{% highlight c# %}

SFDoughnutSeries series = new SFDoughnutSeries ();
series.ExplodeAll       = true;  
{% endhighlight %}


![](ChartTypes_images/DoughnutExplodeAll.png)

### Sector of doughnut

SfChart allows you to render all the data points/segments in semi-doughnut, quarter- doughnut or in any sector using `StartAngle` and `EndAngle` properties.


{% highlight c# %}

SFDoughnutSeries series = new SFDoughnutSeries ();
series.StartAngle       = 180;
series.EndAngle         = 360;        
{% endhighlight %}

![](ChartTypes_images/SemiDoughnut.png)

## Pyramid Chart

To render a pyramid chart, create an instance of `SFPyramidSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the pyramid segment appearance.

* `Color`       – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFPyramidSeries pyramidSeries = new SFPyramidSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Country", 
    YBindingPath = "Value" 
};
chart.Series.Add(pyramidSeries);

{% endhighlight %}

![](ChartTypes_images/Pyramid.png)

### Pyramid Mode

You can render the pyramid series as linear or surface mode. In linear mode, height of the pyramid segment is based on the Y value and in surface mode, area of the pyramid segment is based on the Y values. The default value of `PyramidMode` property is `SFChartPyramidMode.Linear`.


{% highlight c# %}

SFPyramidSeries series = new SFPyramidSeries ();
series.PyramidMode     = SFChartPyramidMode.Surface;   
{% endhighlight %}


![](ChartTypes_images/PyramidMode.png)

### Gap between the segments

You can control the gap between the two segments using `GapRatio` property. Its ranges from 0 to 1.


{% highlight c# %}

SFPyramidSeries series = new SFPyramidSeries ();
series.GapRatio        = 0.1;  
{% endhighlight %}


![](ChartTypes_images/GapRatio.png)

### Exploding a pyramid segment

You can explode a pyramid segment using `ExplodeIndex` property, and `ExplodeOffset` property is used to specify the exploded segment’s distance.


{% highlight c# %}

SFPyramidSeries series = new SFPyramidSeries ();
series.ExplodeIndex    = 2;   
{% endhighlight %}

![](ChartTypes_images/PyramidExplodeIndex.png)

## Funnel Chart

To render a funnel chart, create an instance of `SFFunnelSeries` and add to the Series collection property of `SFChart`. You can use the following properties to customize the funnel segment appearance.

* `Color`       – used to change the color of the series
* `BorderWidth` – used to change the border width of the series
* `BorderColor` – used to change the border color of the series


{% highlight c# %}

SFChart chart = new SFChart();
...

SFFunnelSeries funnelSeries = new SFFunnelSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Status", 
    YBindingPath = "Value" 
};
chart.Series.Add(funnelSeries);
{% endhighlight %}

![](ChartTypes_images/Funnel.png)

### Gap between the segments

You can control the gap between the two segments using `GapRatio` property. Its ranges from 0 to 1.


{% highlight c# %}

SFFunnelSeries series = new SFFunnelSeries ();
series.GapRatio       = 0.1;
   
{% endhighlight %}

![](ChartTypes_images/FunnelGapRatio.png)

### Exploding a funnel segment

You can explode a funnel segment using `ExplodeIndex` property and `ExplodeOffset` property is used to specify the exploded segment’s distance.


{% highlight c# %}
SFFunnelSeries series = new SFFunnelSeries ();
series.ExplodeIndex   = 2;

{% endhighlight %}

![](ChartTypes_images/FunnelExplodeIndex.png)

### Changing the minimum width of the funnel

You can change the minimum width of the funnel neck using `MinimumWidth` property of `SFFunnelSeries`. Default value of `MinimumWidth` is `20`.


{% highlight c# %}

SFFunnelSeries series = new SFFunnelSeries ();
series.MinimumWidth   = 20;

{% endhighlight %}

![](ChartTypes_images/MinWidth.png)