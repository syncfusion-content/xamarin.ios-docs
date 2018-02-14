---
layout: post
title: Localization of Schedule
description: How to Localize the contents of Schedule control.
platform: xamarin.iOS
control: SfSchedule
documentation: ug
---

# Localization

Schedule control is available with complete localization support. Localization can be specified by setting the [Locale](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~Locale.html) property of SfSchedule. In the format of `Language code`.

## Change default control language

Based on the `Locale` specified the strings in the control such as Date, time, days are localized accordingly.

By default, schedule control is available with en locale, which is English.


{% highlight c# %}   
    
          //setting locale for the control
            schedule.Locale = new NSLocale("fr");
 
{% endhighlight %}   
 

>**Note:** AM/PM in the timeline will not be localized in the Schedule views 

![](LocalizationGlobalization_images/Localization.png)   

## Change custom texts in the control.

You can localize custom text available in the control by adding equivalent localized string in the Localizable.strings file. 

![](LocalizationGlobalization_images/Localization_IOS.png)  

If an application requires multiple languages we can follow the below steps.

The procedure to use Localizable.Strings for multiple language
*	Translate the Localizable.Strings file to each language. 
*	Create three new .lproj folders under resource en.lproj, fr.lproj, de.lproj.
* 	Place the Localizable.Strings file in the respective language.lproj folders.


>**Note:** The corresponding .lproj folder loads only depends on the device configuration and locale.

