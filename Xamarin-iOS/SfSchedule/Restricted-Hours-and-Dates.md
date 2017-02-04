---
layout: post
title: Restricted Hours and Dates in Schedule
description: How to restrict the hours and dates of Schedule control.
platform: xamarin.iOS
control: SfSchedule
documentation: ug
---

# Restricted Hours And Dates 

## Non-Accessible blocks

### Day View

You can restrict/allocate certain timeslot as non-accessible block using `NonAccessibleBlocks` of `DayViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewDay;

    DayViewSettings dayViewSettings = new DayViewSettings ();
    //Non-AccessbleBlocks
    NonAccessibleBlock lunch_hour = new NonAccessibleBlock ();
    lunch_hour.StartHour = 13;
    lunch_hour.EndHour = 14;
    lunch_hour.Text = (NSString)"LUNCH";
    dayViewSettings.NonAccessibleBlockCollection.Add (lunch_hour);
    schedule.DayViewSettings = dayViewSettings;

    this.AddSubview (schedule);
    this.control = this;

{% endhighlight %}

### Week View

You can restrict/allocate certain timeslot as non-accessible block using `NonAccessibleBlocks` of `WeekViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWeek;
    WeekViewSettings weekSettings = new WeekViewSettings ();
   
    //Non-AccessibleBlocks
    NonAccessibleBlock lunch_hour = new NonAccessibleBlock ();
    lunch_hour.StartHour = 13;
    lunch_hour.EndHour = 14;
    lunch_hour.Text = (NSString)"LUNCH";
    weekSettings.NonAccessibleBlockCollection.Add (lunch_hour);

    schedule.WeekViewSettings = weekSettings;
    this.AddSubview (schedule);
    this.control = this;

{% endhighlight %}

### WorkWeek View

You can restrict/allocate certain timeslot as non-accessible block using `NonAccessibleBlocks` of `WorkWeekViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewWorkWeek;
    WorkWeekViewSettings workWeekSettings = new WorkWeekViewSettings ();
    //Non-AccessbleBlocks
    NonAccessibleBlock lunch_hour = new NonAccessibleBlock ();
    lunch_hour.StartHour = 13;
    lunch_hour.EndHour = 14;
    lunch_hour.Text = (NSString)"LUNCH";
    workWeekSettings.NonAccessibleBlockCollection.Add (lunch_hour);
    schedule.WorkWeekViewSettings = workWeekSettings;
    this.AddSubview (schedule);
    this.control = this;

{% endhighlight %}

## Blackout Dates

You can restrict/allocate certain month cell as blackout days using `BlackoutDates` of `MonthViewSettings`, so that we can allocate those cells for predefined events/activities like Scheduled maintenance, planned leave etc.

{% highlight c# %}

    SFSchedule schedule= new SFSchedule ();
    schedule.ScheduleView = SFScheduleView.SFScheduleViewMonth;
    
    NSDate today = new NSDate ();
    NSCalendar calendar = NSCalendar.CurrentCalendar;
    // Get the year, month, day from the date
    NSDateComponents components = calendar.Components (
    NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
    
    MonthViewSettings monthViewSettings = new MonthViewSettings ();
    monthViewSettings.BlackoutDates = new NSMutableArray ();
    components.Day -= 3;
    for (int i = 0; i < 3; i++) {
    NSDate startDate = calendar.DateFromComponents (components);
    components.Day += 1;
    monthViewSettings.BlackoutDates.Add (startDate);
    }
    
    schedule.MonthViewSettings = monthViewSettings;
    this.AddSubview (schedule);
    this.control = this;

{% endhighlight %}

![](Localization_images/Localization_img2.jpeg)