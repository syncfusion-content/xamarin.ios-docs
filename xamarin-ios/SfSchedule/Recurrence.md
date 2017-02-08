---
layout: post
title: Recursive patterns and appointments in Schedule.
description: How to create an recurrence appointment in Schedule control.
platform: xamarin.iOS
control: SfSchedule
documentation: ug
---

# Recurrence

Recursive appointments can be created by enabling `IsRecursive` property in Schedule appointments, to know more about adding appointments in the control, refer `ScheduleAppointment`.

And then need to set the RecurrenceRule to populate the required recursive appointment collection in a specific pattern.RRULE can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

Recursive appointment can be created in any recurrence patterns, for instance, some events can be repeated every week such as “Server maintenance”, where as some on them may repeat every year like wedding anniversary. 

## Recurrence Pattern

  * Recurrence pattern used in the control are in iCal standard 
  * Schedule control supports all four types of recurrence patterns.
    * Daily Recurrence
    * Weekly Recurrence
    * Monthly Recurrence
    * Yearly Recurrence

## RRULE generator

`RecurrenceGenerator`/ `RecurrenceBuilder` is available with the control to create RRULE. RRULE can be easily created through this engine by simple APIs available.The generated RRULE need to be assigned to the appointment’s `RecurrenceRule` property.

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;
    NSDate today = new NSDate ();
    NSMutableArray appCollection = new NSMutableArray ();
    NSCalendar calendar = NSCalendar.CurrentCalendar;

    // Get the year, month, day from the date
    NSDateComponents components = calendar.Components (
    NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);

    // Set the hour, minute, second
    components.Hour = 10;
    components.Minute = 0;
    components.Second = 0;
    // Get the year, month, day from the date
    NSDateComponents endDateComponents = calendar.Components (NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
    // Set the hour, minute, second
    endDateComponents.Hour = 12;
    endDateComponents.Minute = 0;
    endDateComponents.Second = 0;
    NSDate startDate = calendar.DateFromComponents (components);
    NSDate endDate = calendar.DateFromComponents (endDateComponents);

    ScheduleAppointment appointment = new ScheduleAppointment ();
    appointment.StartTime = startDate;
    appointment.EndTime = endDate;
    components.Day = components.Day + 1;
    endDateComponents.Day = endDateComponents.Day + 1;
    appointment.Subject = (NSString)"Client Meeting";
    appointment.AppointmentBackground = UIColor.Red;
    
{% endhighlight %}

The RRule is assigned to the created ScheduleAppointment as given below.

{% highlight c# %}

    //Setting Recurrence Rule
    appointment.RecurrenceRule = (NSString)@"FREQ=DAILY;INTERVAL=2;COUNT=25";
    appointment.IsRecursive = true;
    //Adding Appointment Collection 
    appCollection.Add (appointment);
    schedule.Appointments = appCollection;

    this.AddSubview (schedule);
    this.control = this;

{% endhighlight %}

![](Recurrence_images/Recurrence_iOS.png)