---

layout: post
title: Customize the Schedule WorkWeekView at SfSchedule control for Xamarin.iOS
description: Learn how to Customize the schedule WorkWeekView in SfSchedule control
platform: xamarin.iOS
control: SfSchedule
documentation: ug

---


# WorkWeekView

WorkWeekView is to view only working days of a particular week. By default, Saturday and Sunday are the non-working days. You can be customize it with any days of a Week. Appointments arranged in timeslots based on its duration with respective day of the week.

## ViewHeader Appearance
You can customize the default appearance of view header in [WorkWeekView](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFScheduleView.html) by using [DayHeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~DayHeaderStyle.html) property of [SFSchedule](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule.html).

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
![](daymodule_images/viewheaderappearance_workweek.png)

You can customize the height of the ViewHeader in `WorkWeekView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~ViewHeaderHeight.html) property of `SFSchedule`.

{% highlight C# %}

        schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
		schedule.ViewHeaderHeight = 50;
			
{% endhighlight %}

![](daymodule_images/viewheaderheight_workweek.png)

## Change Time Interval
You can customize the interval of timeslots in `WorkWeekView` by setting [TimeInterval](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~TimeInterval.html) property of `SFSchedule`.

{% highlight C# %}

    schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
	schedule.TimeInterval = 120;
{% endhighlight %}
![](daymodule_images/timeintervalworkweek.png)

>**Note**:

If you modify the `TimeInterval` value (in minutes), you need to change the time labels format by setting the `TimeFormat` value as "hh:mm". By default, TimeFormat value is `"h aa"`. You can refer [here](https://help.syncfusion.com/xamarin-ios/sfschedule/workweekview#time-label-formatting) for changing TimeFormat value.

## Change Time Interval Height
You can customize the interval height of timeslots in `WorkWeekView` by setting [TimeIntervalHeight](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~TimeIntervalHeight.html)  property of `SFSchedule`.

{% highlight C# %}

    schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
    schedule.TimeIntervalHeight = 120;
{% endhighlight %}

![](daymodule_images/workweekview_height.png)

## Change Working hours

Working hours in `WorkWeekView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~WorkStartHour.html) and [WorkEndHour](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~WorkEndHour.html) properties of [WorkWeekViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings.html).

{% highlight C# %}

            schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
			//Create new instance of WorkWeekViewSettings
			WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
			workWeekViewSettings.WorkStartHour = 10;
			workWeekViewSettings.WorkEndHour = 18;
			schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}

![](daymodule_images/chnageworkinghour_workweek.png)

>**Note**:
	`WorkStartHour` and `WorkEndHour` should be in integer value to represent hours.

## Changing StartHour and EndHour

Default value for [StartHour](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~StartHour.html) and [EndHour](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~EndHour.html) value is 0 to 24 to show all the time slots in `WorkWeekView`. You need to set [StartHour](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~StartHour.html) and [EndHour](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~EndHour.html) property of `WorkWeekView`, to show only the required time duration for end users.

{% highlight C# %}

            schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
			//Create new instance of WorkWeekViewSettings
			WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
			workWeekViewSettings.StartHour = 08;
			workWeekViewSettings.EndHour = 15;
			schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}

![](daymodule_images/changestartendhour_workweek.png)

>**Note**:
* `StartHour` and `EndHour` should be in integer value to represent hours.
* `StartHour` must be greater than or equal to 0 and `EndHour` must be lesser than or equal to 24, otherwise `Invalid DataException` will be thrown.
* `EndHour` value must be greater than `StartHour`, otherwise `InvalidDataException`  will be thrown.
* Schedule UI such as Appointments and NonAccessibleBlocks which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.

