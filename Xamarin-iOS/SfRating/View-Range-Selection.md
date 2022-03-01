---

layout: post
title: Range selection in Syncfusion SfRating for Xamarin.iOS
description: Perform range selection with custom views in rating control
platform: Xamarin.iOS
control: Rating
documentation: ug

---

# View Range Selection

When using CustomView in SfRating, Only one item will be rated. If you need to change the view of all rated CustomView items, Use the `EnableViewRangeSelection` boolean property.

N> The EnableViewRangeSelection property is used only for CustomViews. 

{% tabs %}

{% highlight C# %}

    rating.EnableCustomView = true;
    rating.EnableViewRangeSelection = true;

{% endhighlight %}

{% endtabs %}

![SfRating EnableViewRangeSelection](images/enableviewrangeselection.png)
