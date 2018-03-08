---

layout: post
title: Populating Appointments in Syncfusion SfSchedule control for Xamarin.iOS
description: Learn how to Populate Appointments in SfSchedule control
platform: xamarin.ios
control: SfSchedule
documentation: ug

---


# Appointments

[ScheduleAppointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment.html) is a class, which holds the details about the appointment to be rendered in schedule. It has some basic properties such as [StartTime](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~StartTime.html), [EndTime](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~EndTime.html), [Subject](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Subject.html) and some additional information about the appointment can be added using [AppointmentBackground](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~AppointmentBackground.html), [Notes](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Notes.html), [Location](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Location.html), [All Day](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~IsAllDay.html), [Recurring properties](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties.html).

{% highlight c# %}
using Foundation;
using Syncfusion.SfSchedule.iOS; 

    //Creating an instance for SfSchedule control
        SFSchedule schedule = new SFSchedule();

    // Creating instance for schedule appointment collection
        NSMutableArray appCollection = new NSMutableArray();
        NSCalendar calendar = NSCalendar.CurrentCalendar;

        NSDate today = new NSDate();

    // Get the year, month, day from the date
        NSDateComponents startDateComponents = calendar.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
    
    // Set the hour, minute, second
        startDateComponents.Hour = 10;
        startDateComponents.Minute = 0;
        startDateComponents.Second = 0;

    // Get the year, month, day from the date
        NSDateComponents endDateComponents = calendar.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);

    // Set the hour, minute, second
        endDateComponents.Hour = 12;
        endDateComponents.Minute = 0;
        endDateComponents.Second = 0;

    //setting start time for the event
        NSDate startDate = calendar.DateFromComponents(startDateComponents);

    //setting end time for the event
        NSDate endDate = calendar.DateFromComponents(endDateComponents);

    //Adding schedule appointment in schedule appointment collection 
        appCollection.Add(new ScheduleAppointment()
            {
	            StartTime = startDate,
                EndTime = endDate,
                Subject = (NSString)"Client Meeting",
                Location = (NSString)"Hutchison road",
                AppointmentBackground = UIColor.Red
			});

    //Adding schedule appointment in schedule appointment collection 
        schedule.Appointments = appCollection;

        View.AddSubview(schedule); 

{% endhighlight %}

![](data_binding_images/appointment.png)

## Minimum Appointment Height

[MinHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~MinHeight.html) of an appointment is to set an arbitrary height to appointments when it has minimum duration, so that the subject can be readable.

