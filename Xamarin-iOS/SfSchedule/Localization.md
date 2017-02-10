---
layout: post
title: Localization of Schedule
description: How to Localize the contents of Schedule control.
platform: xamarin.iOS
control: SfSchedule
documentation: ug
---

# Localization

Schedule control is available with complete localization support . Localization can be specified by setting the `Locale` property of the control. In the format of `Language code`.  Based on the locale specified the strings in the control such as Date, time, days are localized accordingly. As the subject of the appointments are given in the application level, it can be set as localized strings as per the requirement. 

## Locale

 Based on the locale specified the strings in the control such as Date, time, days are localized accordingly. By default schedule control is available with `en-US` locale. 

{% highlight c# %}

    schedule.Locale =  new NSLocale("fr");

{% endhighlight %}

>**NOTE**: AM/PM in the timeline will not be localized in the Schedule views.

![](LocalizationGlobalization_images/Localization.png)

