---
layout: post
title: Chart Axis | SFChart | Xamarin.iOS | Syncfusion
description: This section explains the different types of axis, and how to customize the grid lines, tick lines, labels and title of chart axis.
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Axis in Xamarin.iOS Chart(SfChart)

Charts typically have two axes that are used to measure and categorize data: a vertical (Y) axis, and a horizontal (X) axis.

Vertical(Y) axis uses numeric or logarithmic scale. Horizontal(X) axis supports the following types of scale:

* Category
* Numeric
* Date time
* Logarithmic Axis

The following APIs are available in ChartAxis:

* [`VisibleLabels`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_VisibleLabels) – Represents the axis label collection, which is visible in axis.
* [`VisibleRange`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_VisibleRange) – Represents the [`Start`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DoubleRange.html#Syncfusion_SfChart_iOS_DoubleRange_Start) and [`End`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DoubleRange.html#Syncfusion_SfChart_iOS_DoubleRange_End) range of an axis. The [`Delta`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.DoubleRange.html#Syncfusion_SfChart_iOS_DoubleRange_Delta) property of VisibleRange represents the delta value.

## Category Axis

Category axis displays text labels instead of numbers. 

{% highlight c# %}

SFCategoryAxis xAxis = new SFCategoryAxis ();

chart.PrimaryAxis 	 = xAxis;
{% endhighlight %}


![Category axis support in Xamarin.iOS Chart](Axis_images/CategoryAxis.png)

### Placing labels between ticks

Labels in category axis can be placed between the ticks by setting [`LabelPlacement`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCategoryAxis.html#Syncfusion_SfChart_iOS_SFCategoryAxis_LabelPlacement) to [`SFChartLabelPlacement.BetweenTicks`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartLabelPlacement.html). Default value of [`LabelPlacement`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFCategoryAxis.html#Syncfusion_SfChart_iOS_SFCategoryAxis_LabelPlacement) property is [`SFChartLabelPlacement.OnTicks`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartLabelPlacement.html) i.e. labels will be placed on the ticks by default.

{% highlight c# %}

xAxis.LabelPlacement = SFChartLabelPlacement.BetweenTicks;
{% endhighlight %}

![Axis labels between ticks support in Xamarin.iOS Chart](Axis_images/BetweenTicks.png)

### Displaying labels after a fixed interval

To display labels after a fixed interval n, you can set [`Interval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Interval) property of [`SFAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html) as n. Default value of interval is 1 i.e. all the labels will be displayed by default.


{% highlight c# %}

xAxis.Interval = new NSNumber (2);
{% endhighlight %}


![Enable or disable the axis auto-interval support in Xamarin.iOS Chart](Axis_images/CategoryInterval.png)

### Indexed category axis

Category axis can also be rendered based on the index values of data source by setting the [`ArrangeByIndex`]() property to true in the axis.

{% highlight c# %} 
[C#]

chart.PrimaryAxis = new SFCategoryAxis() 
{ 
	ArrangeByIndex = false 
};

SFColumnSeries series1 = new SFColumnSeries()
{
        ItemsSource = view.Data1,
        XBindingPath = "Country",
        YBindingPath = "Year2016"
};
SFColumnSeries series2 = new SFColumnSeries()
{
        ItemsSource = view.Data2,
        XBindingPath = "Country",
        YBindingPath = "Year2016",
};

chart.Series.Add(series1);
chart.Series.Add(series2);

{% endhighlight %}

![Category axis indexed feature support in Xamarin.Android Chart](Axis_images/ArrangeByIndex.png)

## Numeric Axis

Numeric axis uses numerical scale and displays numbers as labels. 


{% highlight c# %}

SFNumericalAxis xAxis = new SFNumericalAxis ();

chart.PrimaryAxis     = xAxis;
{% endhighlight %}

![Numerical axis support in Xamarin.iOS Chart](Axis_images/NumericalAxis.png)

### Customizing numeric range

To customize the range of an axis, you can use the [`Minimum`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_Maximum) properties of [`SFNumericalAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html). By default, range will be calculated automatically based on the provided data.


{% highlight c# %}

SFNumericalAxis yAxis 	= new SFNumericalAxis ();

chart.SecondaryAxis     = yAxis;

yAxis.Minimum           = new NSNumber (10);

yAxis.Maximum           = new NSNumber (50);

{% endhighlight %}


![NumericalAxis range customization support in Xamarin.iOS Chart](Axis_images/NumericMinMax.png)

### Customizing numeric interval

Axis interval can be customized using the [`Interval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Interval) property of [`SFAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html). By default, interval will be calculated based on the minimum and maximum value of the provided data.

{% highlight c# %}

yAxis.Interval = new NSNumber (5);
{% endhighlight %}

![NumericalAxis interval customization support in Xamarin.iOS Chart](Axis_images/NumericInterval.png)

### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the axis range by using [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property. Numeric axis supports the following types of padding.

* None
* Round
* Additional
* Normal
* RoundStart
* RoundEnd
* PrependInterval
* AppendInterval

**None**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property is [`SFChartNumericalPadding.None`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartNumericalPadding.html), padding will not be applied to the axis. This is also the default value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) for horizontal axis.

{% highlight c# %}

yAxis.RangePadding = SFChartNumericalPadding.None;

{% endhighlight %}


![NumericalAxis range padding support in Xamarin.iOS Chart](Axis_images/NumericPaddingNone.png)

**Round**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property is [`SFChartNumericalPadding.Round`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartNumericalPadding.html), axis range will be rounded to the nearest possible value by the interval.

{% highlight c# %}

yAxis.RangePadding = SFChartNumericalPadding.Round; 
{% endhighlight %}


![NumericalAxis range padding support in Xamarin.iOS Chart](Axis_images/NumericPaddingRound.png)

**Additional**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property is [`SFChartNumericalPadding.Additional`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartNumericalPadding.html), axis range will be rounded and an interval of the axis will be added as padding to the minimum and maximum values of the range.

{% highlight c# %}

yAxis.RangePadding = SFChartNumericalPadding.Additional; 
{% endhighlight %}


![NumericalAxis range padding support in Xamarin.iOS Chart](Axis_images/NumericPaddingAdditional.png)

**Normal**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property is [`SFChartNumericalPadding.Normal`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartNumericalPadding.html), range will be calculated for the axis based on the best readability of the data. This is also the default for vertical axis.

{% highlight c# %}

yAxis.RangePadding = SFChartNumericalPadding.Normal; 
{% endhighlight %}


![NumericalAxis range padding support in Xamarin.iOS Chart](Axis_images/NumericPaddingNormal.png)

**RoundStart**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property is [`SFChartNumericalPadding.RoundStart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartNumericalPadding.html), axis range will be rounded in the start to the nearest possible value by the interval.

{% highlight c# %}

yAxis.RangePadding = SFChartNumericalPadding.RoundStart; 
{% endhighlight %}

![NumericalAxis range padding support in Xamarin.iOS Chart](Axis_images/NumericalAxis_range_padding_RoundStart.png)

**RoundEnd**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property is [`SFChartNumericalPadding.RoundEnd`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartNumericalPadding.html), axis range will be rounded in the end to the nearest possible value by the interval.

{% highlight c# %}

yAxis.RangePadding = SFChartNumericalPadding.RoundEnd; 
{% endhighlight %}

![NumericalAxis range padding support in Xamarin.iOS Chart](Axis_images/NumericalAxis_range_padding_RoundEnd.png)

**PrependInterval**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property is [`SFChartNumericalPadding.PrependInterval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartNumericalPadding.html), axis range will be rounded and an interval of the axis will be added in the start as padding to the minimum values of the range.

{% highlight c# %}

yAxis.RangePadding = SFChartNumericalPadding.PrependInterval; 
{% endhighlight %}

![NumericalAxis range padding support in Xamarin.iOS Chart](Axis_images/NumericalAxis_range_padding_PrependInterval.png)

**AppendInterval**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFNumericalAxis.html#Syncfusion_SfChart_iOS_SFNumericalAxis_RangePadding) property is [`SFChartNumericalPadding.AppendInterval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartNumericalPadding.html), axis range will be rounded and an interval of the axis will be added in the end as padding to the maximum values of the range.

{% highlight c# %}

yAxis.RangePadding = SFChartNumericalPadding.AppendInterval; 
{% endhighlight %}

![NumericalAxis range padding support in Xamarin.iOS Chart](Axis_images/NumericalAxis_range_padding_AppendInterval.png)

## Date Time Axis

Date time axis uses date time scale and displays date time values as axis labels in specified format. 

{% highlight c# %}

SFDateTimeAxis xAxis = new SFDateTimeAxis ();

chart.PrimaryAxis    = xAxis; 
{% endhighlight %}


![DateTime axis support in Xamarin.iOS Chart](Axis_images/DateTimeAxis.png)

### Customizing date time range

To customize the range of an axis, you can use the [`Minimum`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_Maximum) properties of [`SFDateTimeAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html). By default, range will be calculated automatically based on the provided data.

{% highlight c# %}

SFDateTimeAxis primaryAxis = new SFDateTimeAxis();
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);           
primaryAxis.Minimum = calendar.DateFromComponents(new NSDateComponents() {Year = 2010, Month = 1, Day = 1 });           
primaryAxis.Maximum = calendar.DateFromComponents(new NSDateComponents() {Year = 2015, Month = 12, Day = 31 });            

{% endhighlight %}


![DateTimeAxis range customization support in Xamarin.iOS Chart](Axis_images/DateTimeMinMax.png)

### Date time intervals

Date time intervals can be customized using [`Interval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Interval) and [`IntervalType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_IntervalType) properties of the [`SFDateTimeAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html). For example, setting [`Interval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Interval) as 2 and [`IntervalType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_IntervalType) as [`SFChartDateTimeIntervalType.Years`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimeIntervalType.html) will consider 2 years as interval.

Essential Chart supports the following types of interval for date time axis

* Years
* Months
* Days
* Hours
* Minutes
* Seconds
* Milliseconds

{% highlight c# %}

xAxis.IntervalType = SFChartDateTimeIntervalType.Months;

xAxis.Interval     = new NSNumber (6); 
{% endhighlight %}


![DateTimeAxis interval support in Xamarin.iOS Chart](Axis_images/DateTimeInterval.png)

### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the range by using [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding) property. Date time axis supports the following types of padding:

* None
* Round
* Additional
* RoundStart
* RoundEnd
* PrependInterval
* AppendInterval

**None**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding) property is [`SFChartDateTimePadding.None`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimePadding.html), padding will not be applied to the axis. This is also the default value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding).

{% highlight c# %}

xAxis.RangePadding = SFChartDateTimePadding.None;
{% endhighlight %}


![DateTimeAxis range padding support in Xamarin.iOS Chart](Axis_images/DateTimePaddingNone.png)

**Round**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding) property is [`SFChartDateTimePadding.Round`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimePadding.html), axis range will be rounded to the nearest possible date time value.


{% highlight c# %}

xAxis.RangePadding = SFChartDateTimePadding.Round;
{% endhighlight %}


![DateTimeAxis range padding support in Xamarin.iOS Chart](Axis_images/DateTimePaddingRound.png)

**Additional**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding) property is [`SFChartDateTimePadding.Additional`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimePadding.html), range will be rounded and date time interval of the axis will be added as padding to the minimum and maximum extremes of the range.

{% highlight c# %}

xAxis.RangePadding = SFChartDateTimePadding.Additional; 
{% endhighlight %}


![DateTimeAxis range padding support in Xamarin.iOS Chart](Axis_images/DateTimePaddingAdditional.png)

**RoundStart**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding) property is [`SFChartDateTimePadding.RoundStart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimePadding.html), axis range will be rounded in the start to the nearest possible date time value.


{% highlight c# %}

xAxis.RangePadding = SFChartDateTimePadding.RoundStart;
{% endhighlight %}


![DateTimeAxis range padding support in Xamarin.iOS Chart](Axis_images/DateTimeAxis_range_padding_RoundStart.png)

**RoundEnd**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding) property is [`SFChartDateTimePadding.RoundEnd`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimePadding.html), axis range will be rounded in the end to the nearest possible date time value.


{% highlight c# %}

xAxis.RangePadding = SFChartDateTimePadding.RoundEnd;
{% endhighlight %}


![DateTimeAxis range padding support in Xamarin.iOS Chart](Axis_images/DateTimeAxis_range_padding_RoundEnd.png)

**PrependInterval**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding) property is [`SFChartDateTimePadding.PrependInterval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimePadding.html), axis range will be rounded and date time interval of the axis will be added in the start as padding to the minimum extremes of the range.

{% highlight c# %}

xAxis.RangePadding = SFChartDateTimePadding.PrependInterval; 
{% endhighlight %}


![DateTimeAxis range padding support in Xamarin.iOS Chart](Axis_images/DateTimeAxis_range_padding_PrependInterval.png)

**AppendInterval**

When the value of [`RangePadding`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html#Syncfusion_SfChart_iOS_SFDateTimeAxis_RangePadding) property is [`SFChartDateTimePadding.AppendInterval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimePadding.html), axis range will be rounded and date time interval of the axis will be added in the end as padding to the maximum extremes of the range.

{% highlight c# %}

xAxis.RangePadding = SFChartDateTimePadding.AppendInterval; 
{% endhighlight %}


![DateTimeAxis range padding support in Xamarin.iOS Chart](Axis_images/DateTimeAxis_range_padding_AppendInterval.png)

## Date-time category axis

The [`DateTimeCategoryAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeCategoryAxis.html) is a unique type of axis used mainly with financial series. Like CategoryAxis, all the data points are plotted with equal spaces by removing space for missing dates. Intervals and ranges for the axis are calculated similar to DateTimeAxis. There will be no visual gaps between points even when the difference between two points is more than a year. The following APIs are used to customize the interval of DateTimeCategoryAxis.

•	[`Interval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Interval) - Gets or sets the double value that represents the interval between the labels.
•	[`IntervalType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeCategoryAxis.html#Syncfusion_SfChart_iOS_SFDateTimeCategoryAxis_IntervalType) - Gets or sets the DateTimeIntervalType that represents the type of the interval to be displayed.

{% highlight c# %}

SFDateTimeCategoryAxis xAxis = new SFDateTimeCategoryAxis();
xAxis.Interval = new NSNumber(1);
xAxis.IntervalType = SFChartDateTimeIntervalType.Months;
chart.PrimaryAxis = xAxis;

{% endhighlight %}

![DateTimeCategory axis support in Xamarin.iOS Chart](Axis_images/DateTimeCategoryAxis.png)

## Logarithmic Axis

Logarithmic axis uses logarithmic scale and displays numbers as axis labels.

{% highlight c# %}

SFLogarithmicAxis yAxis    = new SFLogarithmicAxis (); 
chart.SecondaryAxis        = yAxis; 
 
{% endhighlight %}


![Logarithmic axis support in Xamarin.iOS Chart](Axis_images/LogAxis1.png)

### Customizing the logarithmic range

To customize the range of log axis, you can use the [`Minimum`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_Maximum) properties of [`LogarithmicAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLogarithmicAxis.html). By default, nice range will be calculated automatically based on the provided data.



{% highlight c# %}

SFLogarithmicAxis yAxis         = new SFLogarithmicAxis ();
yAxis.Minimum                   = new NSNumber(100);
yAxis.Maximum                   = new NSNumber(10000); 
chart.SecondaryAxis             = yAxis; 

{% endhighlight %}


![LogarithmicAxis range customization support in Xamarin.iOS Chart](Axis_images/LogAxis2.png)

### Customizing the logarithmic base 

To customize the log base value, you can use [`LogarithmicBase`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLogarithmicAxis.html#Syncfusion_SfChart_iOS_SFLogarithmicAxis_LogarithmicBase) property.


{% highlight c# %}

SFLogarithmicAxis yAxis          = new SFLogarithmicAxis ();
yAxis.LogarithmicBase            =  2; 
chart.SecondaryAxis              = yAxis; 


{% endhighlight %}


![LogarithmicAxis base support in Xamarin.iOS Chart](Axis_images/LogAxis3.png)

## Common axis features

Customization of features such as axis title, labels, grid lines and tick lines are common to all the axes. Each of these features are explained in this section.

### Axis Visibility

Axis visibility can be controlled using the [`Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Visible) property of axis. Default value of [`Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Visible) property is `True`.

{% highlight c# %}

chart.SecondaryAxis.Visible = false; 

{% endhighlight %}


![Axis visibility support in Xamarin.iOS Chart](Axis_images/AxisIsVisible.png)

### Axis title

The [`Title`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Title) property in axis provides options to customize the text and font of axis title. Axis does not display title by default. The title can be customized using following properties,

* [`Text`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisTitleStyle.html#Syncfusion_SfChart_iOS_SFAxisTitleStyle_Text) – used to set the title for axis.
* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Color) – used to change the color of the label.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BackgroundColor) – used to change the label background color.
* [`BorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderColor) – used to change the border color.
* [`BorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderWidth) – used to change the width of the border.
* [`Font`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Font) – used to change the text size, font family and font weight.
* [`Margin`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Margin) - used to change the margin size for labels.

Following code snippet illustrates how to enable and customize the axis title.

{% highlight c# %}

chart.PrimaryAxis.Title.Text   = new NSString ("Month");

chart.PrimaryAxis.Title.Color  = UIColor.Blue;

chart.PrimaryAxis.Title.Font   = UIFont.BoldSystemFontOfSize(20);
{% endhighlight %}


![Axis title support in Xamarin.iOS Chart](Axis_images/AxisTitle.png)

### Axis label rotation

The [`LabelRotationAngle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_LabelRotationAngle) property of axis can be used to rotate the axis labels position. Default value of [`LabelRotationAngle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_LabelRotationAngle) property is 0d.

{% highlight c# %}

SFCategoryAxis categoryAxis = new SFCategoryAxis(); 
  
categoryAxis.LabelRotationAngle = -45; 
  
chart.PrimaryAxis = categoryAxis;

{% endhighlight %}

![Axis label rotation support in Xamarin.iOS Chart](Axis_images/rotationangle.png)

### Axis line customization

[`SFChart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChart.html) provides support to customize the style of the axis line by using the [`AxisLineStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisLineStyle.html) property as shown in the below code snippet.

* [`LineColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLineStyle.html#Syncfusion_SfChart_iOS_SFLineStyle_LineColor) - used to change the line color of axis line.
* [`LineWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLineStyle.html#Syncfusion_SfChart_iOS_SFLineStyle_LineWidth) - used to change the line width of axis line.
* [`Dashes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisLineStyle.html#Syncfusion_SfChart_iOS_SFAxisLineStyle_Dashes) - used to render axis line series with dashes.

{% highlight c# %}

SFCategoryAxis primaryAxis = new SFCategoryAxis();

primaryAxis.AxisLineStyle.LineColor = UIColor.Red;

primaryAxis.AxisLineStyle.LineWidth = 10;

NSObject[] dashes = new NSObject[2];

dashes [0] = (NSNumber)2;

dashes [1] = (NSNumber)3;

primaryAxis.AxisLineStyle.Dashes = NSArray.FromObjects(dashes);

chart.PrimaryAxis = primaryAxis;

{% endhighlight %}

![Axis line customization support in Xamarin.iOS Chart](Axis_images/axislinecustom.png)

### Axis line offset

The [`AxisLineOffset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_AxisLineOffset) property is used to offset the rendering of axis line.

{% highlight c# %}

SFCategoryAxis categoryAxis = new SFCategoryAxis(); 
  
categoryAxis.PlotOffset = 20;

categoryAxis.AxisLineOffset = 20;

categoryAxis.AxisLineStyle.StrokeWidth = 5;
  
chart.PrimaryAxis = categoryAxis;

{% endhighlight %}

![Axis line offset support in Xamarin.iOS Chart](Axis_images/axislineoffset.png)

### Label customization

The [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_LabelStyle) property of axis provides options to customize the font-family, color, size and font-weight of axis labels. The axis labels can be customized using following properties:

* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Color) – used to change the color of the labels.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BackgroundColor) – used to change the label background color.
* [`BorderColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderColor) – used to change the border color.
* [`BorderWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_BorderWidth) – used to change the thickness of the border.
* [`Font`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Font) – used to change the text size, font family and font weight.
* [`Margin`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLabelStyle.html#Syncfusion_SfChart_iOS_SFLabelStyle_Margin) - used to change the margin size for labels.
* [`LabelAlignment`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFAxisLabelStyle_LabelAlignment) - Used to align the label at the [`Start`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAxisLabelAlignment.html), Center, or End.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFAxisLabelStyle_CornerRadius) - Used to change the corner radius of the background of labels.
* [`MaxWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFAxisLabelStyle_MaxWidth) - Provides the maximum text width of the axis label and wraps into the next line when exceeds the maximum width.
* [`WrappedLabelAlignment`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFAxisLabelStyle_WrappedLabelAlignment) - Positions the wrapped text at the start, center, or end. The default value of the [`WrappedLabelAlignment`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFAxisLabelStyle_WrappedLabelAlignment) property is `Start`.

{% highlight c# %}

chart.PrimaryAxis.LabelStyle.Font  = UIFont.BoldSystemFontOfSize (20);

chart.PrimaryAxis.LabelStyle.Color = UIColor.Red;

{% endhighlight %}


![Axis label customization support in Xamarin.iOS Chart](Axis_images/LabelStyle.png)

### Label and tick positioning

Axis labels and ticks can be positioned [`Inside`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisElementPosition.html) or [`Outside`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisElementPosition.html) the chart area by using [`LabelsPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisLabelStyle.html#Syncfusion_SfChart_iOS_SFAxisLabelStyle_LabelsPosition) and [`TickPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_TickPosition) properties of [`SFAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html). By default labels and ticks will be positioned outside the chart area.

{% highlight c# %}

chart.PrimaryAxis.LabelStyle.LabelsPosition   = SFChartAxisElementPosition.Inside;

chart.PrimaryAxis.TickPosition                = SFChartAxisElementPosition.Inside;
{% endhighlight %}


![Axis labels and ticks positioning support in Xamarin.iOS Chart](Axis_images/TickPosition.png)

### Edge labels placement

Labels with long text at the edges of an axis may appear partially outside the chart. The [`EdgeLabelsDrawingMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_EdgeLabelsDrawingMode) property can be used to avoid the partial appearance of labels at the corners. The default [`EdgeLabelsDrawingMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_EdgeLabelsDrawingMode) is [`Center`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisEdgeLabelsDrawingMode.html).

{% highlight c# %}

chart.PrimaryAxis.EdgeLabelsDrawingMode = SFChartAxisEdgeLabelsDrawingMode.Shift; 
{% endhighlight %}

![Axis edge labels placement support in Xamarin.iOS Chart](Axis_images/EdgeLabel.png)

### Edge labels visibility

The visibility of the edge labels in an axis can be controlled using [`EdgeLabelsVisibilityMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_EdgeLabelsVisibilityMode) property.
The following options are available in [`EdgeLabelsVisibilityMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_EdgeLabelsVisibilityMode),

* [`Default`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisEdgeLabelsVisibilityMode.html) - used to display the edge label based on auto interval calculations.
* [`Visible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisEdgeLabelsVisibilityMode.html) - used to display the edge labels (first and last label) irrespective of the auto interval calculation until zooming (i.e., in normal state).
* [`AlwaysVisible`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisEdgeLabelsVisibilityMode.html) - used to always display the edge labels even while zooming the chart.

The following code example demonstrates the AlwaysVisible option.

{% highlight c# %}

chart.SecondaryAxis.EdgeLabelsVisibilityMode  = SFChartAxisEdgeLabelsVisibilityMode.AlwaysVisible; 

{% endhighlight %}

### Label extent 

The [`LabelExtent`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_LabelExtent) property allows to set the gap between axis labels and title. This is typically used to maintain the fixed gap between axis labels and title when the digits of the axis value changed in live update.

{% highlight c# %}

Chart.PrimaryAxis = new SFCategoryAxis();

Chart.PrimaryAxis.LabelExtent = 60;

Chart.PrimaryAxis.Title.Text = new NSString("Month");

{% endhighlight %}


![Axis label extent support in Xamarin.iOS Chart](Axis_images/labelextent.png)

### Grid lines customization

The [`ShowMajorGridLines`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_ShowMajorGridLines) and [`ShowMinorGridLines`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_ShowMinorGridLines) properties are used to control the visibility of grid lines. [`MajorGridLineStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_MajorGridLineStyle) and [`MinorGridLineStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_MinorGridLineStyle) properties in axis are used to customize the major grid lines and minor grid lines of an axis respectively. They provide options to change the width, dashes, color of grid lines. By default minor grid lines will not be visible. 

{% highlight c# %}

yAxis.ShowMajorGridLines    = true;

yAxis.ShowMinorGridLines	= true;

yAxis.MinorTicksPerInterval	= 1;

{% endhighlight %}

![Axis grid lines customization support in Xamarin.iOS Chart](Axis_images/GridLineStyle.png)

### Tick lines customization

The [`MajorTickStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_MajorTickStyle) and [`MinorTickStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_MinorTickStyle) properties in axis are used to customize the major tick lines of an axis and minor tick lines of an axis respectively. They provide options to change the [`LineWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLineStyle.html#Syncfusion_SfChart_iOS_SFLineStyle_LineWidth), [`LineSize`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxisTickStyle.html#Syncfusion_SfChart_iOS_SFAxisTickStyle_LineSize), [`LineColor`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFLineStyle.html#Syncfusion_SfChart_iOS_SFLineStyle_LineColor) and [`MinorTicksPerInterval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFRangeAxisBase.html#Syncfusion_SfChart_iOS_SFRangeAxisBase_MinorTicksPerInterval) of tick lines. By default minor tick lines will not be visible.

{% highlight c# %}

SFNumericalAxis yAxis           = new SFNumericalAxis ();

chart.SecondaryAxis             = yAxis;

yAxis.MajorTickStyle.LineSize   = new NSNumber (7);

yAxis.MajorTickStyle.LineWidth  = new NSNumber (3);

yAxis.MajorTickStyle.LineColor  = UIColor.Red;

yAxis.ShowMinorGridLines        = true;

yAxis.MinorTicksPerInterval     = 1;

yAxis.MinorTickStyle.LineSize   = new NSNumber (5);

yAxis.MinorTickStyle.LineWidth  = new NSNumber (2);

yAxis.MinorTickStyle.LineColor  = UIColor.Green;

{% endhighlight %}


![Axis tick lines customization support in Xamarin.iOS Chart](Axis_images/TickStyle.png)


### Customize individual axis elements

The [`RangeStyles`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_RangeStyles) can be used to customize the gridlines, ticks and axis labels for a specific region of [`SFAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html). The following properties are used to customize the specific range in an axis:

* [`Start`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAxisRangeStyle.html#Syncfusion_SfChart_iOS_ChartAxisRangeStyle_Start) - Sets the start range of an axis
* [`End`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAxisRangeStyle.html#Syncfusion_SfChart_iOS_ChartAxisRangeStyle_End) - Sets the end range of an axis
* [`MajorGridLineStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAxisRangeStyle.html#Syncfusion_SfChart_iOS_ChartAxisRangeStyle_MajorGridLineStyle) - Customizes the major grid lines of an axis.
* [`MinorGridLineStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAxisRangeStyle.html#Syncfusion_SfChart_iOS_ChartAxisRangeStyle_MinorGridLineStyle) - Customizes the minor grid lines of an axis.
* [`MajorTickStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAxisRangeStyle.html#Syncfusion_SfChart_iOS_ChartAxisRangeStyle_MajorTickStyle) - Customizes the major tick lines of an axis.
* [`MinorTickStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAxisRangeStyle.html#Syncfusion_SfChart_iOS_ChartAxisRangeStyle_MinorTickStyle) - Customizes the minor tick lines of an axis.
* [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAxisRangeStyle.html#Syncfusion_SfChart_iOS_ChartAxisRangeStyle_LabelStyle) - Customizes the axis labels for a specific range.

{% highlight c# %}

SFNumericalAxis  numericalAxis = new SFNumericalAxis () { Minimum = new NSNumber (15), Maximum = new NSNumber (27) };

ChartAxisRangeStyleCollection axisRangeStyles = new ChartAxisRangeStyleCollection();

ChartAxisRangeStyle rangeStyle = new ChartAxisRangeStyle() { Start = 15, End = 21};

rangeStyle.MajorGridLineStyle = new SFAxisGridLineStyle() { LineColor = UIColor.FromRGB(9, 110, 191), LineWidth = 3 };

rangeStyle.LabelStyle = new SFAxisLabelStyle() { Color = UIColor.FromRGB(9, 110, 191)), Font = UIFont.BoldSystemFontOfSize(10) }; 

....

axisRangeStyles.Add(rangeStyle);

{% endhighlight %}

![Individual axis elements customization support in Xamarin.iOS Chart](Axis_images/AxisRangeCustomize.png)

### Inversing axis

Axis can be inversed using the [`IsInversed`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_IsInversed) property of axis. Default value of [`IsInversed`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_IsInversed) property is `False`.


{% highlight c# %}

chart.SecondaryAxis.IsInversed = true; 
{% endhighlight %}


![Axis inverse support in Xamarin.iOS Chart](Axis_images/IsInversed.png)

### Placing axes at the opposite side

The [`OpposedPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_OpposedPosition) property of axis can be used to place the axis at the opposite side of its default position. Default value of [`OpposedPosition`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_OpposedPosition) property is `False`. 

{% highlight c# %}

chart.SecondaryAxis.OpposedPosition = true;

{% endhighlight %}

![Opposed axis support in Xamarin.iOS Chart](Axis_images/OpposedPosition.png)

### Offset the rendering

The [`PlotOffset`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_PlotOffset) property is used to offset the rendering of the axis at start and end position. The following code snippet demonstrates to apply the plot offset to both x and y axes.

{% highlight c# %}

Chart.PrimaryAxis = new SFCategoryAxis() { PlotOffset = 30 };

Chart.SecondaryAxis = new SFNumericalAxis() { PlotOffset = 30 };

{% endhighlight %}

![PlotOffset support for axis in Xamarin.iOS Chart](Axis_images/plotoffset.png)

#### PlotOffsetStart

The [`PlotOffsetStart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_PlotOffsetStart) property is used to offset the rendering of the axis at start position. The following code snippet demonstrates to apply the plot offset start to both x and y axes.

{% highlight c# %}

Chart.PrimaryAxis = new SFCategoryAxis() { PlotOffsetStart = 30 };

Chart.SecondaryAxis = new SFNumericalAxis() { PlotOffsetStart = 30 };

{% endhighlight %}

![PlotOffsetStart support for axis in Xamarin.iOS Chart](Axis_images/plotOffset_start.png)

#### PlotOffsetEnd

The [`PlotOffsetEnd`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_PlotOffsetEnd) property is used to offset the rendering of the axis at end position. The following code snippet demonstrates to apply the plot offset end to both x and y axes.

{% highlight c# %}

Chart.PrimaryAxis = new SFCategoryAxis() { PlotOffsetEnd = 30 };

Chart.SecondaryAxis = new SFNumericalAxis() { PlotOffsetEnd = 30 };

{% endhighlight %}

![PlotOffsetEnd support for axis in Xamarin.iOS Chart](Axis_images/PlotOffset_end.png)


### Maximum number of labels per 100 pixels

By default, a maximum of 3 labels are displayed for each 100 pixels in axis. The maximum number of labels that should be present within 100 pixels length can be customized using the [`MaximumLabels`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_MaximumLabels) property of an axis. This property is applicable only for automatic range calculation and will not work if you set value for [`Interval`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_Interval) property of an axis.

{% highlight c# %}

Chart.SecondaryAxis.MaximumLabels = 5;

{% endhighlight %}


![Maximum axis labels support in Xamarin.iOS Chart](Axis_images/MaxLabels.png)

### Auto scrolling

[`AutoScrollingDelta`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_AutoScrollingDelta) property is used to ensure that the specified range of data is always visible in the chart. It always shows the recently added data points at the end and scrolling will be reset to the end of the range whenever a new point is added.

By adding [`SFChartZoomPanBehavior`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartZoomPanBehavior.html) to the chart, you can scroll to see the previous datapoints.

### Auto scrolling delta type

In [`SFDateTimeAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFDateTimeAxis.html), you can apply auto scrolling delta value in [`Years`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimeDeltaType.html), [`Months`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimeDeltaType.html), [`Days`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimeDeltaType.html), [`Hours`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimeDeltaType.html), [`Minutes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimeDeltaType.html), [`Seconds`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimeDeltaType.html) and [`Milliseconds`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartDateTimeDeltaType.html) by setting [`AutoScrollingDeltaType`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_AutoScrollingDelta) property.

### Auto scrolling mode

[`AutoScrollingMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_AutoScrollingMode) property can be used to determine whether the axis should be scrolled from start position or end position. The default value of [`AutoScrollingMode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_AutoScrollingMode) is [`End`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartAutoScrollingMode.html).

{% highlight c# %}

SFCategoryAxis primaryAxis = new SFCategoryAxis();

primaryAxis.AutoScrollingDelta = 3;

primaryAxis.AutoScrollingMode = ChartAutoScrollingMode.Start;

chart.PrimaryAxis = primaryAxis;

{% endhighlight %}

## Axis Crossing

Axis can be positioned anywhere in the chart area by using [`CrossesAt`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_CrossesAt) property. This property specifies where the horizontal axis should intersect or cross the vertical axis or vice-versa. Default value of [`CrossesAt`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_CrossesAt) property is null.

{% highlight c# %}

chart.PrimaryAxis  = new SFCategoryAxis () 
{ 
    CrossesAt = 0 
};

chart.SecondaryAxis = new SFNumericalAxis() 
{ 
    CrossesAt = 8 
};

{% endhighlight %}

![AxisCrossing support in Xamarin.iOS Chart](Axis_images/AxisCrossing_img1.png)

### Crossing at specific axis

[`CrossingAxisName`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_CrossingAxisName) property takes axis name as input and determines the axis that used for crossing. By default, all the horizontal axes cross in primary Y axis, and all the vertical axes cross in primary X axis.

{% highlight c# %}

chart.PrimaryAxis  = new SFCategoryAxis() 
{
    CrossesAt = 0,
     
    Name = “PrimaryAxis”,

    CrossingAxisName = “SecondaryAxis”  
};

chart.SecondaryAxis =  new SFNumericalAxis() 
{ 
    CrossesAt = 2, 

    Name = “YAxis”,

    CrossingAxisName = “PrimaryAxis”
};

SFBubbleSeries series = new SFBubbleSeries();

series.YAxis = new SFNumericalAxis()
{
    CrossesAt = 8,

    Name = (NSString)"SecondaryAxis",

    CrossingAxisName = (NSString)"PrimaryAxis"
};

chart.Series.Add(series);

{% endhighlight %}

![Crossing at Specific axis support in Xamarin.iOS Chart](Axis_images/AxisCrossing_img2.png)

### Crossing in date time axis

For crossing in date time horizontal axis, date object should be provided as value for [`CrossesAt`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_CrossesAt) property of vertical axis.

{% highlight c# %}

chart.PrimaryAxis  = new SFDateTimeAxis() 
{ 
    CrossesAt = 0 
};

chart.SecondaryAxis =  new SFNumericalAxis() 
{
    CrossesAt = new DateTime(2003, 1, 1) 
};

{% endhighlight %}

![DateTimeAxis crosses at support in Xamarin.iOS Chart](Axis_images/AxisCrossing_img4.png)

### Positioning the axis elements while crossing

The [`RenderNextToCrossingValue`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_RenderNextToCrossingValue) property is used to determine whether the crossing axis should be placed at crossing position or not. The default value of [`RenderNextToCrossingValue`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_RenderNextToCrossingValue) property is true.

{% highlight c# %}

chart.PrimaryAxis = new SFCategoryAxis()
{
    CrossesAt = 0,

    RenderNextToCrossingValue = false

};

chart.SecondaryAxis = new SFNumericalAxis()
{
    CrossesAt = 5,
};

{% endhighlight %}

![Positioning axis elements while crossing support in Xamarin.iOS Chart](Axis_images/AxisCrossing_img5.png)

## Smart Axis Labels

Axis labels may overlap with each other based on chart dimensions and label size. The [`LabelsIntersectAction`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_LabelsIntersectAction) property of axis is used to avoid overlapping of axis labels. The default value of the [`LabelsIntersectAction`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_LabelsIntersectAction) is [`SFChartAxisLabelsIntersectAction.None`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisLabelsIntersectAction.html); other available values are [`MultipleRows`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisLabelsIntersectAction.html), [`Hide`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisLabelsIntersectAction.html), and [`Wrap`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChartAxisLabelsIntersectAction.html).

{% highlight c# %}

chart.PrimaryAxis.LabelsIntersectAction = SFChartAxisLabelsIntersectAction.MultipleRows;

{% endhighlight %}


![Smart axis labels support in Xamarin.iOS Chart](Axis_images/LabelsIntersectAction.png)

## Events

**LabelClicked**

The [`LabelClicked`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html) event is triggered when the axis label is clicked. The argument contains the following information.

* [`Label`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.ChartAxisLabelClickedEventArgs.html#Syncfusion_SfChart_iOS_SFAxis_ChartAxisLabelClickedEventArgs_Label) - Used to get the ChartAxisLabel, which contains axis label position and text.

**LabelCreated**

The [`LabelCreated`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html) event is triggered when the axis label is created. The argument contains [`AxisLabel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.LabelCreatedEventArgs.html#Syncfusion_SfChart_iOS_SFAxis_LabelCreatedEventArgs_AxisLabel) of [`ChartAxisLabel`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.ChartAxisLabel.html) which contains following properties.

* [`LabelContent`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.ChartAxisLabel.html#Syncfusion_SfChart_iOS_SFAxis_ChartAxisLabel_LabelContent) - used to get or set the content of label
* [`Position`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.ChartAxisLabel.html#Syncfusion_SfChart_iOS_SFAxis_ChartAxisLabel_Position) - used to get or set the position of the label
* [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.ChartAxisLabel.html#Syncfusion_SfChart_iOS_SFAxis_ChartAxisLabel_LabelStyle) - Used to customize the appearance of axis labels based on condition. The properties listed in [`Label customization`](https://help.syncfusion.com/xamarin-ios/sfchart/axis#label-customization) can be customized using LabelStyle property.
