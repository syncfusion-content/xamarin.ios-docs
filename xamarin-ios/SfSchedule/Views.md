---
layout: post
title: Types of Schedule Views.
description: How to create Views in Schedule control.
platform: xamarin.iOS
control: SfSchedule
documentation: ug
---

# Views

Schedule control provides four different types of views to display dates. Day view, Week view, WorkWeek view and Month view. It can be assigned to the schedule control by using `ScheduleView` property. Based on the user’s preference appointments can be viewed in any of the four type of view available. By default schedule control is assigned with day view.

## Day View

Day view is used to display a single day; current day will be visible by default. Appointments on a specific day will be arranged in respective timeslots based on its duration.

{% highlight c# %}

    schedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

{% endhighlight %}

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `DayLabelSettings` of `DayViewSettings` and the size of those strings are also customizable.

You can differentiate the timeslot panel using `VerticaTimeSlotBorderColor` properties of `DayViewSettings`.To know more about customization of time slot panel refer [Timeslots Customization](/xamarin-ios/sfschedule/Appearance-and-Styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewDay;
    
    DayViewSettings dayViewSettings = new DayViewSettings ();
    DayLabelSettings labelSettings= new DayLabelSettings();
    labelSettings.TimeLabelSize =  8;
    labelSettings.DateLabelSize = 25;
    labelSettings.DateLabelFormat = (NSString)"dd/MM/yy";
    labelSettings.DayLabelFormat = (NSString)" - EEEE";
    labelSettings.TimeLabelFormat =(NSString) "hh a";

    dayViewSettings.LabelSettings= labelSettings;
    schedule.DayViewSettings = dayViewSettings;

    View.AddSubview(schedule);

{% endhighlight %}

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and `WorkEndHour` properties of `DayViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHourTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `DayViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-ios/sfschedule/Appearance-and-Styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

    DayViewSettings dayViewSettings = new DayViewSettings ();

    dayViewSettings.WorkStartHour=8;
    dayViewSettings.WorkEndHour = 18;
    schedule.DayViewSettings = dayViewSettings;

    View.AddSubview(schedule);

{% endhighlight %}

#### All Day Appointments Color

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of `DayViewSettings` as true. 

Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`. To know more about customization of all day appointment panel refer [Timeslots Customization](/xamarin-ios/sfschedule/Appearance-and-Styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

    DayViewSettings dayViewSettings = new DayViewSettings ();
    dayViewSettings.ShowAllDay = true;
    schedule.DayViewSettings = dayViewSettings;

   View.AddSubview(schedule);

{% endhighlight %}

![](Views_images/DayView_iOS.png)

## Week View

To view all the seven days of a particular week, by default if will be current week.Appointments arranged in timeslots based on its duration with respective day of the week.

{% highlight c# %}

    schedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;

{% endhighlight %}

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `WeekLabelSettings` of `WeekViewSettings` and the size of those strings are also customizable.

Also you can differentiate the timeslot panel using `VerticaTimeSlotBorderColor` properties of `WeekViewSettings`. To know more about customization of time slot panel refer [Timeslots Customization](/xamarin-ios/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;
    WeekViewSettings weekSettings = new WeekViewSettings ();
    
    WeekLabelSettings labelSettings= new WeekLabelSettings();
    labelSettings.TimeLabelSize =  8;
    labelSettings.DateLabelSize = 20;
    labelSettings.DateLabelFormat = (NSString)"dd";
    labelSettings.DayLabelFormat = (NSString)"eee";
    labelSettings.TimeLabelFormat =(NSString) "hh a";
    weekSettings.LabelSettings= labelSettings;
    schedule.WeekViewSettings = weekSettings;
    
    View.AddSubview(schedule);

{% endhighlight %}

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and  `WorkEndHour`  properties of `WeekViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotColor`, `TimeSlotColor` and `TimeSlotBorderColor` properties of `WeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-ios/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;
    WeekViewSettings weekSettings = new WeekViewSettings ();
    weekSettings.WorkStartHour=8;
    weekSettings.WorkEndHour = 18; 
    schedule.WeekViewSettings = weekSettings;
    View.AddSubview(schedule);

{% endhighlight %}

#### All Day Appointments Color

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of `WeekViewSettings` as true.

Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`.To know more about customization of All day appointment panel refer [Timeslots Customization](/xamarin-ios/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;
    WeekViewSettings weekSettings = new WeekViewSettings ();
    weekSettings.ShowAllDay = true;
    schedule.WeekViewSettings = weekSettings;
    View.AddSubview(schedule);

{% endhighlight %}

![](Views_images/WeekView_iOS.png)

## Work Week View

To view working days of a particular week, by default current work week will be displayed. Saturday and Sunday are the non-working days by default; it can be customized with any days in a week. Appointments arranged in timeslots based on its duration with respective day of the week.

{% highlight c# %}

    schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;

{% endhighlight %}

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `WorkWeekLabelSettings` of  `WorkWeekViewSettings` and the size of those strings are also customizable.

Also you can differentiate the timeslot panel using `VerticaTimeSlotBorderColor` properties of `WorkWeekViewSettings`.To know more about customization of time slot panel refer [Timeslots Customization](/xamarin-ios/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
    WorkWeekViewSettings workWeekSettings = new WorkWeekViewSettings ();
    WorkWeekLabelSettings labelSettings= new WorkWeekLabelSettings();
    labelSettings.TimeLabelSize =  8;
    labelSettings.DateLabelSize = 20;
    labelSettings.DayLabelSize = 5;
    labelSettings.DateLabelFormat = (NSString)"dd";
    labelSettings.DayLabelFormat = (NSString)"eee";
    labelSettings.TimeLabelFormat =(NSString) "hh a";
    workWeekSettings.LabelSettings= labelSettings;
    schedule.WorkWeekViewSettings = workWeekSettings;
    View.AddSubview(schedule);

{% endhighlight %}

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and  `WorkEndHour` properties of `WorkWeekViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotColor`, `TimeSlotColor` and `TimeSlotBorderColor` properties of `WorkWeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
    WorkWeekViewSettings workWeekSettings = new WorkWeekViewSettings ();
    workWeekSettings.WorkStartHour=8;
    workWeekSettings.WorkEndHour = 18; 
    schedule.WorkWeekViewSettings = workWeekSettings;
    View.AddSubview(schedule);

{% endhighlight %}

#### All Day Appointments Color

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of `WorkWeekViewSettings` as true. 

Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`.To know more about customization of All day appointment panel refer [Timeslots Customization](/xamarin-ios/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
    WorkWeekViewSettings workWeekSettings = new WorkWeekViewSettings ();
    workWeekSettings.ShowAllDay = true;
    schedule.WorkWeekViewSettings = workWeekSettings;
    View.AddSubview(schedule);

{% endhighlight %}

### Non-Working Days

By using this non working days support, you can set the Schedule WeekView as only with Working days. You can hide the non working days using `NonWorkingDays` property in `WorkWeekViewSettings` of `Schedule`.

![](Views_images/WorkWeekView_iOS.png)

## Month View

To view entire dates of a particular month, by default current month will be displayed initially. Appointments arranged within the cell based on its duration. Current date is differentiated by some color and rest of the dates in a month will be in different color., Also the color differentiation for dates will be applicable for previous and next month dates.

{% highlight c# %}

    schedule.ScheduleView = SFScheduleView.SFScheduleViewMonth;

{% endhighlight %}

### MonthInlineView

Month Inline view is to view the appointments in the paricular day in Monthview, appointments available in a particular day will be listed in inline view. 

#### Show Appointments Inline 

By setting `ShowAppointmentsInline` property in the MonthViewSettings, you enable/ disable the Month `InlineView` in `MonthView`. Appointments available in a particular day will be listed in inline view, if no appointments in the day dispalyes text as `No Events`. 

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewMonth;

    //setting Show inline 
    schedule.MonthViewSettings.ShowAppointmentsInline = true;

{% endhighlight %}

#### Inline View Customization

Using the Inline View Customization support you can customize the Schedule month Inline view by properties as well as CustomView, To know more about Inline view customization of Month cell refer [View Customization](/xamarin-ios/sfschedule/view-customization "View Customization").

#### Inline Appointment Customization

Using the Inline Appointment Customization support you can customize the Schedule month Inline view Appointments by properties as well as CustomView. To know more about Inline appointment customization of Month cell refer [View Customization](/xamarin-ios/sfschedule/view-customization "View Customization").

#### InlineAppointmentTapped Event
Using the  `InlineAppointmentTapped` Event you can get the details of appointments in inline using `InlineAppointmentTapped` event in `Schedule`. Details of the selected  appointment and the corresponding date is passed through `InlineAppointmentTappedEventArgs` as `selectedAppointment` and `selectedDate` respectively. To know more about Inline view customization of Month cell refer [View Customization](/xamarin-ios/sfschedule/view-customization "View Customization").

### Month Navigation Direction

`MonthView` of Schedule can be navigated horizontally and vertically.You can change the direction of navigation through `MonthNavigationDirection` property of `MonthViewSettings`.By default MonthNavigation value is `Horizontal`

{% highlight C# %}

	MonthViewSettings monthViewSettings = new MonthViewSettings();
	//To navigate vertically
	monthViewSettings.MonthNavigationDirection =  SFMonthNavigationDirections.Vertical;
	sfschedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}

### MonthCell Customization

By using the MonthCell Customization support, you can customize the Schedule Month Cell in the `MonthView` by properties as well as CustomView. To know more about  MonthCell Customization, please refer [View Customization](/xamarin-ios/sfschedule/view-customization "View Customization").

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `MonthLabelSettings` of  `MonthViewSettings` and the size of those strings are also customizable.

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewMonth;
    
    MonthViewSettings monthViewSettings = new MonthViewSettings ();
    MonthLabelSettings labelSettings =  new MonthLabelSettings();
    labelSettings.DayLabelSize = 10;
    labelSettings.DayLabelFormat = (NSString)"EEEE";
    labelSettings.DateLabelFormat = (NSString)"d";
    labelSettings.DateLabelSize =  12;

    monthViewSettings.LabelSettings = labelSettings;
    schedule.MonthViewSettings = monthViewSettings;
    View.AddSubview(schedule);

{% endhighlight %}

#### Week number

You display the week number of the year in month view by setting `ShowWeekNumber` property of `MonthViewSettings` are true. By default it is false.

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewMonth;
    MonthViewSettings monthViewSettings = new MonthViewSettings ();
    monthViewSettings.ShowWeekNumber = true;
    schedule.MonthViewSettings = monthViewSettings;
    View.AddSubview(schedule);

{% endhighlight %}

#### Visible AppointmentCount

You can customize the number of appointments to be rendered inside a month view cell using `VisibleCellAppointmentsCount` property of `MonthViewSettings`.

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewMonth;
    MonthViewSettings monthViewSettings = new MonthViewSettings ();
    monthViewSettings.VisibleCellAppointmentsCount=10;
    schedule.MonthViewSettings = monthViewSettings;
    View.AddSubview(schedule);

{% endhighlight %}

![](Views_images/MonthVew_iOS.png)