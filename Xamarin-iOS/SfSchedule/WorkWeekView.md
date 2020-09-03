---

layout: post
title: Customize work week view at Syncfusion Schedule control | Xamarin.iOS
description: Learn how to configure the view header, timeslots of schedule work week view in SfSchedule control for Xamarin.iOS
platform: xamarin.iOS
control: SfSchedule
documentation: ug

---


# Work Week View in Xamarin.iOS Schedule (SfSchedule)

Work week view is to view only working days of a particular week. By default, Saturday and Sunday are the non-working days. You can be customize it with any days of a Week. Appointments arranged in timeslots based on its duration with respective day of the week.

## ViewHeader Appearance
You can customize the default appearance of view header in [WorkWeekView](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFScheduleView.html) by using [DayHeaderStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_DayHeaderStyle) property of [SFSchedule](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html).

{% tabs %}
{% highlight c# %}
//Create new instance of Schedule
SFSchedule schedule = new SFSchedule();
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Customize the schedule view header
SFViewHeaderStyle viewHeaderStyle = new SFViewHeaderStyle();
viewHeaderStyle.BackgroundColor = UIColor.FromRGB(0, 150, 136);
viewHeaderStyle.DayTextColor = UIColor.FromRGB(255, 255, 255);
viewHeaderStyle.DateTextColor = UIColor.FromRGB(255, 255, 255);
viewHeaderStyle.DayTextStyle = UIFont.FromName("Arial", 15);
viewHeaderStyle.DateTextStyle = UIFont.FromName("Arial", 15);
schedule.DayHeaderStyle = viewHeaderStyle;		
{% endhighlight %}
{% endtabs %}

![Work week view view header appearance customization in schedule for Xamarin.iOS](daymodule_images/viewheaderappearance_workweek.png)

You can customize the height of the ViewHeader in `WorkWeekView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_ViewHeaderHeight) property of `SFSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
schedule.ViewHeaderHeight = 50;
{% endhighlight %}
{% endtabs %}

![Work week view view header height customization for schedule in Xamarin.iOS](daymodule_images/viewheaderheight_workweek.png)

### Customize Font Appearance

You can change the appearance of Font by setting the [DayTextStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFViewHeaderStyle.html#Syncfusion_SfSchedule_iOS_SFViewHeaderStyle_DayTextStyle) and [DateTextStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFViewHeaderStyle.html#Syncfusion_SfSchedule_iOS_SFViewHeaderStyle_DateTextStyle) properties of [ViewHeaderStyle](https://help.syncfusion.com/xamarin-ios/sfschedule/dayview#viewheader-appearance) property in Schedule..

{% tabs %}
{% highlight c# %}
viewHeaderStyle.DayTextStyle = UIFont.FromName("Lobster-Regular", 20);
viewHeaderStyle.DateTextStyle = UIFont.FromName("Lobster-Regular", 20);
{% endhighlight %}
{% endtabs %}

![Work week view custom font for view header for schedule in Xamarin.iOS](daymodule_images/customfontviewheader_workweek.png)

Refer [this](https://help.syncfusion.com/xamarin-ios/sfschedule/monthview#custom-font-setting-in-xamarinios) to configure the custom fonts in Xamarin.iOS.

### ViewHeader Date Format
You can customize the date and day format of `SFSchedule` ViewHeader by using [DateLabelFormat](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekLabelSettings_DateLabelFormat) and [DayLabelFormat](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekLabelSettings_DayLabelFormat) properties of `LabelSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Creating new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
//Creating new instance of WorkWeekLabelSettings
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
//Customizing date format
workWeekLabelSettings.DateLabelFormat = (NSString)"dd";
workWeekLabelSettings.DayLabelFormat = (NSString)"EEEE";
workWeekViewSettings.LabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view view header date format customization for schedule in Xamarin.iOS](daymodule_images/DateFormat_WorkWeek.png)

### ViewHeader Tapped Event
You can handle single tap action of ViewHeader by using [ViewHeaderTapped](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html) event of `SFSchedule`. This event will be triggered when the ViewHeader is Tapped. This event contains [ViewHeaderTappedEventArgs](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.ViewHeaderTappedEventArgs.html) argument which holds [Date](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.ViewHeaderTappedEventArgs.html#Syncfusion_SfSchedule_iOS_ViewHeaderTappedEventArgs_Date) details in it.

{% tabs %}
{% highlight c# %}
//Creating  new instance of Schedule
SFSchedule schedule = new SFSchedule();
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
schedule.ViewHeaderTapped += Handle_ViewHeaderTapped;

...

void Handle_ViewHeaderTapped(object sender, ViewHeaderTappedEventArgs e)
{
    var date = e.Date;
}
{% endhighlight %}
{% endtabs %}

## Change Time Interval
You can customize the interval of timeslots in `WorkWeekView` by setting [TimeInterval](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_TimeInterval) property of `SFSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
schedule.TimeInterval = 120;
{% endhighlight %}
{% endtabs %}

![Work week view time interval customization for schedule in Xamarin.iOS](daymodule_images/timeintervalworkweek.png)

>**NOTE**
If you modify the `TimeInterval` value (in minutes), you need to change the time labels format by setting the `TimeFormat` value as "hh:mm". By default, TimeFormat value is `"h aa"`. You can refer [here](https://help.syncfusion.com/xamarin-ios/sfschedule/workweekview#time-label-formatting) for changing TimeFormat value.

## Change Time Interval Height
You can customize the interval height of timeslots in `WorkWeekView` by setting [TimeIntervalHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_TimeIntervalHeight)  property of `SFSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
schedule.TimeIntervalHeight = 120;
{% endhighlight %}
{% endtabs %}

![Work week view time interval height customization for schedule in Xamarin.iOS](daymodule_images/workweekview_height.png)

## Change Working hours

Working hours in `WorkWeekView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_WorkStartHour) and [WorkEndHour](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_WorkEndHour) properties of [WorkWeekViewSettings](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html). You can also customize the working hours along with minutes by setting double value which will be converted to time.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeLabelFormat = (NSString)"hh:mm";
workWeekViewSettings.WorkStartHour = 11.5;
workWeekViewSettings.WorkEndHour = 17.5;
workWeekViewSettings.LabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work view working hours customization for schedule in Xamarin.iOS](daymodule_images/chnageworkinghour_workweek.png)

>**NOTE**
No need to specify the decimal point values for `WorkStartHour` and `WorkEndHour`, if you don’t want to set the minutes.

## Changing StartHour and EndHour

Default value for [StartHour](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_EndHour) value is 0 to 24 to show all the time slots in `WorkWeekView`. You need to set [StartHour](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_EndHour) property of `WorkWeekView`, to show only the required time duration for end users. You can also set `StartHour` and `EndHour` in double value which will be converted to time to show required time duration in minutes.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeLabelFormat = (NSString)"hh:mm";
workWeekViewSettings.StartHour = 7.5;
workWeekViewSettings.EndHour = 18.5;
workWeekViewSettings.LabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view customizing start and end hour for schedule in Xamarin.iOS](daymodule_images/changestartendhour_workweek.png)

>**NOTE**
* `StartHour` must be greater than or equal to 0 and `EndHour` must be lesser than or equal to 24, otherwise `InvalidDataException` will be thrown.
* `EndHour` value must be greater than `StartHour`, otherwise `InvalidDataException` will be thrown.
* Schedule UI such as Appointments and NonAccessibleBlocks which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.
* No need to specify the decimal point values for `StartHour` and `EndHour`, if you don’t want to set the minutes.
* The number of time slots will be calculated based on total minutes of a day and time interval (total minutes of a day ((start hour - end hour) * 60) / time interval).
* If the custom time interval is given, then the number of time slots calculated based on given time interval should result in integer value, otherwise given time interval will be neglected and default time interval (60 minutes) will be considered.
* If the custom start hour and end hour is given, then the number of time slots calculated based on given start hour, end hour should result in integer value, otherwise given end hour will be rounded off. For example, if StartHour is 7.2 (07:12AM), EndHour is 18.6 (06:36AM) and TimeInterval is 60 minutes, then EndHour will be rounded off to 18.2 (06:12PM).

## Timeslot Appearance
You can customize the appearance of timeslots in `WorkWeekView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-work-hours)
* [Timeslot customization in Non Working hours](#timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours

You can customize the appearance of the working hour timeslots by its color using[TimeSlotColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_TimeSlotColor),[TimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_TimeSlotBorderColor), [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_VerticalLineStrokeWidth), [VerticalTimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_VerticalTimeSlotBorderColor) and [HorizontalLineStrokeWidth](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_HorizontalLineStrokeWidth) properties of `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
workWeekViewSettings.TimeSlotBorderColor = UIColor.Purple;
workWeekViewSettings.VerticalTimeSlotBorderColor = UIColor.Blue;
workWeekViewSettings.TimeSlotColor = UIColor.Yellow;
workWeekViewSettings.HorizontalLineStrokeWidth = 3;
workWeekViewSettings.VerticalLineStrokeWidth = 3;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view time slot appearance customization for schedule in Xamarin.iOS](daymodule_images/timeslotappearance_workweek.png)

### Timeslot customization in Non Working hours

You can customize the appearance of the non-working hour timeslots by its color using[NonWorkingHourTimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_NonWorkingHourTimeSlotBorderColor),[NonWorkingHourTimeSlotColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_NonWorkingHourTimeSlotColor),`VerticalLineStrokeWidth`, ` VerticalTimeSlotBorderColor` and `HorizontalLineStrokeWidth`properties of `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
workWeekViewSettings.NonWorkingHourTimeSlotBorderColor = UIColor.Purple;
workWeekViewSettings.VerticalTimeSlotBorderColor = UIColor.Blue;
workWeekViewSettings.NonWorkingHourTimeSlotColor = UIColor.Yellow;
workWeekViewSettings.HorizontalLineStrokeWidth = 3;
workWeekViewSettings.VerticalLineStrokeWidth = 3;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view non working hours customization for schedule in Xamarin.iOS](daymodule_images/nonworkinghour_workweek.png)

>**NOTE**
`HorizontalLineStrokeWidth`and `VerticalLineStrokeWidth` properties are common to both Working hours and Non-Working hour time slot customization.

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as Non-accessible blocks by using[NonAccessibleBlockCollection](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_NonAccessibleBlockCollection) of `WorkWeekViewSettings` so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Create new instance of NonAccessibleBlock
NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock();
//Create new instance of NonAccessibleBlocksCollection
NSMutableArray nonAccessibleBlocksCollection = new NSMutableArray();
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
nonAccessibleBlock.StartHour = 13;
nonAccessibleBlock.EndHour = 14;
nonAccessibleBlock.Text = (NSString)"LUNCH";
nonAccessibleBlock.BackgroundColor = UIColor.Black;
nonAccessibleBlocksCollection.Add(nonAccessibleBlock);
workWeekViewSettings.NonAccessibleBlockCollection = nonAccessibleBlocksCollection;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Non accessible block support in schedule work week view for Xamarin.iOS](daymodule_images/nonaccessibletimeslot_workweek.png)

>**NOTE**
Selection and related events will not be working in this blocks.

## Change first day of week
By default, schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by using[FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_FirstDayOfWeek) property of `SFSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
schedule.FirstDayOfWeek = 3;
{% endhighlight %}
{% endtabs %}

![First day of week for work week view in schedule for Xamarin.iOS](daymodule_images/firstdayofweek_workweek.png)

## Time Label Formatting
You can customize the format for the labels which are mentioning the time, by setting [TimeLabelFormat](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekLabelSettings_TimeLabelFormat) property of [LabelSettings](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekViewSettings_LabelSettings) in `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
WorkWeekViewSettings workweekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeLabelFormat = (NSString)"hh mm";
workweekViewSettings.LabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workweekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view time label customization for schedule in Xamarin.iOS](daymodule_images/timelabelformat_workweek.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_iOS_WorkWeekLabelSettings_TimeLabelColor) property of `LabelSettings` in `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
//Create new instance of WorkWeekLabelSettings
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeLabelColor = UIColor.Blue;
workWeekViewSettings.LabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view time label appearance customization for schedule in Xamarin.iOS](daymodule_images/timelabelappearance_workweek.png)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection customization using style
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_SelectionStyle) property of `SFSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Create new instance of SelectionStyle
SFSelectionStyle selectionStyle = new SFSelectionStyle();
selectionStyle.BackgroundColor = UIColor.Blue;
selectionStyle.BorderColor = UIColor.Black;
selectionStyle.BorderThickness = 5;
selectionStyle.BorderCornerRadius = 5;
schedule.SelectionStyle = selectionStyle;
{% endhighlight %}
{% endtabs %}

![Selection style for schedule Work week view in Xamarin.iOS](daymodule_images/selectionstyle_workweek.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_SelectionView) property of `SFSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
//Add the CustomView
UIButton customView = new UIButton();
customView.SetTitle("+NewEvent", UIControlState.Normal);
customView.BackgroundColor = UIColor.FromRGB(255, 152, 0);
customView.SetTitleColor(UIColor.White, UIControlState.Normal);
schedule.SelectionView = customView;
{% endhighlight %}
{% endtabs %}