{% highlight c# %}
 
 	    SFSchedule schedule = new SFSchedule();
        NSMutableArray appCollection = new NSMutableArray();
        NSCalendar calendar = NSCalendar.CurrentCalendar;
        NSDate today = new NSDate();
        NSDateComponents startDateComponents = calendar.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
        startDateComponents.Hour = 09;
        startDateComponents.Minute = 0;
        startDateComponents.Second = 0;
        NSDateComponents endDateComponents = calendar.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
        endDateComponents.Hour = 09;
        endDateComponents.Minute = 0;
        endDateComponents.Second = 0;
        NSDate startDate = calendar.DateFromComponents(startDateComponents);
        NSDate endDate = calendar.DateFromComponents(endDateComponents);
		NSDateComponents startDateComponents1 = calendar.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
        startDateComponents1.Hour = 11;
        startDateComponents1.Minute = 0;
        startDateComponents1.Second = 0;
        NSDateComponents endDateComponents1 = calendar.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
        endDateComponents1.Hour = 12;
        endDateComponents1.Minute = 0;
        endDateComponents1.Second = 0;
        NSDate startDate1 = calendar.DateFromComponents(startDateComponents1);
        NSDate endDate1 = calendar.DateFromComponents(endDateComponents1);
        appCollection.Add(new ScheduleAppointment()
            {
			    StartTime = startDate,
                EndTime = endDate,
                Subject = (NSString)"Client Meeting",
                AppointmentBackground = UIColor.FromRGB(216,0,115),
	            MinHeight=30
           });
		appCollection.Add(new ScheduleAppointment()
            {
			    StartTime = startDate1,
                EndTime = endDate1,
                Subject = (NSString)"Anniversary",
                AppointmentBackground = UIColor.FromRGB(162,193,57),
           });
        schedule.Appointments = appCollection;
        View.AddSubview(schedule);
		
{% endhighlight %}

![](data_binding_images/minheightios.png)

>**Note**:
* `MinHeight` value will be set, when the an appointment height (duration) value lesser than MinHeight. 
* Appointment height (duration) value will be set, when the appointment height (duration) value greater than `MinHeight`.
* TimeInterval value will be set, when Minimum Height greater than TimeInterval with lesser appointment height (duration).
* `MinHeight` has ScheduleAppointmentMapping Support.
* All day Appointment does not support `MinHeight`.

## Spanned Appointments
Spanned Appointment is an appointment which lasts more than 24 hours.

{% highlight c# %}

        using Foundation;
    using Syncfusion.SfSchedule.iOS; 

    //Creating an instance for SfSchedule control
            SFSchedule schedule = new SFSchedule();

    // Creating instance for schedule appointment collection
        NSMutableArray appCollection = new NSMutableArray();
        NSCalendar calendar = NSCalendar.CurrentCalendar;

        NSDate today = new NSDate();

    // Get the year, month, day from the date
        NSDateComponents startDateComponents = calendar.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
    
    // Set the hour, minute, second
        startDateComponents.Hour = 10;
        startDateComponents.Minute = 0;
        startDateComponents.Second = 0;

    // Get the year, month, day from the date
        NSDateComponents endDateComponents = calendar.Components(
        NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);

    // Set the date, hour, minute, second
        endDateComponents.Day = endDateComponents.Day + 2;
        endDateComponents.Hour = 12;
        endDateComponents.Minute = 0;
        endDateComponents.Second = 0;

    //setting start time for the event
        NSDate startDate = calendar.DateFromComponents(startDateComponents);

    //setting end time for the event
        NSDate endDate = calendar.DateFromComponents(endDateComponents);

    //Adding schedule appointment in schedule appointment collection 
        appCollection.Add(new ScheduleAppointment()
            {
	            StartTime = startDate,
                EndTime = endDate,
                Subject = (NSString)"Client Meeting",
                Location = (NSString)"Hutchison road",
                AppointmentBackground = UIColor.Red
			});

    //Adding schedule appointment in schedule appointment collection 
        schedule.Appointments = appCollection;

{% endhighlight %}

![](data_binding_images/span.png)

## All Day Appointments
All-Day appointment is an appointment which is scheduled for a whole day. It can be set by using `IsAllDay` property in the `ScheduleAppointment`.

{% highlight c# %}

    //Adding schedule appointment in schedule appointment collection 
        appCollection.Add(new ScheduleAppointment()
            {
            StartTime = startDate,
                EndTime = endDate,
                Subject = (NSString)"Client Meeting",
                Location = (NSString)"Hutchison road",
                AppointmentBackground = UIColor.Red,
                IsAllDay = true
        });
{% endhighlight %} 

### All-Day Appointment Panel
All-day appointment doesn't block out entire time slot in SfSchedule, rather it will render in separate layout exclusively for all-day appointment. It can be enabled by setting `ShowAllDay` property of `DayViewSettings`, `WeekViewSettings` and `WorkWeekViewSettings` of `DayView`, `WeekView` and `WorkWeekView` respectively.

{% highlight c# %}

        //Setting Schedule View
        schedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

	    //Creating Week View Settings for SfSchedule WeekView 
        WeekViewSettings weekViewSettings = new WeekViewSettings();
        weekViewSettings.ShowAllDay = true;
        schedule.WeekViewSettings = weekViewSettings;

{% endhighlight %} 

All-Day panel background can be customized by setting `AllDayAppointmentLayoutColor` 
of the respective view settings.

{% highlight c# %}

            weekViewSettings.AllDayAppointmentLayoutColor = UIColor.Gray; 

{% endhighlight %} 

![](data_binding_images/allday.png)

## Recurrence Appointment
Recurring appointment on a daily, weekly, monthly, or yearly interval. Recurring appointments can be created by enabling `IsRecursive` property in Schedule appointments.

### Recurrence Rule
The `RecurrenceRule` is a string value, that contains the details of the recurrence appointments like repeat type - daily/weekly/monthly/yearly, how many times it needs to be repeated, the interval duration and also the time period to render the appointment, etc.
`RecurrenceRule` has the following properties and based on this property value, the recurrence appointments are rendered in the SfSchedule control with its respective time period.

| PropertyName | Purpose |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| FREQ | Maintains the Repeat type value of the appointment. (Example: Daily, Weekly, Monthly, Yearly, Every week day) Example: FREQ=DAILY;INTERVAL=1 |
| INTERVAL | Maintains the interval value of the appointments. For example, when you create the daily appointment at an interval of 2, the appointments are rendered on the days Monday, Wednesday and Friday. (creates the appointment on all days by leaving the interval of one day gap) Example: FREQ=DAILY;INTERVAL=1 |
| COUNT | It holds the appointment’s count value. For example, when the recurrence appointment count value is 10, it means 10 appointments are created in the recurrence series. Example: FREQ=DAILY;INTERVAL=1;COUNT=10 |
| UNTIL | This property is used to store the recurrence end date value. For example, when you set the end date of appointment as 6/30/2014, the UNTIL property holds the end date value when the recurrence actually ends. Example: FREQ=DAILY;INTERVAL=1;UNTIL=8/25/2014 |
| BYDAY | It holds the “DAY” values of an appointment to render.For example, when you create the weekly appointment, select the day(s) from the day options (Monday/Tuesday/Wednesday/Thursday/Friday/Saturday/Sunday).  When Monday is selected, the first two letters of the selected day “MO” is stored in the “BYDAY” property.  When you select multiple days, the values are separated by commas. Example: FREQ=WEEKLY;INTERVAL=1;BYDAY=MO,WE;COUNT=10 |
| BYMONTHDAY | This property is used to store the date value of the Month while creating the Month recurrence appointment. For example, when you create a Monthly recurrence appointment in the date 3, it means the BYMONTHDAY holds the value 3 and creates the appointment on 3rd day of every month. Example: FREQ=MONTHLY;BYMONTHDAY=3;INTERVAL=1;COUNT=10 |
| BYMONTH | This property is used to store the index value of the selected Month while creating the yearly appointments. For example, when you create the yearly appointment in the Month June, it means the index value for June month is 6 and it is stored in the BYMONTH field.  The appointment is created on every 6th month of a year. Example: FREQ=YEARLY;BYMONTHDAY=16;BYMONTH=6;INTERVAL=1;COUNT=10 |
| BYSETPOS | This property is used to store the index value of the week. For example, when you create the monthly appointment in second week of the month, the index value of the second week (2) is stored in BYSETPOS. Example: FREQ=MONTHLY;BYDAY=MO;BYSETPOS=2;UNTIL=8/11/2014 |

### Recurrence Pattern
Recurrence pattern used in the control are in iCal standard. Schedule control supports all four types of [recurrence patterns](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties.html).

| RecurrenceType | RecurrenceProperties | Description |
|----------------|-------------------------|---------------------------------------------------------------|
| Daily | DailyNDays | Gets or sets the event to recur on a daily N intervals basis. |
|  | IsDailyEveryNDays | Checks whether the event occurs Daily Every N days. |
| Weekly | IsWeeklySunday | Checks whether the event occurs every Sunday of week |
|  | IsWeeklyMonday | Checks whether the event occurs every Monday of week |
|  | IsWeeklyTuesday | Checks whether the event occurs every Tuesday of week |
|  | IsWeeklyWednesday | Checks whether the event occurs every Wednesday of week |
|  | IsWeeklyThursday | Checks whether the event occurs every Thursday of week |
|  | IIsWeeklyFriday | Checks whether the event occurs every Friday of week |
|  | IsWeeklySaturday | Checks whether the event occurs every Saturday of week |
|  | NthWeek | Gets or sets the event only nth week of the year. |
|  | WeekDay | Gets or sets the event every week day. |
|  | WeeklyEveryNWeeks | Gets or sets the event every N Weeks. |
| Monthly | SpecificMonth | Gets or sets the event in a specific month. |
|  | SpecificMonthDay | Gets or sets the event in a specific month day. |
|  | IsMonthlySpecific | Checks whether the event is Monthly specific event |
|  | MonthlyEveryNMonths | Gets or sets the event every N Months. |
|  | MonthlyNthWeek | Gets or sets the event nth week of every month. |
|  | MonthlySpecificMonthDay | Gets or sets the event specific month day of Month. |
|  | MonthlyWeekDay | Gets or sets the event every week day of month. |
| Yearly | IsYearlySpecific | Checks whether the event is Yearly Specific. |
|  | YearlyEveryNYears | Gets or sets the event occurs every N Years. |
|  | YearlyGenericMonth | Gets or sets the event occurs in generic month. |
|  | YearlyNthWeek | Gets or sets the event occurs yearly nth week. |
|  | YearlySpecificMonth | Gets or sets the event occurs yearly specific month. |
|  | YearlySpecificMonthDay | Gets or sets the event occurs yearly specific month day. |
|  | YearlyWeekDay | Gets or sets the event occurs yearly week day. |
|  | EveryNYears | Gets or sets the event every N Years. |
| Common | IsRangeEndDate | Checks whether the event has Range end date |
|  | IsRangeNoEndDate | Checks whether the event has No Range end date |
|  | IsRangeRecurrenceCount | Checks whether the event has recurrence count. |
|  | RangeEndDate | Gets or sets the event range end date. |
|  | RangeStartDate | Gets or sets the event range start date. |
|  | RangeRecurrenceCount | Gets or sets the event range recurrence count. |
|  | IsSpecific | Checks whether the event occurs in Specific recurrence type. |

Find the following `RecurrenceRule` possibilities available in the Schedule control while creating the recurrence appointment.

| PossibilityType | Description | RecurrenceProperties | Examples |
|-----------------|----------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| Daily | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Daily, DailyNDays = 1, IsDailyEveryNDays = true, IsRangeNoEndDate = true | FREQ=DAILY; INTERVAL=1 |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Daily, DailyNDays = 1, IsDailyEveryNDays = true, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 15 | FREQ=DAILY; INTERVAL=1; COUNT=5 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Daily, DailyNDays = 1, IsDailyEveryNDays = true, IsRangeEndDate = true, RangeEndDate = new DateTime(2017, 06, 20) | FREQ=DAILY; INTERVAL=1; UNTIL=06/20/2017 |
|  | Appointment is created with Every (Interval) | RecurrenceType = RecurrenceType.Daily, DailyNDays = 2, IsDailyEveryNDays = true, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=DAILY; INTERVAL=2; COUNT=10 |
| Weekly | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsWeeklyWednesday = true, IsWeeklyFriday = true, IsRangeNoEndDate = true | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO, WE, FR |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyThursday = true, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=WEEKLY; INTERVAL=1; BYDAY=TH; COUNT=10 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsRangeEndDate = true, RangeEndDate = new DateTime(2017, 07, 20) | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO; UNTIL=07/20/2017 |
|  | Appointment is created with selecting multiple day | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 2, IsWeeklyMonday = true, IsWeeklyWednesday = true, IsWeeklyFriday = true IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=WEEKLY; INTERVAL=2; BYDAY=MO, WE, FR; COUNT=10 |
| Every Day | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsWeeklyTuesday = true, IsWeeklyWednesday = true, IsWeeklyThursday = true, IsWeeklyFriday = true, IsRangeNoEndDate = true | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsWeeklyTuesday = true, IsWeeklyWednesday = true, IsWeeklyThursday = true, IsWeeklyFriday = true, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR; COUNT=10 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsWeeklyTuesday = true, IsWeeklyWednesday = true, IsWeeklyThursday = true, IsWeeklyFriday = true, IsRangeEndDate = true, RangeEndDate = new DateTime(2017, 07, 15) | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR; UNTIL=07/15/2017 |
| Monthly | Appointment is created with selected date Ends Never | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, IsMonthlySpecific = true, MonthlySpecificMonthDay = 15, IsRangeNoEndDate = true | FREQ=MONTHLY; BYMONTHDAY=15; INTERVAL=1 |
|  | Appointment is created with selected date and Ends After | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, IsMonthlySpecific = true, MonthlySpecificMonthDay = 16, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=MONTHLY; BYMONTHDAY=16; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected date and Ends On | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, IsMonthlySpecific = true, MonthlySpecificMonthDay = 16, IsRangeEndDate = true, RangeEndDate = new DateTime(2018, 06, 11) | FREQ=MONTHLY; BYMONTHDAY=17; INTERVAL=1; UNTIL=06/11/2018 |
|  | Appointment is created with selected day Ends Never | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, MonthlyNthWeek = 2, MonthlyWeekDay = 6, IsRangeNoEndDate = true | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=2; INTERVAL=1 |
|  | Appointment is created with selected day and Ends After | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, MonthlyNthWeek = 4, MonthlyWeekDay = 4, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=MONTHLY; BYDAY=WE; BYSETPOS=4; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected day and Ends On | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, MonthlyNthWeek = 4, MonthlyWeekDay = 6, IsRangeEndDate = true, RangeEndDate = new DateTime(2018, 06, 11) | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=4; INTERVAL=1; UNTIL=06/11/2018 |
| Yearly | Appointment is created with selected date and month Ends Never | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, YearlyEveryNYears = 1, YearlySpecificMonth = 12, YearlySpecificMonthDay = 15, IsRangeNoEndDate = true | FREQ=YEARLY; BYMONTHDAY=15; BYMONTH=12; INTERVAL=1 |
|  | Appointment is created with selected date and month Ends After | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, YearlyEveryNYears = 1, YearlySpecificMonth = 12, YearlySpecificMonthDay = 10, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=YEARLY; BYMONTHDAY=10; BYMONTH=12; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected date and month Ends On | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, YearlyEveryNYears = 1, YearlySpecificMonth = 12, YearlySpecificMonthDay = 12, IsRangeEndDate = true, RangeEndDate = new DateTime(2018, 06, 11) | FREQ=YEARLY; BYMONTHDAY=12; BYMONTH=12; INTERVAL=1; UNTIL=06/11//2018 |

N> `SFSchedule` does not support Editing and Deleting of Recurring appointment's occurrences.

### Adding Recurrence Appointment using Recurrence Builder
Schedule appointment [RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~RecurrenceRule.html) is used to populate the required recurring appointment collection in a specific pattern. `RRULE` can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

{% highlight c# %}

    // Creating instance for Schedule Appointment Collection
        NSMutableArray appCollection = new NSMutableArray();

    //Adding All-Day Schedule appointment in Schedule Appointment Collection 
        var scheduleAppointment = new ScheduleAppointment()
        {
	        StartTime = startDate,
        	EndTime = endDate,
	        Subject = (NSString)"Client Meeting",
	        Location = (NSString)"Hutchison road",
	        IsRecursive = true,
	        AppointmentBackground = UIColor.Red
        };
        appCollection.Add(scheduleAppointment);

    // Creating Recurrence rule
            RecurrenceProperties recurrenceProperties = new RecurrenceProperties();
            recurrenceProperties.RecurrenceType = RecurrenceType.SFRecurrenceTypeDaily;
            recurrenceProperties.IsRangeRecurrenceCount = true;
            recurrenceProperties.DailyNDays = 2;
            recurrenceProperties.IsDailyEveryNDays = true;
            recurrenceProperties.RangeRecurrenceCount = 10;
            recurrenceProperties.RecurrenceRule = ScheduleHelper.RRuleGenerator(recurrenceProperties, scheduleAppointment.StartTime, scheduleAppointment.EndTime);

        // Setting Recurrence rule to Schedule Appointment
            scheduleAppointment.RecurrenceRule = recurrenceProperties.RecurrenceRule;

        //Adding Schedule appointment in Schedule Appointment Collection 
            schedule.Appointments = appCollection; 
{% endhighlight %} 

![](data_binding_images/recurrence.png)

## Appearance Customization
The default appearance of the appointment can be customized by using the [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle.html) property and [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs.html). The event and property is used to customize or override the default template of the Appointments.

•	[Customize appearance using Style](https://help.syncfusion.com/xamarin-ios/sfschedule/data-bindings#customize-appearance-using-style) 
•	[Customize appearance using Event](https://help.syncfusion.com/xamarin-ios/sfschedule/data-bindings#customize-appearance-using-event)
•	[Customize appearance using Custom View](https://help.syncfusion.com/xamarin-ios/sfschedule/data-bindings#customize-appearance-using-custom-view)

### Customize appearance using Style
Schedule appointment can be customized by setting appointment style properties such as [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~TextColor.html), [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~TextStyle.html), [BorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~BorderColor.html), [BorderCornerRadius](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~BorderCornerRadius.html), [BorderWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~BorderWidth.html) to the `AppointmentStyle` property of `SfSchedule`.

{% highlight c# %}

        //Creating Appointment style 
        SFAppointmentStyle appointmentStyle = new SFAppointmentStyle();
        appointmentStyle.TextColor = UIColor.Red;
        appointmentStyle.TextStyle = UIFont.SystemFontOfSize(20, UIFontWeight.Bold);
        appointmentStyle.BorderColor = UIColor.Blue;
        appointmentStyle.BorderCornerRadius = 12;
        appointmentStyle.BorderWidth = 2;
        appointmentStyle.SelectionBorderColor = UIColor.Yellow;
        appointmentStyle.SelectionTextColor = UIColor.Yellow;

        //Setting Appointment Style 
        schedule.AppointmentStyle = appointmentStyle; 

{% endhighlight %}

![](data_binding_images/style.png)

### Customize appearance using Event
Schedule appointment can be customized during runtime using [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs.html). `ScheduleAppointment` style can be customized using the `AppointmentStyle` property.

[AppointmentLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs.html) has below properties,

•	[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs~Appointment.html) – Contains the appointments values.
•	[AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs~AppointmentStyle.html) – Gets and sets the appointments style.
•	[View](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs~View.html) -  Sets the Custom UI for Appointments.
•	[Bounds](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs~Bounds.html) – Contains the UI bounds of appointment.

{% highlight c# %} 
 
          schedule.AppointmentLoaded += schedule_AppointmentLoaded;
  
void schedule_AppointmentLoaded(object sender, AppointmentLoadedEventArgs e)
    {       
	    if(e.Appointment != null && e.Appointment.IsAllDay == true && e.Appointment.Subject != null)
		{
			e.AppointmentStyle.BorderColor = UIColor.Red;
			e.AppointmentStyle.TextColor = UIColor.White;
            e.AppointmentStyle.BorderCornerRadius = 12;
            e.AppointmentStyle.BorderWidth = 2;
            e.AppointmentStyle.SelectionBorderColor = UIColor.Yellow;
            e.AppointmentStyle.SelectionTextColor = UIColor.Yellow;
		}
		else
        {
            e.AppointmentStyle.BorderColor = UIColor.Blue;
			e.AppointmentStyle.TextColor = UIColor.Red;
            e.AppointmentStyle.BorderCornerRadius = 12;
            e.AppointmentStyle.BorderWidth = 2;
            e.AppointmentStyle.SelectionBorderColor = UIColor.Yellow;
            e.AppointmentStyle.SelectionTextColor = UIColor.Yellow;
        }
    }

{% endhighlight %}

![](PopulatingAppointments_images/appointmentstyle_event.png)

## Customize appearance using Custom View
Default appointment UI can be changed using `View` property passed through `AppointmentLoadedEventArgs`.

{% highlight c# %} 
 
     schedule.AppointmentLoaded += schedule_AppointmentLoaded;

    void schedule_AppointmentLoaded(object sender, AppointmentLoadedEventArgs e)
    {
	
    if ( e.Appointment != null && (e.Appointment as Meeting).IsAllDay == true && (e.Appointment as Meeting).EventName != null)
	{
         UITextView textview = new UITextView();
         textview.BackgroundColor = (UIColor)e.Appointment.AppointmentBackground;
	     textview.Text = (NSString)e.Appointment.Subject;
         e.View = textview;
    }
	else if (e.Appointment != null && (e.Appointment as Meeting).EventName == "Retrospective" && (e.Appointment as Meeting).EventName != null)
	{
	    UIButton button = new UIButton();
		button.SetBackgroundImage(UIImage.FromFile("Meeting.png"), UIControlState.Normal);
		button.BackgroundColor = (UIColor)e.Appointment.AppointmentBackground;
        e.View = button;
	}
	else
	{       
        UIButton button = new UIButton();
		button.SetBackgroundImage(UIImage.FromFile("Cake.png"), UIControlState.Normal);
        if(e.Appointment!=null)
            button.BackgroundColor = (UIColor)e.Appointment.AppointmentBackground;
        e.View = button;
    }
	}
 
{% endhighlight %}

![](PopulatingAppointments_images/appointmentstyle_customview.png)

## Selection
Schedule control has built-in events to handle tapped, double tapped and long pressed touch actions.

•	[CellTapped](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs.html)
•	[CellDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs.html)
•	[CellLongPressed](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs.html)

These events will be triggered while perform respective touch actions in timeslots, month cells and in appointments. All the three events contain the same argument [CellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs.html) which holds selected appointment and date time details in it.

• [SelectedAppointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs~SelectedAppointment.html) -  Contains the selected appointment value, it will be null, if any time slots selected.
• [Date](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs~Date.html) - Contains selected time slot DateTime value.

{% highlight c# %} 
 
        schedule.CellTapped += Schedule_CellTapped;
	schedule.CellDoubleTapped += Schedule_CellDoubleTapped;
	schedule.CellLongPressed += Schedule_CellLongPressed;


	private void Schedule_CellTapped(object sender, CellTappedEventArgs e)
		{
		}
	private void Schedule_CellDoubleTapped(object sender, CellTappedEventArgs e)
		{
		}
	private void Schedule_CellLongPressed(object sender, CellTappedEventArgs e)
		{
		}
 
{% endhighlight %}

### Selection customization
The default selection of an appointment can be customized by using [SelectionBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~SelectionBorderColor.html), [SelectionTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~SelectionTextColor.html) properties in `AppointmentStyle` property of `SfSchedule`. The property is used to customize or override the default selection of the appointments.

N> `BorderWidth` value must be set to highlight `SelectionBorderColor`.

{% highlight c# %} 
 
        //Creating Appointment style 
        SFAppointmentStyle appointmentStyle = new SFAppointmentStyle();
        appointmentStyle.BorderColor = UIColor.Blue;
        appointmentStyle.BorderCornerRadius = 12;
        appointmentStyle.BorderWidth = 2;
        appointmentStyle.SelectionBorderColor = UIColor.Yellow;
        appointmentStyle.SelectionTextColor = UIColor.Yellow;

        //Setting Appointment Style 
        schedule.AppointmentStyle = appointmentStyle;
 
{% endhighlight %}

![](data_binding_images/selection.png)
