---
layout: post
title: Binding Appointments in Schedule using Collections and DataSource.
description: How to bind an appointment of Schedule control.
platform: xamarin.iOS
control: SfSchedule
documentation: ug
---

# Data Bindings 

Schedule control has an built-in capability to handle the appointment arrangement internally based on the `ScheduleAppointment` collections. `ScheduleAppointment` is a class, which holds the details about the appointment to be rendered in schedule. Schedule Appointments collection can be provided to schedule using the following method.

## Adding ScheduleAppointments using Collection

`ScheduleAppointment` has some basic properties such as StartTime, EndTime, Subject and some additional information about the appointment can be added using Color, Notes, Location, All Day, Recursive properties.

Create the collection of the `ScheduleAppointments` by setting required details using above mentioned properties for each appointment. And then assign the created collection to the `Appointment` property of `SfSchedule` as like in below code example.

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
    appCollection.Add (appointment);
    schedule.Appointments = appCollection;
    View.AddSubview(sfschedule);

{% endhighlight %}

### Adding AllDayAppointments 

AllDayAppointment is for setting appointmet for fullday by using `ShowAllDay` property in the `ScheduleAppointment`. Create the collection of the `ScheduleAppointments` by setting required details using above mentioned properties for each appointment. And then assign the created collection to the `Appointment` property of `SfSchedule` as like in below code example.

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
    appCollection.Add (appointment);
    schedule.Appointments = appCollection;
    View.AddSubview(sfschedule);

{% endhighlight %}

### Adding Recurrence Appointments  

Recursive appointments can be created by enabling `IsRecursive` property in Schedule appointments, to know more about adding appointments in the control, refer `ScheduleAppointment`.

And then need to set the RecurrenceRule to populate the required recursive appointment collection in a specific pattern.RRULE can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

Recursive appointment can be created in any recurrence patterns, for instance, some events can be repeated every week such as “Server maintenance”, where as some on them may repeat every year like wedding anniversary. 

To know more about customization of all day appointment panel refer [Recurrence Appointments](/xamarin-ios/sfschedule/Recurrence "Recurrence Pattern")

### Appointment Editor

Appointments can be edit using this Appointmenteditor by tapping the Appointment using `ScheduleCellTapped`event and set the required properties of `ScheduleAppointment` for editing, To know more about Appointment Editor please refer the KB (Knowledge Base).

## Appointment Customization

Schedule views are designed as per the native calendar control with some enriched user interface for the control interaction and usability. You can customize the Schedule as per the requirement using Cutsomization support. 

To know more about customization of all day appointment panel refer [View Customization](/xamarin-ios/sfschedule/appearance-and-styling "View Customization")

![](PopulatingAppointments_images/GettingStarted_iOS.png)


