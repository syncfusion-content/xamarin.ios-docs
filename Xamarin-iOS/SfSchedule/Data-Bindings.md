---

layout: post
title: Populating Appointments in Syncfusion SfSchedule control for Xamarin.iOS
description: Learn how to Populate Appointments in SfSchedule control
platform: xamarin.ios
control: SfSchedule
documentation: ug

---


# Appointments

[ScheduleAppointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment.html) is a class, which holds the details about the appointment to be rendered in schedule. It has some basic properties such as [StartTime](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~StartTime.html), [EndTime](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~EndTime.html), [Subject](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Subject.html) and some additional information about the appointment can be added using [AppointmentBackground](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~AppointmentBackground.html), [Notes](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Notes.html), [Location](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Location.html), [All Day](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~IsAllDay.html), [Recurring properties](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties.html).

{% tabs %}
{% highlight c# %}
using Foundation;
using Syncfusion.SfSchedule.iOS;

//Creating an instance for SfSchedule control
SFSchedule schedule = new SFSchedule();

// Creating instance for schedule appointment collection
NSMutableArray appCollection = new NSMutableArray();
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
calendar.TimeZone = NSTimeZone.FromGMT(NSTimeZone.LocalTimeZone.GetSecondsFromGMT);

NSDate today = new NSDate();

// Get the year, month, day from the date
NSDateComponents startDateComponents = calendar.Components(NSCalendarUnit.Year |
                                                           NSCalendarUnit.Month |
                                                           NSCalendarUnit.Day, today);

// Set the hour, minute, second
startDateComponents.Hour = 10;
startDateComponents.Minute = 0;
startDateComponents.Second = 0;

// Get the year, month, day from the date
NSDateComponents endDateComponents = calendar.Components(NSCalendarUnit.Year |
                                                         NSCalendarUnit.Month |
                                                         NSCalendarUnit.Day, today);

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
{% endtabs %}

![Creating Appointment in schedule Xamarin iOS](data_binding_images/appointment.png)

## Mapping
Schedule supports full data binding to any type of IEnumerable source. Specify the [AppointmentMapping](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping.html) attributes to map the properties in the underlying data source to the schedule appointments.

| PropertyName | Description |
| -------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| [StartTime](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~StartTime.html) | This property is to map the property name of custom class which is equivalent for StartTime of ScheduleAppointment. |
| [EndTime](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~EndTime.html) | This property is to map the property name of custom class which is equivalent for EndTime of ScheduleAppointment. |
| [Subject](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~Subject.html) | This property is to map the property name of custom class which is equivalent for Subject of ScheduleAppointment. |
| [AppointmentBackground](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~AppointmentBackground.html) | This property is to map the property name of custom class which is equivalent for Color of ScheduleAppointment. |
| [IsAllDay](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~IsAllDay.html) | This property is to map the property name of custom class which is equivalent for IsAllDay of ScheduleAppointment. |
| [RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~RecurrenceRule.html) | This property is to map the property name of custom class which is equivalent for RecurrenceRule of ScheduleAppointment. |
| [Notes](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~Notes.html) | This property is to map the property name of custom class which is equivalent for Notes of ScheduleAppointment. |
| [Location](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~Location.html) | This  property is to map the property name of custom class which is  equivalent for Location of ScheduleAppointment. |
| [MinHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~MinHeight.html) | This property is to map the property name of custom class which is equivalent for MinHeight of ScheduleAppointment. |
| [StartTimeZone](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~StartTimeZone.html) | This property is to map the property name of custom class which is equivalent for StartTimeZone of ScheduleAppointment. |
| [EndTimeZone](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~EndTimeZone.html) | This property is to map the property name of custom class which is equivalent for EndTimeZone of ScheduleAppointment. |

>**NOTE**
CustomAppointment class should contain two NSDate fields and a NSString field as mandatory.
 
### Creating custom Appointments
You can create a custom class `Meeting` with mandatory fields 	`From`, `To`, `EventName`.

{% tabs %}
{% highlight c# %}
/// <summary>   
/// Represents custom data properties.   
/// </summary> 
public class Meeting
{
	public NSString EventName { get; set; }
	public NSDate From { get; set; }
	public NSDate To { get; set; }
	public UIColor Color { get; set; }
}
{% endhighlight %}
{% endtabs %}

>**NOTE**
You can inherit this class from `INotifyPropertyChanged` for dynamic changes in Custom data.

You can map those properties of `Meeting` class with our SfSchedule control by using [AppointmentMapping](https://help.syncfusion.com/cr/cref_files/xamarin-iOS/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SfSchedule~AppointmentMapping.html).

{% tabs %}
{% highlight c# %}
/// <summary>   
/// Represents custom data properties.   
/// </summary> 
 AppointmentMapping mapping = new AppointmentMapping();
 mapping.Subject = "EventName";
 mapping.StartTime = "From";
 mapping.EndTime = "To";
 mapping.AppointmentBackground = "Color";
 schedule.AppointmentMapping = mapping;
{% endhighlight %}
{% endtabs %}

You can schedule meetings for a day by setting `From` and `To` of `Meeting` class. Create meetings of type `ObservableCollection <Meeting>` and assign those appointments collection `Meetings` to the `ItemsSource` property which is of `IEnumerable` type.

{% tabs %}
{% highlight c# %}
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
NSDate today = new NSDate();
NSDateComponents startDateComponents = calendar.Components(NSCalendarUnit.Year |
                                                           NSCalendarUnit.Month |
                                                           NSCalendarUnit.Day, today);
startDateComponents.Hour = 09;
startDateComponents.Minute = 0;
startDateComponents.Second = 0;
NSDateComponents endDateComponents = calendar.Components(NSCalendarUnit.Year |
                                                         NSCalendarUnit.Month |
                                                         NSCalendarUnit.Day, today);
endDateComponents.Hour = 10;
endDateComponents.Minute = 0;
endDateComponents.Second = 0;
NSDate startDate = calendar.DateFromComponents(startDateComponents);
NSDate endDate = calendar.DateFromComponents(endDateComponents);
// Creating instance for custom appointment class
Meeting meeting = new Meeting();
// Setting start time of an event
meeting.From = startDate;
// Setting end time of an event
meeting.To = endDate;
// Setting start time for an event
meeting.EventName = (NSString)"Anniversary";
// Setting color for an event
meeting.Color = UIColor.Green;
// Creating instance for collection of custom appointments
var Meetings = new ObservableCollection<Meeting>();
// Adding a custom appointment in CustomAppointmentCollection
Meetings.Add(meeting);
// Adding custom appointments in DataSource of SfSchedule
schedule.ItemsSource = Meetings;
{% endhighlight %}
{% endtabs %}


## Spanned Appointments
Spanned Appointment is an appointment which lasts more than 24 hours. It doesn’t block out time slots in `SfSchedule`,it will render in [All-Day appointment](https://help.syncfusion.com/xamarin-ios/sfschedule/data-bindings#all-day-appointment-panel) panel exclusively.

{% tabs %}
{% highlight c# %}
using Foundation;
using Syncfusion.SfSchedule.iOS;

//Creating an instance for SfSchedule control
SFSchedule schedule = new SFSchedule();

// Creating instance for schedule appointment collection
NSMutableArray appCollection = new NSMutableArray();
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
calendar.TimeZone = NSTimeZone.FromGMT(NSTimeZone.LocalTimeZone.GetSecondsFromGMT);

NSDate today = new NSDate();

// Get the year, month, day from the date
NSDateComponents startDateComponents = calendar.Components(NSCalendarUnit.Year |
                                                           NSCalendarUnit.Month |
                                                           NSCalendarUnit.Day, today);

// Set the hour, minute, second
startDateComponents.Hour = 10;
startDateComponents.Minute = 0;
startDateComponents.Second = 0;

// Get the year, month, day from the date
NSDateComponents endDateComponents = calendar.Components(NSCalendarUnit.Year |
                                                         NSCalendarUnit.Month |
                                                         NSCalendarUnit.Day, today);

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
{% endtabs %}

![spanning or multiday appointments in schedule Xamarin iOS](data_binding_images/span.png)

## All Day Appointments
All-Day appointment is an appointment which is scheduled for a whole day. It can be set by using `IsAllDay` property in the `ScheduleAppointment`.

{% tabs %}
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
{% endtabs %}

>**NOTE**
Appointment which lasts through an entire day (exact 24 hours) will be considered as all day appointment without setting `IsAllDay` property. For example  06/09/2018 12:00AM to 06/10/2018 12:00AM.

### All-Day Appointment Panel
All-day appointment and Spanned appointment doesn't block out entire time slot in SfSchedule, rather it will render in separate layout exclusively for all-day appointment. It can be enabled by setting `ShowAllDay` property of `DayViewSettings`, `WeekViewSettings` and `WorkWeekViewSettings` of `DayView`, `WeekView` and `WorkWeekView` respectively.

{% tabs %}
{% highlight c# %}
//Setting Schedule View
schedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

//Creating Week View Settings for SfSchedule WeekView
WeekViewSettings weekViewSettings = new WeekViewSettings();
weekViewSettings.ShowAllDay = true;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

>**NOTE**
Appointments which lasts less than 24 hours with different start date and end date will be rendered in time slot.

All-Day panel background can be customized by setting `AllDayAppointmentLayoutColor` 
of the respective view settings.

{% tabs %}
{% highlight c# %}
weekViewSettings.AllDayAppointmentLayoutColor = UIColor.Gray;
{% endhighlight %}
{% endtabs %}

![All day appointments in schedule Xamarin iOS](data_binding_images/allday.png)

## Recurrence Appointment
Recurring appointment on a daily, weekly, monthly, or yearly interval. Recurring appointments can be created by setting `RecurrenceRule` property in Schedule appointments.

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
Recurrence pattern used in the control are in iCal standard. Schedule control supports all four types of [recurrence patterns](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties.html).

| RecurrenceType | RecurrenceProperties | Description                                                                                 |
|----------------|----------------------|---------------------------------------------------------------------------------------------|
| Daily          | [Interval](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~Interval.html)             | Gets or sets the day interval on which recurrence has to be set.                            |
| 				 | [IsDailyEveryNDays](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~IsDailyEveryNDays.html)    | Checks whether the event occurs Daily Every N days.                                         |
| Weekly         | [Interval](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~Interval.html)            | Gets or sets the day interval on which recurrence has to be set.                            |
|                | [DayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~DayOfWeek.html)            | Gets or sets the day of week on which recurrence has to be set.                             |
|                | [WeekDays](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~WeekDays.html)             | Gets or sets the day/days in a week on which recurrence has to be set.                      |
|				 | [Week](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~Week.html)					| Gets or sets the week of month on which recurrence has to be set.							  |
| Monthly        | [Interval](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~Interval.html)            | Gets or sets the day interval on which  recurrence has to be set.                           |
|                | [DayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~DayOfWeek.html)            | Gets or sets the day of week on which  recurrence has to be set.                            |
|				 | [Week](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~Week.html)				| Gets or sets the week of month on which recurrence has to be set.							  |
|                | [DayOfMonth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~DayOfMonth.html)           | Gets or sets the day on which recurrence has to be set for every month.                     |
|				 | [IsMonthlySpecific](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~IsMonthlySpecific.html)  | Checks whether the event is Monthly specific event.										  |
| Yearly         | [Interval](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~Interval.html)             | Gets or sets the day interval on which recurrence has to be set.                            |
|                | [DayOfMonth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~DayOfMonth.html)           | Gets or sets the day on which recurrence has to be set for every month.                     |
|                | [DayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~DayOfWeek.html)            | Gets or sets the day of week on which  recurrence has to be set.                            |
|				 | [Month](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~Month.html)				| Gets or sets the specific month of year on which recurrence has to be set.				  |
|				 | [Week](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~Week.html)					| Gets or sets the week of month on which recurrence has to be set.							  |
|				 | [IsYearlySpecific](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~IsYearlySpecific.html)     | Checks whether the event is Yearly Specific.												  |
| Common         | [RecurrenceRange](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~RecurrenceRange.html)      | Gets or sets the type of the recurrence range for the time limit of recurrence appointment. |
|                | [RecurrenceCount](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~RecurrenceCount.html)      | Gets or sets the count for recurring appointment.                                           |
|                | [StartDate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~StartDate.html)           | Gets or sets the date to start the recurrence appointment.                                  |
|                | [EndDate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~EndDate.html)              | Gets or sets the date to end the recurrence appointment.                                    |
| 				 | [IsSpecific](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties~IsSpecific.html)			| Checks whether the event occurs in specific recurrence type.								  |

Find the following `RecurrenceRule` possibilities available in the Schedule control while creating the recurrence appointment.

| PossibilityType | Description | RecurrenceProperties | Examples |
|-----------------|----------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| Daily | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Daily, Interval = 1, IsDailyEveryNDays = true, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=DAILY; INTERVAL=1 |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Daily, Interval = 1, IsDailyEveryNDays = true, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 15 | FREQ=DAILY; INTERVAL=1; COUNT=5 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Daily, Interval = 1, IsDailyEveryNDays = true, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2017, 06, 20) | FREQ=DAILY; INTERVAL=1; UNTIL=06/20/2017 |
|  | Appointment is created with Every (Interval) | RecurrenceType = RecurrenceType.Daily, Interval = 2, IsDailyEveryNDays = true, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=DAILY; INTERVAL=2; COUNT=10 |
| Weekly | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday`|`WeekDays.Wednesday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO, WE, FR |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Thursday, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=WEEKLY; INTERVAL=1; BYDAY=TH; COUNT=10 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2017, 07, 20) | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO; UNTIL=07/20/2017 |
|  | Appointment is created with selecting multiple day | RecurrenceType = RecurrenceType.Weekly, Interval = 2, WeekDays = WeekDays.Monday`|`WeekDays.Wednesday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=WEEKLY; INTERVAL=2; BYDAY=MO, WE, FR; COUNT=10 |
| Every Day | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday	`|`WeekDays.Tuesday`|`WeekDays.Wednesday`|`WeekDays.Thursday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday`|`WeekDays.Tuesday`|`WeekDays.Wednesday`|`WeekDays.Thursday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR; COUNT=10 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Weekly, Interval = 1, WeekDays = WeekDays.Monday`|`WeekDays.Tuesday`|`WeekDays.Wednesday`|`WeekDays.Thursday`|`WeekDays.Friday, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2017, 07, 15) | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR; UNTIL=07/15/2017 |
| Monthly | Appointment is created with selected date Ends Never | RecurrenceType = RecurrenceType.Monthly, Interval = 1, IsMonthlySpecific = true, DayOfMonth = 15, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=MONTHLY; BYMONTHDAY=15; INTERVAL=1 |
|  | Appointment is created with selected date and Ends After | RecurrenceType = RecurrenceType.Monthly, Interval = 1, IsMonthlySpecific = true, DayOfMonth = 16, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=MONTHLY; BYMONTHDAY=16; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected date and Ends On | RecurrenceType = RecurrenceType.Monthly, Interval = 1, IsMonthlySpecific = true, DayOfMonth = 16, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2018, 06, 11) | FREQ=MONTHLY; BYMONTHDAY=17; INTERVAL=1; UNTIL=06/11/2018 |
|  | Appointment is created with selected day Ends Never | RecurrenceType = RecurrenceType.Monthly, Interval = 1, Week = 2, DayOfWeek = 6, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=2; INTERVAL=1 |
|  | Appointment is created with selected day and Ends After | RecurrenceType = RecurrenceType.Monthly, Interval = 1, Week = 4, DayOfWeek = 4, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=MONTHLY; BYDAY=WE; BYSETPOS=4; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected day and Ends On | RecurrenceType = RecurrenceType.Monthly, Interval = 1, Week = 4, DayOfWeek = 6, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2018, 06, 11) | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=4; INTERVAL=1; UNTIL=06/11/2018 |
| Yearly | Appointment is created with selected date and month Ends Never | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, Interval = 1, Month = 12, DayOfMonth = 15, RecurrenceRange = RecurrenceRange.NoEndDate | FREQ=YEARLY; BYMONTHDAY=15; BYMONTH=12; INTERVAL=1 |
|  | Appointment is created with selected date and month Ends After | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, Interval = 1, Month = 12, DayOfMonth = 10, RecurrenceRange = RecurrenceRange.Count, RecurrenceCount = 10 | FREQ=YEARLY; BYMONTHDAY=10; BYMONTH=12; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected date and month Ends On | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, Interval = 1, Month = 12, DayOfMonth = 12, RecurrenceRange = RecurrenceRange.EndDate, EndDate = new DateTime(2018, 06, 11) | FREQ=YEARLY; BYMONTHDAY=12; BYMONTH=12; INTERVAL=1; UNTIL=06/11//2018 |

N> `SFSchedule` does not support Editing and Deleting of Recurring appointment's occurrences.

### Adding Recurrence Appointment using Recurrence Builder
Schedule appointment [RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~RecurrenceRule.html) is used to populate the required recurring appointment collection in a specific pattern. `RRULE` can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

{% tabs %}
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
	AppointmentBackground = UIColor.Red
};
appCollection.Add(scheduleAppointment);

// Creating Recurrence rule
RecurrenceProperties recurrenceProperties = new RecurrenceProperties();
recurrenceProperties.RecurrenceType = RecurrenceType.SFRecurrenceTypeDaily;
recurrenceProperties.RecurrenceRange = true;
recurrenceProperties.Interval = 2;
recurrenceProperties.IsDailyEveryNDays = true;
recurrenceProperties.RecurrenceCount = 10;


// Setting Recurrence rule to Schedule Appointment
scheduleAppointment.RecurrenceRule = ScheduleHelper.RRuleGenerator(recurrenceProperties, scheduleAppointment.StartTime, scheduleAppointment.EndTime);

//Adding Schedule appointment in Schedule Appointment Collection 
schedule.Appointments = appCollection; 
{% endhighlight %}
{% endtabs %}

![Recurrence appointment support in schedule Xamarin iOS](data_binding_images/recurrence.png)

## Recurrence Pattern Exceptions 
You can delete or change any recurrence pattern appointment by handling exception dates and exception appointments to that recurring appointment.

### Recurrence Exception Dates
You can delete any occurrence appointment which is exception from the recurrence pattern appointment by adding exception dates to the recurring appointment.  

### Recurrence Exception appointment
You can also change any occurrence appointment which is exception from recurrence pattern appointment by adding the recurrence exception appointment in the schedule `ItemsSource`.

### Create recurrence exceptions for schedule appointment

You can add/remove the recurrence exception appointments and recurrence exception dates to `ScheduleAppointment` by using its property, [RecurrenceExceptionDates](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~RecurrenceExceptionDates.html), [RecurrenceId](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~RecurrenceId.html), [ExceptionOccurrenceActualDate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~ExceptionOccurrenceActualDate.html).

#### Delete occurrence from recurrence pattern appointment or adding exception dates to recurrence pattern appointment
You can delete any of occurrence which is exception from recurrence pattern appointment by using `RecurrenceExceptionDates` property of `ScheduleAppointment`.The deleted occurrence date will be considered as recurrence exception dates.
{% tabs %}
{% highlight c# %}
 NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
NSDate today = NSDate.Now;

// Get the year, month, day from the date
NSDateComponents startDateComponents = calendar.Components(NSCalendarUnit.Year |
														   NSCalendarUnit.Month |
														   NSCalendarUnit.Day, today);
														   
// Set the year, month, day, hour, minute, second
startDateComponents.Year = 2017;
startDateComponents.Month = 09;
startDateComponents.Day = 03;
startDateComponents.Hour = 10;
startDateComponents.Minute = 0;
startDateComponents.Second = 0;

//setting start time for the event
NSDate startDate = calendar.DateFromComponents(startDateComponents);

//setting end time for the event
NSDate endDate = startDate.AddSeconds(2 * 60 * 60);

// Set the exception date. 
var exceptionDate = startDate.AddSeconds(4 * 24 * 60 * 60);

// Add Schedule appointment
ScheduleAppointment recurrenceAppointment = new ScheduleAppointment
{
	StartTime = startDate,
	EndTime = endDate,
	Subject = (NSString)"Occurs Daily",
	AppointmentBackground = UIColor.Blue,
	RecurrenceRule = (NSString)"FREQ=DAILY;COUNT=20",
	RecurrenceExceptionDates = new ObservableCollection<NSDate> 
	{
		exceptionDate
	}
};
{% endhighlight %}
{% endtabs %}

>**NOTE**
•	Exception dates should be Universal Time Coordinates (UTC) time zone.
•	You can also update the RecurrenceExceptionDates collection dynamically.

![Recurrence Exception dates support in schedule Xamarin iOS](data_binding_images/exception_dates.png)

#### Delete occurrence from recurrence pattern dynamically or add exception dates to recurrence pattern dynamically
You can also delete any occurrence from the recurrence pattern appointment by adding exception date to the `RecurrenceExceptionDates` collection.

{% tabs %}
{% highlight c# %}
exceptionDate = exceptionDate.AddSeconds(24 * 60 * 60);
var recurrenceAppointment = scheduleAppointmentCollection[0];
recurrenceAppointment.RecurrenceExceptionDates.Add(exceptionDate);
{% endhighlight %}
{% endtabs %}

#### Add deleted occurrence to recurrence pattern dynamically or remove exception dates from recurrence pattern dynamically
You can also add the deleted occurrence to the recurrence pattern appointment by removing exception date from the `RecurrenceExceptionDates` collection.

{% tabs %}
{% highlight c# %}
var recurrenceAppointment = scheduleAppointmentCollection[0];
recurrenceAppointment.RecurrenceExceptionDates.RemoveAt(0);
{% endhighlight %}
{% endtabs %}

>**NOTE**
If you add the deleted occurrence to the recurrence pattern by removing exception date when any [exception appointment](#recurrence-exception-appointment) has been created for the mentioned exception date, the respective exception appointment will be deleted by matching with `RecurrenceId` and `ExceptionOccurrenceActualDate` from Schedule `ItemsSource` and recurrence pattern appointment created for that exception date.

#### Add all deleted occurrences to recurrence pattern dynamically or clear exception dates from recurrence pattern dynamically
You can also add all deleted occurrences to the recurrence pattern appointment by clearing the exception dates from the `RecurrenceExceptionDates` collection.

{% tabs %}
{% highlight c# %}
var recurrenceAppointment = scheduleAppointmentCollection[0];
recurrenceAppointment.RecurrenceExceptionDates.Clear();
{% endhighlight %}
{% endtabs %}

#### Add exception appointment to recurrence pattern

You can change any occurrence appointment which is an exception from the recurrence pattern appointment by using the `RecurrenceId` property which is used to map the exception appointment with recurrence pattern appointment and `ExceptionOccurrenceActualDate` property which is used to mention the actual pattern occurrence date of exception appointment of `ScheduleAppointment`.
You should add the created exception recurrence appointment to the schedule `ItemsSource`.
{% tabs %}
{% highlight c# %}
 NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
NSDate today = NSDate.Now;

// Get the year, month, day from the date
NSDateComponents startDateComponents = calendar.Components(NSCalendarUnit.Year |
														   NSCalendarUnit.Month |
														   NSCalendarUnit.Day, today);
														   
// Set the year, month, day, hour, minute, second
startDateComponents.Year = 2017;
startDateComponents.Month = 09;
startDateComponents.Day = 03;
startDateComponents.Hour = 10;
startDateComponents.Minute = 0;
startDateComponents.Second = 0;

//setting start time for the event
NSDate startDate = calendar.DateFromComponents(startDateComponents);

//setting end time for the event
NSDate endDate = startDate.AddSeconds(2 * 60 * 60);

// Set the exception date. 
var exceptionDate = startDate.AddSeconds(4 * 24 * 60 * 60);

// Add Schedule appointment
ScheduleAppointment recurrenceAppointment = new ScheduleAppointment
{
	StartTime = startDate,
	EndTime = endDate,
	Subject = (NSString)"Occurs Daily",
	AppointmentBackground = UIColor.Blue,
	RecurrenceRule = (NSString)"FREQ=DAILY;COUNT=20",
        RecurrenceExceptionDates = new ObservableCollection<NSDate> 
	{
           exceptionDate
	}
};

var exceptionAppointment = new ScheduleAppointment
{
	StartTime = exceptionDate.AddSeconds(3 * 60 * 60),
	EndTime = exceptionDate.AddSeconds(4 * 60 * 60),
	Subject = (NSString)"Meeting",
	AppointmentBackground = UIColor.Red,
	// set the parent appointment to recurrence Id.
	RecurrenceId = recurrenceAppointment,
	 //Actual occurrence date
	ExceptionOccurrenceActualDate = exceptionDate
};
{% endhighlight %}
{% endtabs %}

>**NOTE**
•	`RecurrenceId` should be a recurrence pattern appointment object.
•	Exception appointment should be a normal appointment and should not be created as recurring appointment, since its occurrence is from recurrence pattern.
•	`ExceptionOccurrenceActualDate` should be in Universal Time Coordinates (UTC) time zone.

![Recurrence Exception Appointment support in schedule Xamarin iOS](data_binding_images/exception_appointment.png)

#### Add exception appointment to recurrence pattern dynamically
You can also add exception appointment dynamically for added exception date by adding exception appointment to the schedule `ItemsSource` which is exception from the recurrence pattern appointment by using the `RecurrenceId` property which is used to map the exception appointment with recurrence pattern appointment and `ExceptionOccurrenceActualDate` property which is used to mention the actual pattern occurrence date of exception appointment of the `ScheduleAppointment` class.

{% tabs %}
{% highlight c# %}
var recurrenceAppointment = scheduleAppointmentCollection[0];

// Add exception appointment to the current recurrence series
var exceptionAppointment = new ScheduleAppointment
{
	StartTime = exceptionDate.AddSeconds(3 * 60 * 60),
	EndTime = exceptionDate.AddSeconds(4 * 60 * 60),
	Subject = (NSString)"Meeting",
	AppointmentBackground = UIColor.Red,
	// set the parent appointment to recurrence Id
	RecurrenceId = recurrenceAppointment,
	//Actual occurrence date
	ExceptionOccurrenceActualDate = exceptionDate
};

//Adding exception appointment in schedule appointment collection
scheduleAppointmentCollection.Add(exceptionAppointment);
{% endhighlight %}
{% endtabs %}
>**NOTE**
•	`RecurrenceId` should be a recurrence pattern appointment object.
•	Exception appointment should be a normal appointment and should not be created as recurring appointment, since its occurrence from recurrence pattern.
•	`ExceptionOccurrenceActualDate` should be in Universal Time Coordinates (UTC) time zone.

#### Remove exception appointment from recurrence pattern
You can directly remove the added exception appointment for recurrence pattern by removing it from schedule `ItemsSource`.

{% tabs %}
{% highlight c# %}
var exceptionAppointment = scheduleAppointmentCollection[1];
//Remove exception appointment from schedule appointment collection
scheduleAppointmentCollection.Remove(exceptionAppointment);
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo for Xamarin.iOS from
here [RecurrenceExceptions](https://github.com/SyncfusionExamples/Create-Recurrence-Exceptions-to-schedule-recurring-appointments-in-Xamarin.iOS).

### Create recurrence exceptions for custom appointment

You can add/remove the recurrence exception appointments and recurrence exception dates to the CustomAppointment, You can create a custom class `Meeting`([refer](#mapping)) with mandatory fields `RecurrenceExceptionDates`, `ActualDate`, `RecurrenceId`.

#### Delete occurrence from recurrence pattern appointment or adding exception dates to recurrence pattern appointment
You can delete any occurrence which is exception from the recurrence pattern appointment by using the [RecurrenceExceptionDates](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~RecurrenceExceptionDates.html) property of `AppointmentMapping` class which is used to map the exception dates to the schedule recurrence appointment. The deleted occurrence date will be considered as recurrence exception dates.
To add the exception dates in the recurrence series of custom appointment, add the RecurrenceExceptionDates property to custom class `Meeting`.

{% tabs %}
{% highlight c# %}
 public ObservableCollection<NSDate> RecurrenceExceptionDates { get; set; } = new ObservableCollection<NSDate>();
{% endhighlight %}
{% endtabs %}

You should map this custom property `RecurrenceExceptionDates` of custom class with the `RecurrenceExceptionDates` property of `AppointmentMapping` class to map the exception dates to the schedule appointment.

{% tabs %}
{% highlight c# %}
// data mapping for custom appointments.
dataMapping.RecurrenceExceptionDates = "RecurrenceExceptionDates";
            
// Create the new exception date.
var calendar = new NSCalendar(NSCalendarType.Gregorian);
var today = NSDate.Now;

// Get the year, month, day from the date
var startDateComponents = calendar.Components(NSCalendarUnit.Year |
										   NSCalendarUnit.Month |
										   NSCalendarUnit.Day, today);
										   
// Set the year, month, day, hour, minute, second
startDateComponents.Year = 2017;
startDateComponents.Month = 09;
startDateComponents.Day = 03;
startDateComponents.Hour = 10;
startDateComponents.Minute = 0;
startDateComponents.Second = 0;

//setting start time for the event
var startDate = calendar.DateFromComponents(startDateComponents);

//setting end time for the event
var endDate = startDate.AddSeconds(2 * 60 * 60);
var exceptionDate = startDate.AddSeconds(4 * 24 * 60 * 60);

// Add Schedule appointment
var recurrenceAppointment = new Meeting
{
	From = startDate,
	To = endDate,
	EventName = (NSString)"Occurs Daily",
	Color = UIColor.Blue,
	RecurrenceRule = (NSString)"FREQ=DAILY;COUNT=20",
	RecurrenceExceptionDates = new ObservableCollection<NSDate>
	{
		exceptionDate
	}
};
{% endhighlight %}
{% endtabs %}

>**NOTE**
•	Exception dates should be in Universal Time Coordinates (UTC) time zone.
•	You can also dynamically update the custom property RecurrenceExceptionDates collection.

![Recurrence Exception dates support in schedule Xamarin iOS](data_binding_images/exception_dates.png)

#### Delete occurrence from recurrence pattern dynamically or add exception dates to recurrence pattern dynamically
You can also delete any occurrence from the recurrence pattern appointment by adding exception date to the `RecurrenceExceptionDates` custom property collection.

{% tabs %}
{% highlight c# %}
var recurrenceAppointment = scheduleAppointmentCollection[0];
var addExceptionDate = exceptionDate.AddSeconds(24 * 60 * 60);
recurrenceAppointment.RecurrenceExceptionDates.Add(addExceptionDate);
{% endhighlight %}
{% endtabs %}

#### Add deleted occurrence to recurrence pattern dynamically or remove exception dates from recurrence pattern dynamically
You can also add the deleted occurrence to the recurrence pattern appointment by removing exception date from the `RecurrenceExceptionDates` custom property collection.

{% tabs %}
{% highlight c# %}
var recurrenceAppointment = scheduleAppointmentCollection[0];
recurrenceAppointment.RecurrenceExceptionDates.RemoveAt(0);
{% endhighlight %}
{% endtabs %}

>**NOTE**
If you add the deleted occurrence to the recurrence pattern by removing exception date when any [exception appointment](#recurrence-exception-appointment) has been created for the mentioned exception date, the respective exception appointment will be deleted by matching with `RecurrenceId` and `ActualDate` from the schedule `ItemsSource` and recurrence pattern appointment created for that exception date.

#### Add all deleted occurrence to recurrence pattern dynamically or clear exception dates from recurrence pattern dynamically
You can also add all deleted occurrence to the recurrence pattern appointment by clearing the exception dates from the `RecurrenceExceptionDates` custom property collection.

{% tabs %}
{% highlight c# %}
var recurrenceAppointment = scheduleAppointmentCollection[0];
recurrenceAppointment.RecurrenceExceptionDates.Clear();
{% endhighlight %}
{% endtabs %}

#### Add exception appointment to recurrence pattern
You can change any occurrence appointment which is exception from the recurrence pattern appointment by using the [RecurrenceId](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~RecurrenceId.html) property of `AppointmentMapping` class which is used to map the custom exception appointment with schedule recurrence series appointment and [ExceptionOccurrenceActualDate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentMapping~ExceptionOccurrenceActualDate.html) property of `AppointmentMapping` class which is used to mention the actual series occurrence date of exception appointment of schedule recurrence appointment.
For adding custom exception appointment to the recurrence series, add the `ActualDate` and `RecurrenceID` properties to custom class `Meeting`.

{% tabs %}
{% highlight c# %}
public Calendar ActualDate { get; set; }
public object RecurrenceID { get; set; }
{% endhighlight %}
{% endtabs %}

You should map this custom property `RecurrenceID` of `Meeting` with the `RecurrenceId` property of `AppointmentMapping` class which is used to map the exception appointment with schedule recurrence series appointment `Meeting`.
You should also map this custom property `ActualDate` of `Meeting` with the `ExceptionOccurrenceActualDate` property of `AppointmentMapping` class which is used to mention the actual series occurrence date of exception appointment with schedule recurrence appointment.
You should add the created exception recurrence appointment to the schedule `ItemsSource`.

{% tabs %}
{% highlight c# %}
 NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
NSDate today = NSDate.Now;

// Get the year, month, day from the date
NSDateComponents startDateComponents = calendar.Components(NSCalendarUnit.Year |
													   NSCalendarUnit.Month |
													   NSCalendarUnit.Day, today);
													   
// Set the year, month, day, hour, minute, second
startDateComponents.Year = 2017;
startDateComponents.Month = 09;
startDateComponents.Day = 03;
startDateComponents.Hour = 10;
startDateComponents.Minute = 0;
startDateComponents.Second = 0;

//setting start time for the event
NSDate startDate = calendar.DateFromComponents(startDateComponents);

//setting end time for the event
NSDate endDate = startDate.AddSeconds(2 * 60 * 60);

// Set the exception date. 
var exceptionDate = startDate.AddSeconds(4 * 24 * 60 * 60);

// Add Schedule appointment
ScheduleAppointment recurrenceAppointment = new ScheduleAppointment
{
	StartTime = startDate,
	EndTime = endDate,
	Subject = (NSString)"Occurs Daily",
	AppointmentBackground = UIColor.Blue,
	RecurrenceRule = (NSString)"FREQ=DAILY;COUNT=20",
        RecurrenceExceptionDates = new ObservableCollection<NSDate> 
	{
           exceptionDate
	}
};

var exceptionAppointment = new ScheduleAppointment
{
	StartTime = exceptionDate.AddSeconds(2 * 60 * 60),
	EndTime = exceptionDate.AddSeconds(3 * 60 * 60),
	Subject = (NSString)"Meeting",
	AppointmentBackground = UIColor.Red,
	// set the parent appointment to recurrence Id
	RecurrenceId = recurrenceAppointment,
	 //Actual occurrence date
	ExceptionOccurrenceActualDate = exceptionDate
};
{% endhighlight %}
{% endtabs %}

>**NOTE**
•	`RecurrenceId` should be a recurrence pattern appointment object.
•	Exception appointment should be a normal appointment and should not be created as recurring appointment, since its occurrence from recurrence pattern.
•	`ActualDate` should be in Universal Time Coordinates (UTC) time zone.

![Recurrence Exception Appointment support in schedule Xamarin iOS](data_binding_images/exception_appointment.png)

#### Add exception appointment to recurrence pattern dynamically

You can also add exception appointment dynamically for added exception date by adding exception appointment to the schedule `ItemsSource` by using the `RecurrenceId` property of `AppointmentMapping` class which is used to map the custom exception appointment with schedule recurrence series appointment and `ExceptionOccurrenceActualDate` property of the `AppointmentMapping` class which is used to mention the actual series occurrence date of exception appointment of schedule recurrence appointment.

{% tabs %}
{% highlight c# %}
var recurrenceAppointment = scheduleAppointmentCollection[0];

// Add Exception appointment to recurrence series
var exceptionAppointment = new Meeting
{
	From = exceptionDate.AddSeconds(3 * 60 * 60),
	To = exceptionDate.AddSeconds(4 * 60 * 60),
	EventName = (NSString)"Meeting",
	Color = UIColor.Red,
	// set the parent appointment to recurrence Id
	RecurrenceID = recurrenceAppointment,
	 //Actual occurrence date
	ActualDate = exceptionDate
};
scheduleAppointmentCollection.Add(exceptionAppointment);
{% endhighlight %}
{% endtabs %}

>**NOTE**
•	`RecurrenceId` should be a recurrence pattern appointment object.
•	Exception appointment should be a normal appointment and should not be created as recurring appointment, since its occurrence from recurrence pattern.
•	`ActualDate` should be in Universal Time Coordinates (UTC) time zone.


#### Remove exception appointment from recurrence pattern
You can directly remove the added exception appointment for recurrence pattern by removing from the schedule `ItemsSource`.

{% tabs %}
{% highlight c# %}
var exceptionAppointment = scheduleAppointmentCollection[1];
scheduleAppointmentCollection.Remove(exceptionAppointment);
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo for Xamarin.iOS from
here [RecurrenceExceptions](https://github.com/SyncfusionExamples/Create-Recurrence-Exceptions-to-schedule-for-custom-recurring-appointments-in-Xamarin.iOS).

## Appearance Customization
The default appearance of the appointment can be customized by using the [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle.html) property and [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs.html). The event and property is used to customize or override the default template of the Appointments.

•	[Customize appearance using Style](https://help.syncfusion.com/xamarin-ios/sfschedule/data-bindings#customize-appearance-using-style) 
•	[Customize appearance using Event](https://help.syncfusion.com/xamarin-ios/sfschedule/data-bindings#customize-appearance-using-event)
•	[Customize appearance using Custom View](https://help.syncfusion.com/xamarin-ios/sfschedule/data-bindings#customize-appearance-using-custom-view)

### Customize appearance using Style
Schedule appointment can be customized by setting appointment style properties such as [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~TextColor.html), [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~TextStyle.html), [BorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~BorderColor.html), [BorderCornerRadius](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~BorderCornerRadius.html), [BorderWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~BorderWidth.html) to the `AppointmentStyle` property of `SfSchedule`.

{% tabs %}
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
{% endtabs %}

![Appointments styling support in schedule Xamarin iOS](data_binding_images/style.png)

### Customize appearance using Event
Schedule appointment can be customized during runtime using [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs.html). `ScheduleAppointment` style can be customized using the `AppointmentStyle` property.

[AppointmentLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs.html) has below properties,

•	[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs~Appointment.html) – Contains the appointments values.
•	[AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs~AppointmentStyle.html) – Gets and sets the appointments style.
•	[View](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs~View.html) -  Sets the Custom UI for Appointments.
•	[Bounds](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs~Bounds.html) – Contains the UI bounds of appointment.

{% tabs %}
{% highlight c# %} 
schedule.AppointmentLoaded += schedule_AppointmentLoaded;

...

private void schedule_AppointmentLoaded(object sender, AppointmentLoadedEventArgs e)
{       
	if(e.Appointment != null && e.Appointment.IsAllDay)
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
{% endtabs %}

![Appointments customization in schedule Xamarin iOS](PopulatingAppointments_images/appointmentstyle_event.png)

## Customize appearance using Custom View
Default appointment UI can be changed using `View` property passed through `AppointmentLoadedEventArgs`.

{% tabs %}
{% highlight c# %} 
schedule.AppointmentLoaded += schedule_AppointmentLoaded;

...

private void schedule_AppointmentLoaded(object sender, AppointmentLoadedEventArgs e)
{
	if (e.Appointment == null)
		return;	
	if (e.Appointment.IsAllDay)
	{
		UITextView textView = new UITextView();
		textView.BackgroundColor = (UIColor)e.Appointment.AppointmentBackground;
		textView.Text = (NSString)e.Appointment.Subject;
		e.View = textView;
	}
	else if (e.Appointment.Subject == "Retrospective")
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
		button.BackgroundColor = (UIColor)e.Appointment.AppointmentBackground;
		e.View = button;
	}
}
{% endhighlight %}
{% endtabs %}

![Custom view support for appointments in schedule Xamarin iOS](PopulatingAppointments_images/appointmentstyle_customview.png)

### Customize Font Appearance

You can change the appearance of Font by setting the [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~TextStyle.html) property of [AppointmentStyle](https://help.syncfusion.com/xamarin-ios/sfschedule/data-bindings#appearance-customization) property in Schedule.

{% tabs %}
{% highlight c# %}
appointmentStyle.TextStyle = UIFont.FromName("Lobster-Regular",15);
{% endhighlight %}
{% endtabs %}

![custom font support in schedule Xamarin iOS](data_binding_images/customfontappointment.png)

Refer [this](https://help.syncfusion.com/xamarin-ios/sfschedule/monthview#custom-font-setting-in-xamarinios) to configure the custom fonts in Xamarin.iOS.

## Selection
Schedule control has built-in events to handle tapped, double tapped and long pressed touch actions.

•	[CellTapped](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs.html)
•	[CellDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs.html)
•	[CellLongPressed](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs.html)

These events will be triggered while perform respective touch actions in timeslots, month cells and in appointments. All the three events contain the same argument [CellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs.html) which holds selected appointment and date time details in it.

• [SelectedAppointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs~SelectedAppointment.html) -  Contains the selected appointment value, it will be null, if any time slots selected.
• [Date](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.CellTappedEventArgs~Date.html) - Contains selected time slot DateTime value.

{% tabs %}
{% highlight c# %} 
schedule.CellTapped += Schedule_CellTapped;
schedule.CellDoubleTapped += Schedule_CellDoubleTapped;
schedule.CellLongPressed += Schedule_CellLongPressed;

...

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
{% endtabs %}

### Selection customization
The default selection of an appointment can be customized by using [SelectionBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~SelectionBorderColor.html), [SelectionTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle~SelectionTextColor.html) properties in `AppointmentStyle` property of `SfSchedule`. The property is used to customize or override the default selection of the appointments.

N> `BorderWidth` value must be set to highlight `SelectionBorderColor`.

{% tabs %}
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
{% endtabs %}

![Selection customization in schedule Xamarin iOS](data_binding_images/selection.png)

## Minimum Appointment Height

[MinHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~MinHeight.html) of an appointment is to set an arbitrary height to appointments when it has minimum duration, so that the subject can be readable.

{% tabs %}
{% highlight c# %}
SFSchedule schedule = new SFSchedule();
NSMutableArray appCollection = new NSMutableArray();
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
calendar.TimeZone = NSTimeZone.FromGMT(NSTimeZone.LocalTimeZone.GetSecondsFromGMT);
NSDate today = new NSDate();
NSDateComponents startDateComponents = calendar.Components(NSCalendarUnit.Year |
                                                           NSCalendarUnit.Month |
                                                           NSCalendarUnit.Day, today);
startDateComponents.Hour = 09;
startDateComponents.Minute = 0;
startDateComponents.Second = 0;
NSDateComponents endDateComponents = calendar.Components(NSCalendarUnit.Year |
                                                         NSCalendarUnit.Month |
                                                         NSCalendarUnit.Day, today);
endDateComponents.Hour = 09;
endDateComponents.Minute = 0;
endDateComponents.Second = 0;
NSDate startDate = calendar.DateFromComponents(startDateComponents);
NSDate endDate = calendar.DateFromComponents(endDateComponents);
NSDateComponents startDateComponents1 = calendar.Components(NSCalendarUnit.Year |
                                                            NSCalendarUnit.Month |
                                                            NSCalendarUnit.Day, today);
startDateComponents1.Hour = 11;
startDateComponents1.Minute = 0;
startDateComponents1.Second = 0;
NSDateComponents endDateComponents1 = calendar.Components(NSCalendarUnit.Year |
                                                          NSCalendarUnit.Month |
                                                          NSCalendarUnit.Day, today);
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
{% endtabs %}

![Minimum Appointment height support in schedule Xamarin iOS](data_binding_images/minheightios.png)

>**NOTE**
* `MinHeight` value will be set, when the an appointment height (duration) value lesser than MinHeight. 
* Appointment height (duration) value will be set, when the appointment height (duration) value greater than `MinHeight`.
* TimeInterval value will be set, when Minimum Height greater than TimeInterval with lesser appointment height (duration).
* `MinHeight` has ScheduleAppointmentMapping Support.
* All day Appointment does not support `MinHeight`.
