---
layout: post
title: Getting started with Syncfusion Essential Schedule for iOS
description: How to create a Schedule, add Appointments, enable Inline and other functionalities
platform: xamarin.iOS
control: SfSchedule
documentation: ug
---

# Getting Started

This section explains you the steps required to render the `Meeting Room Booking Scheduler` using Schedule control by populating events(appointments) in the control. This section covers only the minimal features that you need to know to get started with the Schedule

### Configure the Schedule control

The following steps explain you how to create and configure a Schedule.

1. Add reference to the SfSchedule in view controller as follows.

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically: {Syncfusion Installed location}\Essential Studio{version number}\lib
You have to add the following assembly reference to the iOS unified project ios-unifed \ Syncfusion.SfSchedule.iOS.dll

N> Assemblies are available in unzipped package location in Mac.

## Initializing Schedule

Initialize `SfSchedule` instance in viewDidLoad method and then add the schedule as a sub view of  self view.

{% highlight c# %}

    public ScheduleViews ()
    {
        SFSchedule meetingRoomScheduler = new SFSchedule();
        meetingRoomScheduler.ScheduleView = SFScheduleView.SFScheduleViewWeek;
        View.AddSubview(meetingRoomScheduler);
    }

{% endhighlight %}

You can change the default UI of schedule using `ScheduleView` to display the dates in different layouts available in the control.

{% highlight c# %}

    //setting schedule view.
    meetingRoomScheduler.ScheduleView = SFScheduleView. SFScheduleViewWeek;
    View.AddSubview(meetingRoomScheduler);

{% endhighlight %}

## Populating Events

You can add events to the schedule by creating collection of `ScheduleAppointments` using `ScheduleAppointmentCollection`. You can schedule meetings for a particular day by setting `From` and `To` of `Meeting` class.Here meeting appointments are created for around 20 days before and after current day, with single appointment each day and with 3 appointments each day(from three days before current day to three days after the current day)


{% highlight c# %}

    public ScheduleViews ()
    {
        SFSchedule meetingRoomScheduler = new SFSchedule();
        meetingRoomScheduler.ScheduleView = SFScheduleView.SFScheduleViewWeek;
        meetingRoomScheduler.Appointments = CreateAppointments();
        View.AddSubview(meetingRoomScheduler);
    }
    
    NSMutableArray CreateAppointments()
    {
        NSDate today = new NSDate();
        InitializeDataForBookings();
        NSMutableArray appCollection = new NSMutableArray();
        NSCalendar calendar = NSCalendar.CurrentCalendar;

        NSDateComponents DateFrom = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);			
        DateFrom.Day -= 10;
        NSDate dateFrom = calendar.DateFromComponents(DateFrom);

        NSDateComponents DateTo = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
        DateTo.Day += 10;

        NSDateComponents DateRangeStart = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
        DateRangeStart.Day -= 3;
        NSDate dateRangeStart = calendar.DateFromComponents(DateRangeStart);

        NSDateComponents DateRangeEnd = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
        DateRangeEnd.Day += 3;
        NSDate dateRangeEnd = calendar.DateFromComponents(DateRangeEnd);

        Random randomTime = new Random();
        List<CGPoint> randomTimeCollection = GettingTimeRanges();

        NSDateComponents startDate = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, dateFrom);
        startDate.Calendar = calendar;

        NSDateComponents endDate = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, dateFrom);

    for (int dateIndex = -10; dateIndex <= 11;dateIndex++)
    {
        if ((startDate.Date.Compare(dateRangeStart) > 0) && (startDate.Date.Compare(dateRangeEnd) < 0))
        {
        for (int AdditionalAppointmentIndex = 0; AdditionalAppointmentIndex < 3; AdditionalAppointmentIndex++)
            {
            
            var hour = randomTime.Next((int)randomTimeCollection[AdditionalAppointmentIndex].X, (int)randomTimeCollection[AdditionalAppointmentIndex].Y);
            startDate.Hour = hour;
            endDate.Hour = (startDate.Hour) + 1;

            NSDate startdate = calendar.DateFromComponents(startDate);
            NSDate enddate = calendar.DateFromComponents(endDate);

            ScheduleAppointment meeting = new ScheduleAppointment();
            meeting.StartTime = startdate;
            meeting.EndTime = enddate;
            meeting.Subject = (NSString)subjectCollection[randomTime.Next(9)];
            meeting.AppointmentBackground = colorCollection[randomTime.Next(9)];

            appCollection.Add(meeting);
            }
        }
        else {
            var hour = randomTime.Next(9, 16);
            startDate.Hour = hour;
            endDate.Hour = (startDate.Hour) + 1;
            
            NSDate  startdate= calendar.DateFromComponents(startDate);
NSDate enddate = calendar.DateFromComponents(endDate);

            ScheduleAppointment meeting = new ScheduleAppointment();
            meeting.StartTime = startdate;
            meeting.EndTime = enddate;
            meeting.Subject = (NSString)subjectCollection[randomTime.Next(9)];
            meeting.AppointmentBackground = colorCollection[randomTime.Next(9)];

            appCollection.Add(meeting);
        }
        startDate.Day++;
        endDate.Day++;
        }
    return appCollection;
    }
    
