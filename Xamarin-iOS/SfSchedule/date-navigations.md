---
layout: post
title: Dates, Navigations and Gestures for syncfusion Schedule in iOS
description: How to Navigate date, enable or disable navigation and other functionalities of Schedule control in Xamarin.iOS.
platform: xamarin.iOS
control: SfSchedule
documentation: ug
---

# Date Navigations

## Enabling Navigation 
By default, Schedule views can be moved backwards and forwards using touch swipe gesture. This navigation gesture can be enabled or disabled by setting [EnableNavigation](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_EnableNavigation) property of `SfSchedule`. By default, it is enabled.

{% tabs %}
{% highlight c# %}
//disabling navigation gesture
schedule.EnableNavigation = false;
{% endhighlight %}
{% endtabs %}


## Programmatically change to specific dates 
Visible dates can be moved to specific date using [MoveToDate](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_MoveToDate_Foundation_NSDate_) method available in `SfSchedule`. It will move to any specific date if the schedule view is Day View, similarly it will move to the specific week if it is week view and to specific month if it is month view

{% tabs %}
{% highlight c# %}
NSDate date = new NSDate();
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
calendar.TimeZone = NSTimeZone.FromGMT(NSTimeZone.LocalTimeZone.GetSecondsFromGMT);
// Get the year, month, day from the date
NSDateComponents components = calendar.Components(
NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, date);
// Set the hour, minute, second
components.Month = 3;
components.Hour = 10;
components.Minute = 0;
components.Second = 0;
NSDate moveToDate = calendar.DateFromComponents(components);
schedule.MoveToDate(moveToDate);
{% endhighlight %}
{% endtabs %}

>**NOTE**
The specified date should lies between `MinDisplayDate` and `MaxDisplayDate` , if  the specified date is greater than `MaxDisplayDate` then the view moved to `MaxDisplayDate` similarly if the specified date is lesser than the `MinDisplayDate` then the view moved to `MinDisplayDate`.

## Programmatically change to adjacent dates.
By default the date can be navigated to next and previous view using touch gesture, by swiping the control in right to left and right to left direction. The view can be also changed programmatically using [Forward](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_Forward) and [Backward](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_Backward) method available in `SfSchedule`. 

*  	Forward
*	Backward

### Forward
You can use the `Forward` method for viewing the next immediate visible dates in the SfSchedule. It will move to next month if the schedule view is month, similarly it will move to next week for week view and next day for day view.

{% tabs %}
{% highlight c# %}
//Viewing next immediate visible dates
schedule.Forward();
{% endhighlight %}
{% endtabs %}

>**NOTE**
It can be navigated until it reaches the Min Max dates.

### Backward
You can use the `Backward` method for viewing the previous immediate visible dates in the `SfSchedule`. It will move to previous month if the schedule view is month, similarly it will move to previous week for week view and previous day for day view.

{% tabs %}
{% highlight c# %}
           //Viewing previous immediate visible dates
            schedule.Backward();
{% endhighlight %}
{% endtabs %}

>**NOTE**
It can be navigated until it reaches the Min Max dates.

## Range for visible dates
Visible dates can be restricted between certain range of dates, using [MinDisplayDate](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_MinDisplayDate)  and [MaxDisplayDate](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_MaxDisplayDate)  property in `SfSchedule`. It is applicable in all the schedule views.

### Minimum Display Date
`MinDisplayDate` will restrict date navigations features of `Backward`, `MoveToDate` and also can’t swipe the control using touch gesture beyond the min max date range. Thus, Inline and selection feature in month view will works only within the min max date range.

{% tabs %}
{% highlight c# %}
SFSchedule schedule= new SFSchedule ();
schedule.ScheduleView = SFScheduleView.SFScheduleViewMonth;
NSDate today = new NSDate ();
NSMutableArray appCollection = new NSMutableArray ();
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
calendar.TimeZone = NSTimeZone.FromGMT(NSTimeZone.LocalTimeZone.GetSecondsFromGMT);
// Get the year, month, day from the date
NSDateComponents components = calendar.Components (NSCalendarUnit.Year |
                                                   NSCalendarUnit.Month |
                                                   NSCalendarUnit.Day, today);
// Set the hour, minute, second
components.Month=3;
components.Hour = 10;
components.Minute = 0;
components.Second = 0;
// Get the year, month, day from the date
NSDateComponents endDateComponents = calendar.Components (NSCalendarUnit.Year |
                                                          NSCalendarUnit.Month-1 |
                                                          NSCalendarUnit.Day, today);
// Set the hour, minute, second
endDateComponents.Year=2015;
endDateComponents.Month = 11;
endDateComponents.Hour = 12;
endDateComponents.Minute = 0;
endDateComponents.Second = 0;
NSDate minDate = calendar.DateFromComponents (components);
schedule.MinDisplayDate = minDate;
{% endhighlight %}
{% endtabs %}

### Maximum Display Date
`MaxDisplayDate` will restrict date navigations features of `Forward`, `MoveToDate` and also can’t swipe the control using touch gesture beyond the max date range. Thus, Inline and selection in month view will works only within the max date range.

{% tabs %}
{% highlight c# %}
SFSchedule schedule= new SFSchedule ();
NSDate today = new NSDate ();
NSMutableArray appCollection = new NSMutableArray ();
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
calendar.TimeZone = NSTimeZone.FromGMT(NSTimeZone.LocalTimeZone.GetSecondsFromGMT);
// Get the year, month, day from the date
NSDateComponents components = calendar.Components (NSCalendarUnit.Year |
                                                   NSCalendarUnit.Month |
                                                   NSCalendarUnit.Day, today);
// Set the hour, minute, second
components.Month=3;
components.Hour = 10;
components.Minute = 0;
components.Second = 0;
// Get the year, month, day from the date
NSDateComponents endDateComponents = calendar.Components (NSCalendarUnit.Year |
                                                          NSCalendarUnit.Month-1 |
                                                          NSCalendarUnit.Day, today);
// Set the hour, minute, second
endDateComponents.Year=2025;
endDateComponents.Month = 11;
endDateComponents.Hour = 12;
endDateComponents.Minute = 0;
endDateComponents.Second = 0;
NSDate maxDate = calendar.DateFromComponents (components);
schedule.MaxDisplayDate = maxDate;
{% endhighlight %}
{% endtabs %}

## VisibleDatesChanged event
You can get the visible dates of the Schedule using [VisibleDatesChanged](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html) in `SfSchedule`. It is applicable in all the schedule views.The event handler receives an argument of type [VisibleDatesChangedEventArgs](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.VisibleDatesChangedEventArgs.html) containing [VisibleDates](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.VisibleDatesChangedEventArgs.html#Syncfusion_SfSchedule_iOS_VisibleDatesChangedEventArgs_VisibleDates).

{% tabs %}
{% highlight c# %} 
schedule.VisibleDatesChanged += Schedule_VisibleDatesChanged;

...

void Schedule_VisibleDatesChanged(object sender, VisibleDatesChangedEventArgs e)
{
    var visibleDates = e.VisibleDates;
}
{% endhighlight %}
{% endtabs %}

`VisibleDatesChanged` event will be triggered when view is swiped back or forth and also when schedule view is switched dynamically.

You can add appointments on demand based on the visible date range in this event by setting Appointments property to schedule in the VisibleDatesChanged event.

{% tabs %}
{% highlight c# %}
void Schedule_VisibleDatesChanged(object sender, VisibleDatesChangedEventArgs e)
{
    schedule.Appointments = scheduleAppointmentCollection;
}
{% endhighlight %}
{% endtabs %}

You can also move to specific time of the day or current time of day when view is swiped by setting specific time in MoveToDate property in the VisibleDatesChanged event. Such that when the schedule view is swiped, it moves to the mentioned time.  

{% tabs %}
{% highlight c# %}
schedule.VisibleDatesChanged += Schedule_VisibleDatesChanged;

...

void Schedule_VisibleDatesChanged(object sender, VisibleDatesChangedEventArgs e)
{
    NSDate date = e.VisibleDates.GetItem<NSDate>(0);
    NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
    calendar.TimeZone = NSTimeZone.FromGMT(NSTimeZone.LocalTimeZone.GetSecondsFromGMT);

    // Get the year, month, day from the date
    NSDateComponents components = calendar.Components(NSCalendarUnit.Year |
                                                      NSCalendarUnit.Month |
                                                      NSCalendarUnit.Day, date);
    // Set the hour, minute, second
    components.Hour = 10;
    components.Minute = 0;
    components.Second = 0;
    NSDate moveToDate = calendar.DateFromComponents(components);
    schedule.MoveToDate(moveToDate);
}
{% endhighlight %}
{% endtabs %}