![Custom selection view support for schedule Work week view in Xamarin.iOS](daymodule_images/selectioncustomview_workweek.png)

### Programmatic selection
You can programmatically select the specific timeslot by setting corresponding date and time value to [SelectedDate](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_SelectedDate) property of `SFSchedule`. By default, it is null.

{% tabs %}
{% highlight C# %}
// Creating instance of calendar
NSCalendar calendar = new NSCalendar(NSCalendarType.Gregorian);
calendar.TimeZone = NSTimeZone.FromGMT(NSTimeZone.LocalTimeZone.GetSecondsFromGMT);

// Creating instance of date
NSDate date = new NSDate();

// Setting a date and time to select
NSDateComponents dateComponents = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, date);
dateComponents.Year = 2017;
dateComponents.Month = 10;
dateComponents.Day = 04;
dateComponents.Hour = 10;
schedule.SelectedDate = calendar.DateFromComponents(dateComponents);
{% endhighlight %}
{% endtabs %}

You can clear the selection by setting [SelectedDate](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_SelectedDate) as null.

{% tabs %}
{% highlight C# %}
// Setting null value to deselect
schedule.SelectedDate = null;
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo for Xamarin.iOS from here [Date_Selection](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Date_Selection481745259.zip)

>**NOTE**
* `SFSchedule` does not support multiple selection.
* `SFSchedule` supports two-way binding of `SelectedDate` property.

![Programmatic selection support for schedule Work week view in Xamarin.iOS](daymodule_images/selection_WorkWeek.png)


