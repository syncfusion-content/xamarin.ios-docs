---
layout: post
title: Label Support for Syncfusion RangeSlider control for Xamarin.iOS
description: Learn how to set label and their positions in RangeSlider control
platform: Xamarin.iOS
control: RangeSlider
documentation: ug
---

# Labels

## ShowValueLabel

This property allows us to display labels for the ticks. When it sets to true, it displays the label for all the ticks based on the `ValuePlacement` property.

N> The default value of the `ShowValueLabel` property is false.

{% highlight c# %}

	sfRangeSlider.ShowValueLabel= True;

{% endhighlight %}

## CustomLabel

To display custom labels, `ShowCustomLabel` property should be set to true and need to populate the `CustomLabels` property with observable collection of items by specifying the custom labels for corresponding values.

{% highlight c# %}
	
	 SfRangeSlider RangeSlider; 
	 ObservableCollection<Items>  customCollection;
	 public RangeSliderPage ()
     {
       	customCollection = new ObservableCollection<Items> ();
           customCollection.Add(new Items(){Label = "Min", Value= 0});
           customCollection.Add(new Items() { Label = "Max", Value = 100 });
		   RangeSlider = new SfRangeSlider ();
           RangeSlider.HeightRequest = 400;
           RangeSlider.ShowCustomLabel = true;
           RangeSlider.CustomLabels = customCollection

	 }

{% endhighlight %}


## ValuePlacement

The `ValuePlacement` property describes the position of the Value respective to ticks. 

Available options for this property are:

* BottomRight

* TopLeft

{% highlight c# %}

	sfRangeSlider.ValuePlacement=ValuePlacement.TopLeft;

{% endhighlight %}

![](images/value-TopLeft.png)

{% highlight c# %}

	sfRangeSlider.ValuePlacement=ValuePlacement.BottomRight;

{% endhighlight %}

![](images/Value-BottomRight.png)

## LabelPlacement

The `LabelPlacement` property describes the position of the labels respective to ticks. 

Available options for this property are:

* BottomRight

* TopLeft

{% highlight c# %}

	sfRangeSlider.LabelPlacement=LabelPlacement.TopLeft;

{% endhighlight %}
