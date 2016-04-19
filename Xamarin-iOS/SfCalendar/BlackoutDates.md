---
layout: post
title: BlackOut Dates support in Syncfusion Calendar control for Xamarin.iOS
description: Learn how to add black out dates for calendar
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Restricting Dates

## Min Max dates

Visible dates can be restricted between certain range of dates using `minDate` and `maxDate` properties available in calendar control. It is applicable in all the calendar views.

The inline feature in month view will work only within the min max date range.

N> Beyond the min max date range, following restrictions will be applied.

* Date navigations features of move to date will be restricted.

* Cannot swipe the control using touch gesture.

* Selection does not work for month view. 

* The tapped delegates will not be triggered while tapped on the month cell.  

{% highlight c# %}

	DateTime d1=new DateTime(2015,1,1);
	sfCalendar.MinDate=mindate;
	DateTime d2=new DateTime(2040,12,12);
	sfCalendar.MaxDate=d2;
	
{% endhighlight %}

## Blackout dates

In Calendar, BlackoutDates refers the disabled dates that restrict the user from selecting it. These dates will be marked with slanted Stripes. 

The BlackoutDays can be achieved in two ways. 

*	A date collection can be provided to set the `blackoutDates`. This is useful where one wants to block dates where holidays or any other events occur. 

*	By invoking the `addDatesInPast` method, all past dates will be blacked out till current date.

{% highlight c# %}

	List<DateTime> black_dates = new List<DateTime>();
	black_dates.Add (new DateTime(2015,11,3));
	black_dates.Add (new DateTime(2015,11,7));
	black_dates.Add (new DateTime(2015,11,15));
	black_dates.Add (new DateTime(2015,11,16));
	black_dates.Add (new DateTime(2015,11,26));
	black_dates.Add (new DateTime(2015,11,30));
	sfCalendar.BlackoutDates= black_dates ;
	
{% endhighlight %}

![](images/blackout_dates.png)                                        


N> This support is enabled only in month view and the dates that consists inline events will also be disabled, when they are blacked out.
