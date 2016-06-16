---
layout: post
title: Getting Started with Syncfusion Calendar control for Xamarin.iOS
description: A quick tour to initial users on Syncfusion calendar control for Xamarin.iOS platform 
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Getting Started

This section explains you the steps required to render the Calendar control, to change selection mode, set min max dates and black out dates for the control. This section covers only the minimal features that you need to know to get started with the Calendar.

![](images/Calendar-iOS.png) 

## Creating your first Calendar in Xamarin.iOS.

This section provides a quick overview to work with the Calendar in Objective C. This example explains how to create an Calendar with different CalendarModes and SuggestionModes.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio {version number}\lib
And below assembly reference to the iOS unified project.
iOS-unifed\Syncfusion.SfCalendar.iOS.dll


### And and Configure the Calendar

The following steps explain on how to create an Calendar and configure its elements,

* Adding reference to Calendar.

{% highlight c# %}

	using Syncfusion.SFCalendar.iOS; 

{% endhighlight %}

* Create an instance of SfCalendar
   
{% highlight c# %}
	
	SfCalendar calendar = new SfCalendar();
	SetContentView(calendar);
	
{% endhighlight %}

### Enabling Multiple Selection 

To enable multiple selection, Change the selection type using `SelectionMode` property. Check the [Selection Mode](http://help.syncfusion.com/android/sfcalendar/selectionmode)  section for more details.

{% highlight c# %}

	SfCalendar calendar = new SfCalendar (this);
	calendar.SelectionMode=SelectionMode.MultiSelection;

{% endhighlight %}

### Setting blackout dates

Add the dates into `BlackOutDates` property, that needs to be disabled among visible dates. Check the [BlackOutDates](http://help.syncfusion.com/android/sfcalendar/blackoutdates) section for more details.

For instance add all the holiday dates to blackout dates property.

{% highlight c# %}

	SfCalendar  calendar = new SfCalendar (this);
	List<DateTime> black_dates = new List<DateTime>();
	for (int i = 0; i < 5; i++)
	{
		DateTime date = DateTime.Now.Date.AddDays(i+7);
		black_dates.Add(date);
    }
	calendar.BlackoutDates = black_dates;


{% endhighlight %}

### Restricting Dates

Set `MinDate` and `MaxDate` property to limit visible dates range. Check the [Min Max dates](http://help.syncfusion.com/android/sfcalendar/datenavigation-and-gesture#min-max-dates) section for more details.

{% highlight c# %}

	SfCalendar  calendar = new SfCalendar (this);
	calendar.MinDate = new DateTime(2014,4,1);
	calendar.MaxDate = new DateTime(2018,4,1);


{% endhighlight %}                                  
