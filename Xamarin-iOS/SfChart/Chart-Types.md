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

To render a line chart, create an instance of `SFLineSeries` and return it in the `GetSeries` method. You can use the following properties to customize the appearance.

* `Color` – used to change the color of the line
* `StrokeWidth` – used to change the stroke width of the line


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFLineSeries series = new SFLineSeries ();

    return series; 
}

{% endhighlight %}


![](ChartTypes_images/Line.png)

## Area Chart

To render an area chart, create an instance of `SFAreaSeries` and return it in the `GetSeries` method. You can use the following properties to customize the appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFAreaSeries series = new SFAreaSeries ();

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/Area.png)

## Spline Area Chart

To render a spline area chart, create an instance of `SFSplineAreaSeries` and return it in the `GetSeries` method. You can use the following properties to customize the spline area appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFSplineAreaSeries series = new SFSplineAreaSeries ();

    return series; 
}

{% endhighlight %}


![](ChartTypes_images/SplineArea.png)



## Stacked Area Chart

To render a stacked area chart, create an instance of `SFStackingAreaSeries` and return it in the `GetSeries` method. You can use the following properties to customize the stacked area appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0) {

        SFStackingAreaSeries series1 = new SFStackingAreaSeries ();

        return series1;

    }
    else if (index ==1) {

        SFStackingAreaSeries series2 = new SFStackingAreaSeries ();

        return series2;

    } 
    else {

        SFStackingAreaSeries series3 = new SFStackingAreaSeries ();

        return series3;

    }  
}

{% endhighlight %}

![](ChartTypes_images/StackedArea.png)

## 100% Stacked Area Chart

To render a 100% stacked area chart, create an instance of `SFStackingArea100Series` and return it in the `GetSeries` method. You can use the following properties to customize the 100% stacked area appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0) {

        SFStackingArea100Series series1 = new SFStackingArea100Series ();

        return series1;

    }
    else if (index ==1) {

        SFStackingArea100Series series2 = new SFStackingArea100Series ();

        return series2;

    } 
    else {

        SFStackingArea100Series series3 = new SFStackingArea100Series ();

        return series3;

    }  
}

{% endhighlight %}

![](ChartTypes_images/StackedArea100.png)

## Column Chart

To render a column chart, create an instance of `SFColumnSeries` and return it in the `GetSeries` method. You can use the following properties to customize the appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFColumnSeries series = new SFColumnSeries ();

    return series; 
}
{% endhighlight %}


![](ChartTypes_images/Column.png)

## Range Column Chart

To render a range column chart, create an instance of `SFRangeColumnSeries` and return it in the `GetSeries` method. 

Since the `SFRangeColumnSeries` requires two Y values for a point, your data should contain high and low values. High and low value specifies the maximum and minimum range of the point. 




{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFRangeColumnSeries series = new SFRangeColumnSeries ();

    return series; 

}
{% endhighlight %}


Following properties are used to customize the range column segment appearance,

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series

![](ChartTypes_images/RangeColumn.png)

## Stacked Column Chart

To render a stacked column chart, create an instance of `SFStackingColumnSeries` and return it in the `GetSeries` method. You can use the following properties to customize the stacked column segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series



{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0) {

        SFStackingColumnSeries series1 = new SFStackingColumnSeries ();

        return series1;

    } 
    else if (index ==1) {

         SFStackingColumnSeries series2 = new SFStackingColumnSeries ();

         return series2; 

    }
    else {

        SFStackingColumnSeries series3 = new SFStackingColumnSeries ();

        return series3;

    } 
}
{% endhighlight %}

![](ChartTypes_images/StackedColumn.png)

## 100% Stacked Column Chart

To render a 100% stacked column chart, create an instance of `SFStackingColumn100Series` and return it in the `GetSeries` method. You can use the following properties to customize the series appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0) {

        SFStackingColumn100Series series1 = new SFStackingColumn100Series ();

        return series1;

    } 
    else if (index ==1) {

         SFStackingColumn100Series series2 = new SFStackingColumn100Series ();

         return series2; 

    }
    else {

        SFStackingColumn100Series series3 = new SFStackingColumn100Series ();

        return series3;

    } 
}

{% endhighlight %}


![](ChartTypes_images/StackedColumn100.png)

## Bar Chart

To render a bar chart, create an instance of `SFBarSeries` and return it in the `GetSeries` method. You can use the following properties to customize the bar segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFBarSeries series = new SFBarSeries ();

    return series; 
}
{% endhighlight %}


![](ChartTypes_images/Bar.png)

## Stacked Bar Chart

