---
layout: post
title: Label Support for Syncfusion RangeSlider control for Xamarin.iOS
description: Learn how to set label and their positions in RangeSlider control
platform: Xamarin.iOS
control: RangeSlider
documentation: ug
---

# Labels

SfRangeSlider provides option to show or hide the label and position customization.

## Show Value Label

This property allows us to display labels for the ticks. When it sets to true, it displays the label for all the ticks based on the `ValuePlacement` property.

N> The default value of the `ShowValueLabel` property is false.

{% tabs %}

{% highlight c# %}

	rangeSlider.ShowValueLabel= true;

{% endhighlight %}

{% endtabs %}

## Set Custom Label

To display custom labels, `ShowCustomLabel` property should be set to true and need to populate the `CustomLabels` property with observable collection of items by specifying the custom labels for corresponding values.

{% tabs %}

{% highlight c# %}
	
	 SFRangeSlider rangeSlider; 
	 public RangeSliderPage ()
     {
           NSMutableArray<SFLabelItems> labels = new NSMutableArray<SFLabelItems>();
		   labels.Add(new SFLabelItems() { Label = (NSString)"Min", Value = 0 });
		   labels.Add(new SFLabelItems() { Label = (NSString)"Max", Value = 100 });
		   rangeSlider = new SFRangeSlider ();
           rangeSlider.HeightRequest = 400;
           rangeSlider.ShowCustomLabel = true;
           rangeSlider.CustomLabel = labels;

	 }

{% endhighlight %}

{% endtabs %}


## Value Placement

The `ValuePlacement` property describes the position of the Value respective to ticks. 

Available options for this property are:

* BottomRight

* TopLeft

{% tabs %}

{% highlight c# %}

	rangeSlider.ValuePlacement=SFValuePlacement.SFValuePlacementTopLeft;

{% endhighlight %}

{% endtabs %}

![](images/Value-TopLeft .png)

{% tabs %}

{% highlight c# %}

	rangeSlider.ValuePlacement=SFValuePlacement.SFValuePlacementBottomRight;

{% endhighlight %}

{% endtabs %}

![](images/Value-BottomRight.png)

## Label Placement

The `LabelPlacement` property describes the position of the labels respective to ticks. 

Available options for this property are:

* BottomRight

* TopLeft

{% tabs %}

{% highlight c# %}

	rangeSlider.LabelPlacement=SFLabelPlacement.SFLabelPlacementTopLeft;

{% endhighlight %}

{% endtabs %}
