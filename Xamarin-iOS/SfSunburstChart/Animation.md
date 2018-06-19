---
layout: post
title: Animation feature of Essential Xamarin.iOS SfSunburstChart
description: This section describes the animation feature of sunburst chart.
platform: Xamarin.iOS
control: SfSunburstChart
documentation: ug
---

# Animation

The sunburst chart provides animation on loading and whenever the item source changes. Animation can be enabled by setting the `EnableAnimation` property to true.

The following code shows enabling animation.

{% tabs %} 

{% highlight C# %} 

            SfSunburstChart sunburstChart = new SfSunburstChart();

            SunburstViewModel dataModel = new SunburstViewModel();
            sunburstChart.ItemsSource = dataModel.DataSource;
            sunburstChart.ValueMemberPath = "EmployeesCount";

            sunburstChart.EnableAnimation = true;
            sunburstChart.DataLabel.ShowLabel = true;

            sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "Country" });
            sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobDescription" });
            sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobGroup" });
            sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobRole" });

            sunburstChart.Frame = this.View.Frame;
            View.AddSubview(sunburstChart);   
          
{% endhighlight %}

{% endtabs %} 

## Duration

Animation duration can be controlled using the `AnimationDuration` property.

{% tabs %} 

{% highlight C# %} 

            SfSunburstChart sunburstChart = new SfSunburstChart();

            SunburstViewModel dataModel = new SunburstViewModel();
            sunburstChart.ItemsSource = dataModel.DataSource;
            sunburstChart.ValueMemberPath = "EmployeesCount";

            sunburstChart.EnableAnimation = true;
            sunburstChart.AnimationDuration = 2;
            sunburstChart.DataLabel.ShowLabel = true;

            sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "Country" });
            sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobDescription" });
            sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobGroup" });
            sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobRole" });

            sunburstChart.Frame = this.View.Frame;
            View.AddSubview(sunburstChart);

{% endhighlight %}

{% endtabs %} 

The following screenshot depicts animation of the sunburst chart with the specified duration.

![](Animation_images/Animate.gif)

