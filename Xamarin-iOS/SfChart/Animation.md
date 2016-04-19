---
layout: post
title: Animating chart series | SFChart | Xamarin.iOS | Syncfusion
description: Animation
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Animation

`SFChart` provides animation support for series. Series will be animated on loading data points and whenever the items source changes. Animation can be enabled by setting the `EnableAnimation` property as true and the animation duration can be handled by the `AnimationDuration` property, which are available in `SFSeries`.

{% highlight c# %}
SFColumnSeries series       = new SFColumnSeries ();
series.EnableAnimation      = true;
series.AnimationDuration    = 0.8;
{% endhighlight %}

