---

layout: post
title: Populating Appointments in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to Populate Appointments in SfSchedule control
platform: xamarin.ios
control: SfSchedule
documentation: ug

---


# Appointments

[ScheduleAppointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment.html) is a class, which holds the details about the appointment to be rendered in schedule. It has some basic properties such as [StartTime](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~StartTime.html), [EndTime](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~EndTime.html), [Subject](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Subject.html) and some additional information about the appointment can be added using [AppointmentBackground](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~AppointmentBackground.html), [Notes](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Notes.html), [Location](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~Location.html), [All Day](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~IsAllDay.html), [Recursive properties](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.RecurrenceProperties.html).

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
            NSDateComponents endDateComponents = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);

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
            NSDateComponents endDateComponents = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);

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

## Recurrence Appointment
Recurring an appointment on a daily, weekly, monthly, or yearly interval. Recursive appointments can be created by enabling `IsRecursive` property in Schedule appointments. 

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

### Adding Recurrence Appointment using Recurrence Builder
Schedule appointment [RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.ScheduleAppointment~RecurrenceRule.html) is used to populate the required recursive appointment collection in a specific pattern. `RRULE` can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

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
            recurrenceProperties.IsWeeklySunday = false;
            recurrenceProperties.IsWeeklyMonday = true;
            recurrenceProperties.IsWeeklyTuesday = false;
            recurrenceProperties.IsWeeklyWednesday = false;
            recurrenceProperties.IsWeeklyThursday = false;
            recurrenceProperties.IsWeeklyFriday = false;
            recurrenceProperties.IsWeeklySaturday = false;
            recurrenceProperties.RangeRecurrenceCount = 10;
            recurrenceProperties.RecurrenceRule = ScheduleHelper.RRuleGenerator(recurrenceProperties, scheduleAppointment.StartTime, scheduleAppointment.EndTime);

        // Setting Recurrence rule to Schedule Appointment
            scheduleAppointment.RecurrenceRule = recurrenceProperties.RecurrenceRule;

        //Adding Schedule appointment in Schedule Appointment Collection 
            schedule.Appointments = appCollection; 
{% endhighlight %} 

## Appearance Customization
The default appearance of the appointment can be customized by using the [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFAppointmentStyle.html) property and [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.AppointmentLoadedEventArgs.html). The event and property is used to customize or override the default template of the Appointments.

•	Customize appearance using Style 
•	Customize appearance using Event
•	Customize appearance using Custom View

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
			if (e.Appointment != null && e.Appointment.Subject == "Meeting")
			{
				e.AppointmentStyle.BorderColor = UIColor.Blue;
				e.AppointmentStyle.BorderCornerRadius = 12;
				e.AppointmentStyle.BorderWidth = 2;
				e.AppointmentStyle.SelectionBorderColor = UIColor.Yellow;
				e.AppointmentStyle.SelectionTextColor = UIColor.Yellow;
			}
		}

{% endhighlight %}

## Customize appearance using Custom View
Default appointment UI can be changed using `View` property passed through `AppointmentLoadedEventArgs`.

{% highlight c# %} 
 
     schedule.AppointmentLoaded += schedule_AppointmentLoaded;

        void schedule_AppointmentLoaded(object sender, AppointmentLoadedEventArgs e)

		{
			UIButton button = new UIButton();
			button.BackgroundColor = UIColor.Green;
			if(e.Appointment!=null)
				button.SetTitle((NSString)e.Appointment.Subject, UIControlState.Normal);
			e.View = button;
		}

 
{% endhighlight %}

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

N>**Note:** `BorderWidth` value must be set to highlight `SelectionBorderColor`.

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
