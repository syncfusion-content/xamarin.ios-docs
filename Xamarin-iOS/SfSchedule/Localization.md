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

![](LocalizationGlobalization_images/LocalizationGlobalization1.jpeg)

## Schedule Custom String Localization

Schedule has a built-in support for localizing the Custom Strings in it by specifying the corresponding string’s key and value in the `Localizable.strings` in the application.

### AllDay and No events Text
For an example in schedule there is a string `No Events` in Schedule Month View Inline. To localize the string, specify the key (“No Events”) and assign the corresponding localized string to it in `Localizable.strings` file. 

### Appointment Localization
Schedule search for the key in corresponding language `Localizable.strings` file and displays the corresponding string in the schedule.

>**NOTE**: AM/PM in the timeline will not be localized in the Schedule views.