To render a stacked bar chart, create an instance of `SFStackingBarSeries` and return it in the `GetSeries` method. You can use the following properties to customize the stacked bar segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0) {

         SFStackingBarSeries series1 = new SFStackingBarSeries ();

         return series1;

    } 
    else if (index ==1) {

         SFStackingBarSeries series2 = new SFStackingBarSeries ();

         return series2;

    }
    else {

        SFStackingBarSeries series3 = new SFStackingBarSeries ();

        return series3;

    } 
}

{% endhighlight %}


![](ChartTypes_images/StackedBar.png)

## 100% Stacked Bar Chart

To render a 100% stacked bar chart, create an instance of `SFStackingBar100Series` and return it in the `GetSeries` method. You can use the following properties to customize the series appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    if (index == 0) {

         SFStackingBar100Series series1 = new SFStackingBar100Series ();

         return series1;
    } 
    else if (index ==1) {

        SFStackingBar100Series series2 = new SFStackingBar100Series ();

        return series2;
    } 
    else {

         SFStackingBar100Series series3 = new SFStackingBar100Series ();

         return series3;
    } 
}
{% endhighlight %}

![](ChartTypes_images/StackedBar100.png)

## Spline Chart

To render a spline chart, create an instance of `SFSplineSeries` and return it in the `GetSeries` method. You can use the following properties to customize the spline segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFSplineSeries series = new SFSplineSeries ();

    return series; 

}
{% endhighlight %}


![](ChartTypes_images/Spline.png)

## StepLine Chart

To render a step line chart, create an instance of `SFStepLineSeries` and return it in the `GetSeries` method. You can use the following properties to customize the appearance.

* `Color` – used to change the color of the line
* `StrokeWidth` – used to change the stroke width of the line


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFStepLineSeries series  = new SFStepLineSeries ();

    return series;  
}

{% endhighlight %}


![](ChartTypes_images/StepLine.png)

## Fast Line Chart

`SFFastLineSeries` is a line chart, but it loads faster than `SFLineSeries`. You can use this when there are large number of points to be loaded in chart. To render a fast line chart, create an instance of `SFFastLineSeries` and return it in the `GetSeries` method. You can use the following properties to customize the fast line segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFFastLineSeries series    = new SFFastLineSeries ();

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/FastLine.png)

### Dashed Lines

`Dashes` property of the `SFFastLineSeries` is used to render fast line series with dashes.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFFastLineSeries series = new SFFastLineSeries ();

    NSObject[] dashes       = new NSObject[2];

    dashes [0]              = (NSNumber)2;

    dashes [1]              = (NSNumber)3;

    series.Dashes           = NSArray.FromObjects (dashes);

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/DashedLines.png)

## Bubble Chart

To render a bubble chart, create an instance of `SFBubbleSeries` and return it in the `GetSeries` method. 

Bubble chart requires 3 fields (X, Y and Size) to plot a point. Here **Size** is used to specify the size of each bubble segment. 



{% highlight c# %}

public ChartDataModel ()
  {

    AddDataPointsForChart("64", 14.4, 20);

    AddDataPointsForChart("71", 2, 15);

    AddDataPointsForChart("74", 7, 30);

    AddDataPointsForChart("80", 4, 22);

    AddDataPointsForChart("82", 10.3, 28);

    AddDataPointsForChart("94", 1, 8); 

    AddDataPointsForChart("96", 6, 18);

    AddDataPointsForChart("98", 12.3, 28);
}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFBubbleSeries series = new SFBubbleSeries ();

    return series;  
}

{% endhighlight %}



Following properties are used to customize the bubble segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series
* `MinimumRadius` – used to change the minimum size of the series
* `MaximumRadius` – used to change the maximum size of the series

![](ChartTypes_images/Bubble.png)

## Scatter Chart	

To render a scatter chart, create an instance of `SFScatterSeries` and return it in the `GetSeries` method. You can use the following properties to customize the scatter segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series
* `ScatterWidth` – used to change the width of the series
* `ScatterHeight` – used to change the height of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFScatterSeries series = new SFScatterSeries ();

    return series;  
}
{% endhighlight %}

![](ChartTypes_images/Scatter.png)

## OHLC Chart

To render an OHLC chart, create an instance of `SFOHLCSeries` and return it in the `GetSeries` method.

OHLC chart requires five values (X, Open, High, Low and Close) to plot a point. 

You can use SFChartDataPoint's five parameter constructor to pass x, open, high, low and close values to  `SFOHLCSeries`,


{% highlight c# %}

 public ChartDataModel ()
 {

    AddDataPointsForChart("2010", 873.8, 878.85, 855.5, 860.5);

    AddDataPointsForChart("2011", 861, 868.4, 835.2, 843.45);

    AddDataPointsForChart("2012", 846.15, 853, 838.5, 847.5);

    AddDataPointsForChart("2013", 846, 860.75, 841, 855);

    AddDataPointsForChart("2014", 841, 845, 827.85, 838.65); 
}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFOHLCSeries series = new SFOHLCSeries ();

    return series;  
}