## Timeslot Appearance
You can customize the appearance of timeslots in `WorkWeekView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-work-hours)
* [Timeslot customization in Non Working hours](#timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours

You can customize the appearance of the working hour timeslots by its color using[TimeSlotColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~TimeSlotColor.html),[TimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~TimeSlotBorderColor.html), [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~VerticalLineStrokeWidth.html), [VerticalTimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~VerticaTimeSlotBorderColor.html) and [HorizontalLineStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~HorizontalLineStrokeWidth.html) properties of `WorkWeekViewSettings`.

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

![](daymodule_images/timeslotappearance_workweek.png)


### Timeslot customization in Non Working hours

You can customize the appearance of the non-working hour timeslots by its color using[NonWorkingHourTimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~NonWorkingHourTimeSlotBorderColor.html),[NonWorkingHourTimeSlotColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~NonWorkingHourTimeSlotColor.html),`VerticalLineStrokeWidth`, ` VerticalTimeSlotBorderColor` and `HorizontalLineStrokeWidth`properties of `WorkWeekViewSettings`.

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

![](daymodule_images/nonworkinghour_workweek.png)

>**Note**:
`HorizontalLineStrokeWidth`and `VerticalLineStrokeWidth` properties are common to both Working hours and Non-Working hour time slot customization.

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as Non-accessible blocks by using[NonAccessibleBlockCollection](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~NonAccessibleBlockCollection.html) of `WorkWeekViewSettings` so that you can allocate those timeslots for predefined events/activities like Lunch hour.

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

![](daymodule_images/nonaccessibletimeslot_workweek.png)


>**Note**:
Selection and related events will not be working in this blocks.

## Change first day of week
By default, schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by using[FirstDayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~FirstDayOfWeek.html) property of `SFSchedule`.
{% highlight C# %}

            schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
			schedule.FirstDayOfWeek = 3;
{% endhighlight %}

![](daymodule_images/firstdayofweek_workweek.png)

## Time Label Formatting
You can customize the format for the labels which are mentioning the time, by setting [TimeLabelFormat](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekLabelSettings~TimeLabelFormat.html) property of [LabelSettings](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekViewSettings~LabelSettings.html) in `WorkWeekViewSettings`.

{% highlight C# %}

            schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
			WorkWeekViewSettings workweekViewSettings = new WorkWeekViewSettings();
			WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
			workWeekLabelSettings.TimeLabelFormat = (NSString)"hh mm";
			workweekViewSettings.LabelSettings = workWeekLabelSettings;
			schedule.WorkWeekViewSettings = workweekViewSettings;
{% endhighlight %}

![](daymodule_images/timelabelformat_workweek.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.WorkWeekLabelSettings~TimeLabelColor.html) property of `LabelSettings` in `WorkWeekViewSettings`.

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

![](daymodule_images/timelabelappearance_workweek.png)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection customization using style
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~SelectionStyle.html) property of `SFSchedule`.

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

![](daymodule_images/selectionstyle_workweek.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~SelectionView.html) property of `SFSchedule`.
{% highlight C# %}

          schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
			//Add the CustomView  
			UIButton customView = new UIButton();
			customView.SetTitle("+NewEvent", UIControlState.Normal);
			customView.BackgroundColor = UIColor.FromRGB(255, 152, 0);
			customView.SetTitleColor(UIColor.White, UIControlState.Normal);
			schedule.SelectionView = customView;
{% endhighlight %}

![](daymodule_images/selectioncustomview_workweek.png)

### Programmatic selection
You can programmatically select the specific timeslot by setting corresponding date and time value to [SelectedDate]( https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~SelectedDate.html) property of `SFSchedule`. By default, it is null.

{% highlight C# %}

    // Creating instance of calendar
    NSCalendar calendar = NSCalendar.CurrentCalendar;

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

You can clear the selection by setting [SelectedDate]( https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~SelectedDate.html) as null.

{% highlight C# %}

    // Setting null value to deselect
    schedule.SelectedDate = null;

{% endhighlight %}

You can download the entire source code of this demo for Xamarin.iOS from here [Date_Selection](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Date_Selection481745259.zip)

>**Note**:
* `SFSchedule` does not support multiple selection.
* `SFSchedule` supports two-way binding of `SelectedDate` property.

![](daymodule_images/selection_WorkWeek.png)

