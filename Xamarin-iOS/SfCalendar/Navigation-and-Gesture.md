---
layout: post
title: Date Navigation and Gestures | SfCalendar | Xamarin.iOS | Syncfusion
description: Learn the complete navigating and gestures support
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Navigation and Gesture

## Move to Date 

Visible dates can be moved to specific date using `MoveToDate` property available in `SfCalendar`. It will move to any specific month,year,decade,century view based on the `ViewMode`.

{% highlight c# %}

NSCalendar date = NSCalendar.CurrentCalendar;
NSDate today = new NSDate();
NSDateComponents movetoDateComponents = date.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);

movetoDateComponents.Year = 2015;
movetoDateComponents.Month = 4;
movetoDateComponents.Day = 1;

NSDate moveToDate = date.DateFromComponents(movetoDateComponents);
calendar.MoveToDate(moveToDate);

{% endhighlight %}

N>  The specified date should lie between MinDate and MaxDate, if the specified date is greater than MaxDate then the view will be moved to MaxDate and if the specified date is lesser than the MinDate then the view will be moved to MinDate.

## Toggle  navigation

This navigation, using touch gesture can be enabled and disabled using `NavigationEnable` property available in `SfCalendar` control. By default, `NavigationEnable` property is enabled.

N> By default, `SfCalendar` views can be moved backwards and forwards using touch swipe gesture. 

{% highlight c# %}

calendar.ViewMode = SFCalendarViewMode.SFCalendarViewModeMonth;
calendar.EnableNavigation = false;

{% endhighlight %}