{% endhighlight %}


You can use the following properties to customize the HiLoOpenCloseSeries segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series

![](ChartTypes_images/OHLC.png)

### Bull and Bear Color	

In OHLC chart, `BullFillColor` property is used to specify a fill color for the segments that indicates an increase in stock price in the measured time interval and `BearFillColor` property is used to specify a fill color for the segments that indicates a decrease in stock price in the measured time interval.


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFOHLCSeries series  = new SFOHLCSeries ();

    series.BearFillColor = UIColor.Blue;

    series.BullFillColor = UIColor.Purple;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/OHLC1.png)

## Candle Chart

To render a candle chart, create an instance of `SFCandleSeries` and return it in the `GetSeries` method.

Candle chart requires five values (X, Open, High, Low and Close) to plot a point. 

You can use SFChartDataPoint's five parameter constructor to pass x, open, high, low and close values to  `SFCandleSeries`,


{% highlight c# %}


public ChartDataModel ()
 {

    AddDataPointsForChart("2010", 873.8, 878.85, 855.5, 860.5);

    AddDataPointsForChart("2011", 861, 868.4, 835.2, 843.45);

    AddDataPointsForChart("2012", 846.15, 853, 838.5, 847.5);

    AddDataPointsForChart("2013", 846, 860.75, 841, 855);

    AddDataPointsForChart("2014", 841, 845, 827.85, 838.65); 
}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFCandleSeries series = new SFCandleSeries ();

    return series;  
}

{% endhighlight %}

You can use the following properties to customize the candle segment appearance.

* `Color`       – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series

![](ChartTypes_images/Candle.png)

### Bull and Bear Color

In Candle chart, `BullFillColor` property is used to specify a fill color for the segments that indicates an
increase in stock price in the measured time interval and `BearFillColor` property is used to specify a fill color
for the segments that indicates a decrease in stock price in the measured time interval.



{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFCandleSeries series = new SFCandleSeries ();

    series.BearFillColor  = UIColor.Blue;

    series.BullFillColor  = UIColor.Purple;

    return series; 
}

{% endhighlight %}


![](ChartTypes_images/Candle1.png)

## Radar Chart

To render a candle chart, create an instance of `SFRadarSeries` and return it in the `GetSeries` method.

### Draw type

`DrawType` property is used to specify the radar series rendering type. Following are the two options you can set to this property,

* `Line` – data points are visualized as line.
* `Area` – data points are visualized as area.

{% highlight c# %}
SFRadarSeries radarSeries   = new SFRadarSeries();
radarSeries.DrawType        = SFChartPolarRadarSeriesDrawType.Line;

{% endhighlight %}

![](ChartTypes_images/Radar.png)

### Customize the appearance

You can use the following properties to customize the appearance.

* `Color` – used to change the color of the series.
* `BorderWidth` – used to change the stroke width of the series.
* `BorderColor` – used to change the stroke color of the series when draw types is set to area
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

## Polar Chart

To render a polar chart, create an instance of `SFPolarSeries` and return it in the `GetSeries` method. 

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
* `BorderWidth` – used to change the stroke width of the series.
* `BorderColor` – used to change the stroke color of the series when draw types is set to area
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

## Pie Chart

To render a pie chart, create an instance of `SFPieSeries` and return it in the `GetSeries` method. You can use the following properties to customize the pie segment appearance.

* `Color`       – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFPieSeries series         = new SFPieSeries ();

    series.CircularCoefficient = 0.5f;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/PieCircularCoefficient.png)

### Exploding a pie segment

You can explode a pie segment using `ExplodeIndex` property and specify the explode radius using `ExplodeRadius` property of `SFPieSeries`.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFPieSeries series  = new SFPieSeries ();

    series.ExplodeIndex = 1;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/PieExplodeIndex.png)

### Exploding all the segments

Using `ExplodeAll` property of `SFPieSeries`, you can explode all the pie segments.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFPieSeries series = new SFPieSeries ();

    series.ExplodeAll  = true;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/PieExplodeAll.png)

### Sector of Pie

SFChart allows you to render all the data points/segments in semi-pie, quarter-pie or in any sector using `StartAngle` and `EndAngle` properties.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFPieSeries series = new SFPieSeries ();

    series.StartAngle  = 180;

    series.EndAngle    = 360;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/SemiPie.png)

## Doughnut Chart

