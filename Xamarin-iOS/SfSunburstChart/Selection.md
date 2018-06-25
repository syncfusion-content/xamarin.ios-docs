---
layout: post
title: Selection feature of Essential Xamarin.iOS SfSunburstChart
description: This section describes the segment selection.
platform: Xamarin.iOS
control: SfSunburstChart
documentation: ug
---

# Selection

The sunburst chart provides support to select or highlight the segments.

## Selection type

The `SelectionType` property allows you to select a segment based on the following categories:

* Child: Highlights the selected segment along with its children in all levels.
* Group: Highlights the entire group of the selected segment in a hierarchy.
* Parent: Highlights the parent of the selected segment in the hierarchy.
* Single: Highlights the selected segment alone.

### Child

The following code shows the `Child` selection type.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.SelectionSettings.EnableSelection = true;
            sunburstChart.SelectionSettings.Opacity = 0.5;
            sunburstChart.SelectionSettings.SelectionType = SelectionType.Child;            

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Child.jpg)

### Group

The following code shows the `Group` selection type.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.SelectionSettings.EnableSelection = true;
            sunburstChart.SelectionSettings.Opacity = 0.5;
            sunburstChart.SelectionSettings.SelectionType = SelectionType.Group;            

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Group.jpg)

### Parent

The following code shows the `Parent` selection type.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.SelectionSettings.EnableSelection = true;
            sunburstChart.SelectionSettings.Opacity = 0.5;
            sunburstChart.SelectionSettings.SelectionType = SelectionType.Parent;            

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Parent.jpg)

### Single

The following code shows the `Single` selection type.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.SelectionSettings.EnableSelection = true;
            sunburstChart.SelectionSettings.Opacity = 0.5;
            sunburstChart.SelectionSettings.SelectionType = SelectionType.Single;

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Single.jpg)

## Selection display mode

The selection display mode provides the following selection options to highlight the segments:

* By stroke
* By Color
* By opacity

### Opacity

This mode highlights the selected segment with the opacity specified in the `Opacity` property.

{% tabs %} 

{% highlight C# %} 

            sunburstChart.SelectionSettings.EnableSelection = true;
            sunburstChart.SelectionSettings.Opacity = 0.5;           
            sunburstChart.SelectionSettings.SelectionType = SelectionType.Group;
            sunburstChart.SelectionSettings.SelectionDisplayMode = SelectionDisplayMode.HighlightByOpacity;

{% endhighlight %}

{% endtabs %} 

![](Selection_images/Group.jpg)

### Color

This mode highlights the selected segment using the brush specified in the `SelectionBrush` property.

{% tabs %}

{% highlight C# %} 

            sunburstChart.SelectionSettings.EnableSelection = true;  
            sunburstChart.SelectionSettings.SelectionDisplayMode = SelectionDisplayMode.HighlightByColor;          
            sunburstChart.SelectionSettings.SelectionBrush = UIColor.Black;
            sunburstChart.SelectionSettings.SelectionType = SelectionType.Group;          

{% endhighlight %}

{% endtabs %} 

![](Selection_images/ColorSelection.png)

### Stroke

This mode highlights the selected segment by applying stroke to it. The color and thickness of the stroke can be customized using the `SelectionStrokeBrush` and `SelectionStrokeWidth` properties.

{% tabs %}

{% highlight C# %} 

            sunburstChart.SelectionSettings.EnableSelection = true;
            sunburstChart.SelectionSettings.SelectionDisplayMode = SelectionDisplayMode.HighlightByStroke;           
            sunburstChart.SelectionSettings.SelectionBrush = UIColor.Black;
            sunburstChart.SelectionSettings.SelectionType = SelectionType.Group;          

{% endhighlight %}

{% endtabs %} 

![](Selection_images/StrokeSelection.png)

## Events

### Selection Changed

This event occurs whenever you select the segment. You can get the selected segment details as argument from SunburstSelectionChangedEventArgs handler.

{% tabs %} 

{% highlight C# %}

            sunburstChart.SelectionSettings.EnableSelection = true;
            sunburstChart.SelectionSettings.SelectionDisplayMode = SelectionDisplayMode.HighlightByStroke;
            sunburstChart.SelectionSettings.SelectionType = SelectionType.Single;

            sunburstChart.SelectionChanged += SunburstChart_SelectionChanged; 

        private void SunburstChart_SelectionChanged(object sender, SunburstSelectionChangedEventArgs e)
        {
            if (e.SelectedSegment != null)
                e.SelectedSegment.Color = UIColor.Green;          
        }


{% endhighlight %}

{% endtabs %} 

![](Selection_images/Event.jpg)