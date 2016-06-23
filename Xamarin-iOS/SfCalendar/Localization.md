---
layout: post
title: Localization support in Syncfusion Calendar control for Xamarin.iOS
description: Learn how to localize your calendar to regional language
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Localization

Calendar control is available with complete localization support.
 
Localization can be specified by setting the `Locale` property of the control using the format of Language code followed by Country code. Based on the locale specified, the strings in the control are localized accordingly.
 
N> By default, calendar control is available with en-US locale.

{% highlight c# %}

	calendar.Locale =  new NSLocale("fr-FR");

{% endhighlight %}

![](images/localisation.png)                                        

