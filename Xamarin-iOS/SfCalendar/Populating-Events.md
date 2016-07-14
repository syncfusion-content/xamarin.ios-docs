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

	calendar.ShowInLineEvent=true;

{% endhighlight %}

N> The Inline function will be available only in month view with single selection mode.

## Adding events using Collection

Calendar events collection can be provided to SfCalendar using the following steps.

The Appointment class has some basic properties such as `StartTime`, `EndTime` and `Subject`.

{% highlight C# %}
		   
		   SFCalendarInlineEvent event=new SFCalendarInlineEvent();
           DateTime d=new DateTime(2015,1,1);
           DateTime d1=new DateTime(2015,1,1);
           event.StartTime=d;
           event.EndTime=d1;
           event.Subject=(NSString)”Go to Meeting”;
           event.Color=UIColor.RED;
		   
{% endhighlight %}

* Create the collection of the Calendar events by setting required details using above mentioned properties for each events and assign the collection to appointment property.

{% highlight c# %}

	SFCalendarEventCollection eventsCollection = new SFCalendarEventCollection();
	eventsCollection.Add(events);
	
{% endhighlight %}

![](images/inline_event.png)                                        



