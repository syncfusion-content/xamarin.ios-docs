---
layout: post
title: Getting Started | SFChart | Xamarin.iOS | Syncfusion
description: getting started 
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Getting Started 

This section explains you the steps required to populate the Chart with data, title, add data labels and tooltips to the Chart. This section covers only the minimal features that you need to know to get started with the Chart.

## Adding Chart Reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio\{version number}\lib

N> Assemblies are available in unzipped package location in Mac.

You have to add the following assembly reference to the iOS unified project

ios-unifed\Syncfusion.SFChart.iOS.dll

## Initialize Chart

Import the SFChart namespace as shown below in your respective Page,

{% highlight C# %}
using Syncfusion.SfChart.iOS;
{% endhighlight %}

Then initialize an empty chart with two axes as shown below,

{% highlight C# %} 
public override void ViewDidLoad ()
{
    base.ViewDidLoad ();

    //Initialize the Chart with required frame. This frame can be any rectangle, which bounds inside the view.
    SFChart chart = new SFChart ();
    chart.Frame   = this.View.Frame;

    //Adding Primary Axis for the Chart.
    SFCategoryAxis primaryAxis = new SFCategoryAxis ();
    chart.PrimaryAxis          = primaryAxis;

    //Adding Secondary Axis for the Chart.
    SFNumericalAxis secondaryAxis = new SFNumericalAxis ();
    chart.SecondaryAxis           = secondaryAxis; 

    this.View.AddSubview (chart);
}
{% endhighlight %}

Run the project and check if you get following output to make sure you have configured your project properly to add SFChart.

![](Getting-Started_images/img1.png)

## Initialize view model

Now, let us define a simple data model that represents a data point in SfChart.

{% highlight C# %}
public class Person   
{   
    public string Name { get; set; }

    public double Height { get; set; }
}
{% endhighlight %} 

Next, create a view model class and initialize a list of `Person` objects as shown below,

{% highlight C# %}
public class ViewModel  
{
      public List<Person> Data { get; set; }      

      public ViewModel()       
      {
            Data = new List<Person>()
            {
                new Person { Name = "David", Height = 180 },
                new Person { Name = "Michael", Height = 170 },
                new Person { Name = "Steve", Height = 160 },
                new Person { Name = "Joel", Height = 182 }
            }; 
       }
 }
{% endhighlight %} 

## Populate Chart with data

As we are going to visualize the comparison of heights in the data model, add [`SFColumnSeries`]() to [`SFChart.Series`]() property, and then set the Data property of the above `ViewModel` to the [`SFColumnSeries.ItemsSource`]() property as shown below.

N> You need to set [`XBindingPath`]() and [`YBindingPath`]() properties, so that [`SFChart`]() would fetch values from the respective properties in the data model to plot the series.

{% highlight C# %}
//Initializing primary axis
SFCategoryAxis primaryAxis = new SFCategoryAxis();

primaryAxis.Title.Text = new NSString("Name");

chart.PrimaryAxis = primaryAxis;

//Initializing secondary Axis
SFNumericalAxis secondaryAxis = new SFNumericalAxis();

secondaryAxis.Title.Text = new NSString("Height (in cm)");

chart.SecondaryAxis = secondaryAxis;

//Initializing view model
ViewModel model = new ViewModel();

//Initializing column series
SFColumnSeries series = new SFColumnSeries();

series.ItemSource = model.Data;

series.XBindingPath = "Name";

series.YBindingPath = "Height";

chart.Series.Add(series);
{% endhighlight %}

## Add Title

You can add title to chart to provide quick information to the user about the data being plotted in the chart. You can set title using [`SFChart.Title`]() property as shown below.

{% highlight C# %} 
chart.Title.Text = "Chart";
{% endhighlight %}

Refer this [link]() to learn more about the options available in [`SFChart`]() to customize chart title.

## Enable data labels

You can add data labels to improve the readability of the chart. This can be achieved using [`SFSeries.DataMarker`]() property as shown below.

{% highlight C# %} 
series.DataMarker.ShowLabel = true;
{% endhighlight %}

Refer this [link]() to learn more about the options available in [`SFChart`]() to customize data markers.

## Enable legend

You can enable legend using [`SFChart.Legend`]() property as shown below,

{% highlight C# %} 
chart.Legend.Visible = true;
{% endhighlight %}

Additionally, you need to set label for each series using [`SFSeries.Label`]() property, which will be displayed in corresponding legend.

{% highlight C# %} 
series.Label = "Heights";
{% endhighlight %}

Refer this [link]() to learn more about the options available in [`SFChart`]() to customize legend.

## Enable tooltip

Tooltips are used to show information about the segment, when you tap on the segment. You can enable tooltip by setting [`SFSeries.EnableTooltip`]() property to true.

{% highlight C# %} 
series.EnableTooltip = true;
{% endhighlight %}

Refer this [link]() to learn more about the options available in [`SFChart`]() to customize tooltip.

This is how the final output looks like on iOS devices. You can also download the entire source code of this demo from this [link.]()

![](Getting-Started_images/img2.png)