{% endhighlight %}

You can add `Subject` and `Color` to the appointments created by creating a collection for the same.

{% highlight c# %}
    
    List<String> meetingCollection;
    List<UIColor> colorCollection;

    private void InitializeDataForBookings()
    {
    //adding subject collection
    meetingCollection = new List<String>();
    meetingCollection.Add("GoToMeeting");
    meetingCollection.Add("Business Meeting");
    meetingCollection.Add("Conference");
    meetingCollection.Add("Project Status Discussion");
    meetingCollection.Add("Auditing");
    meetingCollection.Add("Client Meeting");
    meetingCollection.Add("Generate Report");
    meetingCollection.Add("Target Meeting");
    meetingCollection.Add("General Meeting");
    meetingCollection.Add("Pay House Rent");
    meetingCollection.Add("Car Service");
    meetingCollection.Add("Medical Check Up");
    meetingCollection.Add("Wedding Anniversary");
    meetingCollection.Add("Sam's Birthday");
    meetingCollection.Add("Jenny's Birthday");

    // adding colors collection
    colorCollection = new List<UIColor>();
    colorCollection.Add(UIColor.FromRGB(0xA2, 0xC1, 0x39));
    colorCollection.Add(UIColor.FromRGB(0xD8, 0x00, 0x73));
    colorCollection.Add(UIColor.FromRGB(0x1B, 0xA1, 0xE2));
    colorCollection.Add(UIColor.FromRGB(0xE6, 0x71, 0xB8));
    colorCollection.Add(UIColor.FromRGB(0xF0, 0x96, 0x09));
    colorCollection.Add(UIColor.FromRGB(0x33, 0x99, 0x33));
    colorCollection.Add(UIColor.FromRGB(0x00, 0xAB, 0xA9));
    colorCollection.Add(UIColor.FromRGB(0xE6, 0x71, 0xB8));
    colorCollection.Add(UIColor.FromRGB(0x1B, 0xA1, 0xE2));
    colorCollection.Add(UIColor.FromRGB(0xD8, 0x00, 0x73));
    colorCollection.Add(UIColor.FromRGB(0xA2, 0xC1, 0x39));
    colorCollection.Add(UIColor.FromRGB(0xD8, 0x00, 0x73));
    colorCollection.Add(UIColor.FromRGB(0x33, 0x99, 0x33));
    colorCollection.Add(UIColor.FromRGB(0xE6, 0x71, 0xB8));
    colorCollection.Add(UIColor.FromRGB(0x00, 0xAB, 0xA9));
    }

{% endhighlight %}

![](GettingStarted_images/GettingStarted_iOS.png)
