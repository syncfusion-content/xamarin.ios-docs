---
layout: post
title: Populating Events in Syncfusion Calendar control for Xamarin.iOS
description: Learn how to populate events inside a cell and inline events descriptions
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Populating Events

SfCalendar control has built-in capability to display the events based on the Calendar events collection provided to `appointment` property. For events to be listed for a particular day, enable the inline feature in month view cell.

N> The default UI of the inline view with events will be like list of events with a dark background

![](images/inline_events.png)                                        


Inline event support can be toggled on / off with `ShowInLineEvent` property.

{% highlight c# %}

	 calendar.EnableInLine = true;

{% endhighlight %}

N> The Inline function will be available only in month view with single selection mode.

## Adding events using Collection

Calendar events collection can be provided to SfCalendar using the following steps.

The Appointment class has some basic properties such as `StartTime`, `EndTime` and `Subject`.

{% highlight C# %}
		   
		   NSMutableArray appCollection = new NSMutableArray();
            NSCalendar nscalendar = NSCalendar.CurrentCalendar;

            NSDate today = new NSDate();

            // Get the year, month, day from the date
            NSDateComponents startDateComponents = nscalendar.Components(
            NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);

            // Set the year, day, hour, minute, second
            startDateComponents.Year = 2015;
            startDateComponents.Month = 10;
            startDateComponents.Day = 9;
            startDateComponents.Hour = 10;
            startDateComponents.Minute = 0;
            startDateComponents.Second = 0;

            // Get the year, month, day from the date
            NSDateComponents endDateComponents = nscalendar.Components(
            NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);

            // Set the year, day, hour, minute, second
            endDateComponents.Year = 2015;
            endDateComponents.Month = 10;
            endDateComponents.Day = 9;
            endDateComponents.Hour = 12;
            endDateComponents.Minute = 0;
            endDateComponents.Second = 0;

            //setting start time for the event
            NSDate startDate = nscalendar.DateFromComponents(startDateComponents);

            //setting end time for the event
            NSDate endDate = nscalendar.DateFromComponents(endDateComponents);

            //Adding calendar appointment in calendar appointment collection 
            appCollection.Add(new SFAppointment()
            {
                StartTime = startDate,
                EndTime = endDate,
                Subject = (NSString)"Client Meeting",
                AppointmentBackground = UIColor.Blue
            });

		   
{% endhighlight %}

* Create the collection of the Calendar events by setting required details using above mentioned properties for each events and assign the collection to appointment property.

{% highlight c# %}

	 calendar.Appointments = appCollection;
	
{% endhighlight %}

![](images/inline_event.png)                                        