To render a doughnut chart, create an instance of `SFDoughnutSeries` and return it in the `GetSeries` method. You can use the following properties to customize the doughnut segment appearance.

* `Color` – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFDoughnutSeries series = new SFDoughnutSeries ();

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/Doughnut.png)

### Changing Doughnut inner radius

You can change the doughnut chart inner radius using `DoughnutCoefficient` with respect to the plot area. It ranges from 0 to 1 and the default value is `0.4`.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFDoughnutSeries series     = new SFDoughnutSeries ();

    series.doughnutCoefficient  = 0.6f;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/DoughnutCoefficient.png)

### Changing the doughnut size

You can use the `CircularCoefficient` property to change the diameter of the doughnut chart with respect to the plot area. It ranges from 0 to 1 and the default value is 0.8.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFDoughnutSeries series     = new SFDoughnutSeries ();

    series.CircularCoefficient  = 0.5f;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/DoughnutCircularCoefficient.png)

### Exploding a doughnut segment

Exploding a specific doughnut segment, you have to set the index to be exploded using `ExplodeIndex` property of the series.

{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFDoughnutSeries series = new SFDoughnutSeries ();

    series.ExplodeIndex     = 1;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/DoughnutExplodeIndex.png)

### Exploding all the segments

To explode all the segments, you have to enable `ExplodeAll` property of the series.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFDoughnutSeries series = new SFDoughnutSeries ();

    series.ExplodeAll       = true;

    return series; 
}

{% endhighlight %}


![](ChartTypes_images/DoughnutExplodeAll.png)

### Sector of Doughnut

SfChart allows you to render all the data points/segments in semi-doughnut, quarter- doughnut or in any sector using `StartAngle` and `EndAngle` properties.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFDoughnutSeries series = new SFDoughnutSeries ();

    series.StartAngle       = 180;

    series.EndAngle         = 360;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/SemiDoughnut.png)

## Pyramid Chart

To render a pyramid chart, create an instance of `SFPyramidSeries` and return it in the `GetSeries` method. You can use the following properties to customize the pyramid segment appearance.

* `Color`       – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFPyramidSeries series = new SFPyramidSeries ();

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/Pyramid.png)

### Pyramid Mode

You can render the pyramid series as linear or surface mode. In linear mode, height of the pyramid segment is based on the Y value and in surface mode, area of the pyramid segment is based on the Y values. The default value of `PyramidMode` property is `SFChartPyramidMode.Linear`.


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFPyramidSeries series = new SFPyramidSeries ();

    series.PyramidMode     = SFChartPyramidMode.Surface;

    return series; 
}

{% endhighlight %}


![](ChartTypes_images/PyramidMode.png)

### Gap between the segments

You can control the gap between the two segments using `GapRatio` property. Its ranges from 0 to 1.


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFPyramidSeries series = new SFPyramidSeries ();

    series.GapRatio        = 0.1;

    return series; 
}

{% endhighlight %}


![](ChartTypes_images/GapRatio.png)

### Exploding a pyramid segment

You can explode a pyramid segment using `ExplodeIndex` property, and `ExplodeOffset` property is used to specify the exploded segment’s distance.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFPyramidSeries series = new SFPyramidSeries ();

    series.ExplodeIndex    = 2;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/PyramidExplodeIndex.png)

## Funnel Chart

To render a funnel chart, create an instance of `SFFunnelSeries` and return it in the `GetSeries` method. You can use the following properties to customize the funnel segment appearance.

* `Color`       – used to change the color of the series
* `StrokeWidth` – used to change the stroke width of the series
* `StrokeColor` – used to change the stroke color of the series


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFFunnelSeries series = new SFFunnelSeries ();

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/Funnel.png)

### Gap between the segments

You can control the gap between the two segments using `GapRatio` property. Its ranges from 0 to 1.


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFFunnelSeries series = new SFFunnelSeries ();

    series.GapRatio       = 0.1;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/FunnelGapRatio.png)

### Exploding a funnel segment

You can explode a funnel segment using `ExplodeIndex` property and `ExplodeOffset` property is used to specify the exploded segment’s distance.


{% highlight c# %}
public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFFunnelSeries series = new SFFunnelSeries ();

    series.ExplodeIndex   = 2;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/FunnelExplodeIndex.png)

### Changing the minimum width of the funnel

You can change the minimum width of the funnel neck using `MinimumWidth` property of `SFFunnelSeries`. Default value of `MinimumWidth` is `20`.


{% highlight c# %}

public override SFSeries GetSeries (SFChart chart, nint index)
{
    SFFunnelSeries series = new SFFunnelSeries ();

    series.MinimumWidth   = 20;

    return series; 
}

{% endhighlight %}

![](ChartTypes_images/MinWidth.png)