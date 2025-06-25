---

layout: post
title: Range Selection in Syncfusion® SfRating for Xamarin.iOS
description: Learn how to perform range selection with custom views in the Rating control
platform: xamarin.ios
control: Rating
documentation: ug

---

# View Range Selection

When using CustomView in SfRating, only one item will be rated by default. If you need to change the appearance of all rated CustomView items, use the `EnableViewRangeSelection` boolean property to enable range selection behavior.

> **Note:** The `EnableViewRangeSelection` property is used only for CustomViews.

{% tabs %}

{% highlight C# %}

    rating.EnableCustomView = true;
    rating.EnableViewRangeSelection = true;

{% endhighlight %}

{% endtabs %}

![SfRating EnableViewRangeSelection](images/enableviewrangeselection.png)
