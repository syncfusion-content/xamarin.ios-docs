---
layout: post
title: Appearance & Stylings in Schedule
description: How to Customize appointment and day cell.
platform: Xamarin.iOS
control: SfSchedule
documentation: ug
---

# Appearance & Styling

## Header Customization

You can customize the header of the Schedule using `HeaderStyle` and `HeaderHeight` property in schedule.

### Header Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% highlight c# %}

	sfSchedule.HeaderHeight = 50;

{% endhighlight %}

### Labels

you can change the header format and style using `HeaderStyle` property in schedule.

#### Format

You can change the header text format and size using `ScheduleDateHeaderSize` and `ScheduleDateHeaderFormat` property in `HeaderStyle`

{% highlight c# %}

	sfSchedule.ScheduleDateHeaderFormat = (NSString)("MMM yyyy");

{% endhighlight %}

#### Fonts and colors

You can change the backgroundcolor,text style and text size using properties such as `BackgroundColor`,`TextStyle`, `TextSize` of Header using `HeaderStyle` property in schedule.

{% highlight c# %}

	SFHeaderStyle headerStyle = new SFHeaderStyle();
	headerStyle.BackgroundColor = UIColor.Gray;
	headerStyle.TextStyle = UIFont.SystemFontOfSize(20, UIFontWeight.Bold);	
	headerStyle.TextColor = UIColor.Red;
	sfSchedule.HeaderStyle = headerStyle;

{% endhighlight %}

## View Header Customization

	You can customize the header of the Schedule using `ViewHeaderStyle` and `ViewHeaderHeight` property in schedule.

### Labels

#### Fonts and Colors

You can change the backgroundcolor,text style and text size using properties such as `BackgroundColor`,`DateTextStyle`, `DayTextStyle`, `DayTextColor`, `DateTextColor`,`DateTextSize`, `DayTextSize` of ViewHeader using `DayHeaderStyle` property in schedule.

{% highlight c# %}

	SFViewHeaderStyle viewHeaderStyle = new SFViewHeaderStyle();
	viewHeaderStyle.BackgroundColor = UIColor.Gray;
	viewHeaderStyle.DayTextSyle = UIFont.SystemFontOfSize(20, UIFontWeight.Bold);
	viewHeaderStyle.DateTextSyle = UIFont.SystemFontOfSize(20, UIFontWeight.Bold);
	viewHeaderStyle.DayTextColor = UIColor.Blue;
	viewHeaderStyle.DateTextColor = UIColor.Blue;
	sfSchedule.DayHeaderStyle = viewHeaderStyle;

{% endhighlight %}

### ViewHeader Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% highlight c# %}

	sfSchedule.ViewHeaderHeight = 30;

{% endhighlight %}

![](AppearanceandStyling_images/Header_iOS.png)

## Timeslots customization

### Custom Day View

#### Non-Working Hours 

You can differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor` properties of `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	sfschedule = new SfSchedule(this);

	//setting schedule view
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.NonWorkingHourTimeSlotBorderColor = UIColor.Gray;
	dayViewSettings.NonWorkingHourTimeSlotColor = UIColor.Black;
	sfSchedule.DayViewSettings = dayViewSettings;

	// Set our view from the "main" layout resource
	this.View.AddSubview(sfSchedule);

{% endhighlight %}

#### Timeslots 

You can differentiate working hours with non-working hour timeslots by its color using  `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SFSchedule sfSchedule = new SFSchedule();

	//setting schedule view
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewDay;
	
	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.TimeSlotColor = UIColor.White;
	dayViewSettings.TimeSlotBorderColor = UIColor.Blue;
	dayViewSettings.TimeSlotStrokeWidth = 2;
	sfSchedule.DayViewSettings = dayViewSettings;

	View.AddSubview(sfSchedule);

{% endhighlight %}

#### Labels

You can change the format , colors, size, style of text using `DateFormat` and `DayFormat`, `DateLabelSize`,`DayLabelSize`,`TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `DayLabelSettings` in `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SFSchedule sfschedule = new SFSchedule();

	//setting schedule view
	sfschedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

	DayViewSettings dayViewSettings = new DayViewSettings();
	DayLabelSettings dayLabelSettings = new DayLabelSettings();
	dayLabelSettings.DateLabelFormat = (NSString)"d/M/yyyy";
	dayLabelSettings.DateLabelSize = 15;
	dayLabelSettings.DayLabelSize = 15;
	dayLabelSettings.DayLabelFormat = (NSString) "ddd";
	dayLabelSettings.TimeLabelFormat = (NSString) "hh mm";
	dayLabelSettings.TimeLabelColor = UIColor.Blue;
	dayLabelSettings.TimeLabelSize = 10;
	dayViewSettings.LabelSettings = dayLabelSettings;
	sfschedule.DayViewSettings = dayViewSettings;


	View.AddSubview(sfschedule);

{% endhighlight %}

#### All Day Appointments color

You can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor` of `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SFSchedule sfschedule = new SFSchedule();

	//setting schedule view
	sfschedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.AllDayAppointmentLayoutColor = UIColor.Blue;
	sfschedule.DayViewSettings = dayViewSettings;

	View.AddSubview(sfschedule);

{% endhighlight %}

![](AppearanceandStyling_images/NonWorkingHours_Day_iOS.png)

### Custom Week View

#### Non-Working Hours 

You can differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor` properties of `WeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;

	//setting day view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.NonWorkingHourTimeSlotBorderColor = UIColor.Gray;
	weekViewSettings.NonWorkingHourTimeSlotColor = UIColor.LightGray;
	sfSchedule.WeekViewSettings = weekViewSettings;

	View.AddSubview(sfSchedule);
	SetContentView(sfschedule);

{% endhighlight %}

#### Timeslots 

You can differentiate working hours with non-working hour timeslots by its color using `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WeekViewSettings`.

{% highlight c# %}

	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;

	//setting day view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.TimeSlotColor = UIColor.Gray;
	weekViewSettings.TimeSlotBorderColor = UIColor.LightGray;
	sfSchedule.WeekViewSettings = weekViewSettings;

	View.AddSubview(sfSchedule);

{% endhighlight %}

#### Lines

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WeekViewSettings`.

{% highlight c# %}

	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;

	//setting day view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.VerticalLineStrokeWidth = 2;
	weekViewSettings.VerticaTimeSlotBorderColor = UIColor.LightGray;
	sfSchedule.WeekViewSettings = weekViewSettings;

	View.AddSubview(sfSchedule);

{% endhighlight %}

#### Labels

You can change the format , colors, size, style of text using `DateFormat` and `DayFormat`, `DateLabelSize`,`DayLabelSize`,`TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `WeekLabelSettings` in `WeekViewSettings`.

{% highlight c# %}

	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleViewWeek;

	WeekViewSettings weekViewSettings = new WeekViewSettings();
	WeekLabelSettings labelSettings = new WeekLabelSettings();
	labelSettings.TimeLabelSize = 15;
	labelSettings.DateLabelSize = 15;
	labelSettings.DayLabelSize = 15;
	labelSettings.DateLabelFormat = (NSString)"dd/MM/yy";
	labelSettings.DayLabelFormat = (NSString)" - EEEE";
	labelSettings.TimeLabelFormat = (NSString)"hh a";
	labelSettings.TimeLabelColor = UIColor.Blue;

	weekViewSettings.LabelSettings = labelSettings;
	sfSchedule.WeekViewSettings = weekViewSettings;

{% endhighlight %}

#### All Day Appointments Color

You can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor` of `WeekViewSettings`.

{% highlight c# %}

	SFSchedule sfschedule = new SFSchedule();

	//setting schedule view
	sfschedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;

	//setting day view settings properties
	WeekViewSettings weekViewSetings = new WeekViewSettings();
	weekViewSetings.AllDayAppointmentLayoutColor = UIColor.Blue;
	sfschedule.WeekViewSettings = weekViewSetings;

	View.AddSubview(sfschedule);

{% endhighlight %}

![](AppearanceandStyling_images/NonWorkingHours_Week_iOS.png)

### Custom Work Week View

#### Non-Working Hours 

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor` properties of `WorkWeekViewSettings`.

{% highlight c# %}

	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;

	//setting day view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	workWeekViewSettings.NonWorkingHourTimeSlotColor = UIColor.LightGray;
	workWeekViewSettings.NonWorkingHourTimeSlotBorderColor = UIColor.Blue;
	sfSchedule.WorkWeekViewSettings = workWeekViewSettings;

	View.AddSubview(sfSchedule);

{% endhighlight %}

#### Timeslots

You can also differentiate working hours with non-working hour timeslots by its color using `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.

{% highlight c# %}

	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;

	//setting day view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	workWeekViewSettings.TimeSlotColor = UIColor.LightGray;
	workWeekViewSettings.TimeSlotBorderColor = UIColor.Blue;
	sfSchedule.WorkWeekViewSettings = workWeekViewSettings;

{% endhighlight %}

#### Lines

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WorkWeekViewSettings`.

{% highlight c# %}

	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;

	//setting day view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	workWeekViewSettings.VerticalLineStrokeWidth = 2;
	workWeekViewSettings.VerticaTimeSlotBorderColor = UIColor.Black;
	sfSchedule.WorkWeekViewSettings = workWeekViewSettings;

	View.AddSubview(sfSchedule);

{% endhighlight %}

#### Labels

You can change the format , colors, size, style of text using `DateFormat` and `DayFormat`, `DateLabelSize`,`DayLabelSize`,`TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `WorkWeekLabelSettings` in `WorkWeekViewSettings`.

{% highlight c# %}

	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;

	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	WorkWeekLabelSettings labelSettings = new WorkWeekLabelSettings();
	labelSettings.TimeLabelSize = 15;
	labelSettings.DateLabelSize = 15;
	labelSettings.DayLabelSize = 15;
	labelSettings.DateLabelFormat = (NSString)"dd/MM/yy";
	labelSettings.DayLabelFormat = (NSString)" - EEEE";
	labelSettings.TimeLabelFormat = (NSString)"hh a";
	labelSettings.TimeLabelColor = UIColor.Blue;

	workWeekViewSettings.LabelSettings = labelSettings;
	sfSchedule.WorkWeekViewSettings = workWeekViewSettings;

	View.AddSubview(sfSchedule);

{% endhighlight %}

#### All Day Appointments Panel

You can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor` of `WorkWeekViewSettings`.

{% highlight c# %}

	SFSchedule sfSchedule = new SFSchedule();
	sfSchedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;

	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	workWeekViewSettings.AllDayAppointmentLayoutColor = UIColor.Blue;
	sfSchedule.WorkWeekViewSettings = workWeekViewSettings;

	View.AddSubview(sfSchedule);

{% endhighlight %}

![](AppearanceandStyling_images/NonWorkingHours_WorkWeek_iOS.png)

### Interval

You can change the time interval and time interval height using `TimeInterval` and `TimeIntervalHeight` in schedule.

{% highlight c# %}

	sfSchedule.TimeInterval = 5;
	sfSchedule.TimeIntervalHeight = 10;

{% endhighlight %}

![](AppearanceandStyling_images/TimeInterval_iOS.png)
