---
layout : post
title : Overview of Syncfusion Carousel control for Xamarin.Forms
description : Overview and key features of Carousel control
platform : Xamarin
control : Carousel
documentation : ug
---

# Linear Arrangement

The Carousel items can be populated in the view in a stacked linear layout by setting the `ViewMode` property to Linear. The present option is `Default`.

{% tabs %}

{% highlight C# %}

	carousel.ViewMode = ViewMode.Linear;

{% endhighlight %}

{% endtabs %}


N> It is important to include Xamarin.Android.Support.v17.Leanback library to use carousel linear mode in Android platform.



