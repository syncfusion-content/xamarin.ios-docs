---   
layout: post   
title: MonthView   
description: Overview of MonthView related features
platform: xamarin.ios   
control: SfSchedule   
documentation: ug   
---   
    
# Month View
`MonthView` of `SfSchedule` used to display entire dates of the specific month, current month will be displayed by default initially. Current date color is differentiated with other dates of the current month, also the color differentiation for dates will be applicable for previous and next month dates.

{% tabs %}
{% highlight c# %}

			schedule.ScheduleView = SFScheduleView.SFScheduleViewMonth;

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthview.png)

## Month Appointment indicator
In `MonthView`, appointments are not viewed in the month cell instead appointment indicators are drawn. You can customize the number of appointment indicators displayed in month cell using  [AppointmentIndicatorCount](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthViewSettings~AppointmentIndicatorCount.html) property of [MonthViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~MonthViewSettings.html) in `SfSchedule`, by default Appointment indicator count is 3.

{% highlight c# %}

			//creating new instance for month view settings
			MonthViewSettings monthViewSettings = new MonthViewSettings();
			monthViewSettings.AppointmentIndicatorCount = 2;
			schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}

![](monthview_images/appointmentindicator.png)

>**Notes**: If appointments count are lesser than the `AppointmentIndicatorCount` value in the particular day, then according to number of appointments available, indicator will be displayed in the month cell.Maximum number of appointment indicators drawn in the month cell is 6.

## Month Inline View
You can use [ShowAppointmentsInline](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthViewSettings~ShowAppointmentsInline.html) bool property in [MonthViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~MonthViewSettings.html) to enable / disable the month inline view, by setting `ShowAppointmentsInline` property as `true` you can view the Appointments in the specific date. 

{% tabs %}
{% highlight c# %}

			//creating new instance for month view settings
			MonthViewSettings monthViewSettings = new MonthViewSettings();
			monthViewSettings.ShowAppointmentsInline = true;
			schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}
{% endtabs %}

![](monthview_images/appointmentindicator.png)

>**Notes**: If appointments not there in the selected day, Inline view displays the text as "No Events"      

## Month Navigation direction
`MonthView` of Schedule can be navigated in both horizontal and vertical direction. You can change the direction of navigation through [MonthNavigationDirection](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthViewSettings~MonthNavigationDirection.html) property of `MonthViewSettings` in `SfSchedule`, by default Month navigation direction is `Horizontal`.

{% tabs %}
{% highlight c# %}

			monthViewSettings.MonthNavigationDirection = SFMonthNavigationDirections.Vertical;

{% endhighlight %}
{% endtabs %}

## Restricted days in Month
You can disable the interaction for certain date in Month view by using [BlackoutDates](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthViewSettings~BlackoutDates.html) of `MonthViewSettings`, using this you can allocate / restrict the specific date for predefined events.

{% tabs %}
{% highlight c# %}

			//creating new instance for month view settings
			MonthViewSettings monthViewSettings = new MonthViewSettings();
			monthViewSettings.BlackoutDates = new NSMutableArray();
			NSDate today = new NSDate();
			NSCalendar calendar = NSCalendar.CurrentCalendar;
			// Get the year, month, day from the date
			NSDateComponents components = calendar.Components(
			NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
			components.Day += 1;
			for (int i = 0; i < 3; i++)
			{
				NSDate startDate = calendar.DateFromComponents(components);
				components.Day += 1;
				monthViewSettings.BlackoutDates.Add(startDate);
			}
			schedule.MonthViewSettings = monthViewSettings;


{% endhighlight %}
{% endtabs %}

![](monthview_images/blackoutdate.png)

## First day of Week in Month
You can set First day of week using [FirstDayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~FirstDayOfWeek.html) property of `SfSchedule`, by default schedule control will rendered with `Sunday` as the first day of the week. 

{% tabs %}
{% highlight c# %}

			//setting FirstDayOfWeek
			schedule.FirstDayOfWeek = 2; // Monday

{% endhighlight %}
{% endtabs %}

![](monthview_images/firstdayofweek.png)

## Week Number of the Year in Month
You can display the Week Number of the year in Month View by setting [ShowWeekNumber](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthViewSettings~ShowWeekNumber.html) property of `MonthViewSettings` as `true`, by default it is `false`.

{% tabs %}
{% highlight c# %}

			monthViewSettings.ShowWeekNumber = true;

{% endhighlight %}
{% endtabs %}

![](monthview_images/showweeknumber.png)

## Week Number Appearance
You can customize the Week Number appearance by using [SFWeekNumberStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFWeekNumberStyle.html) property of `MonthViewSettings`. Week number [BackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFWeekNumberStyle~BackgroundColor.html), [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFWeekNumberStyle~TextColor.html) and [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFWeekNumberStyle~TextStyle.html) can be customized using `SFWeekNumberStyle` properties.

{% tabs %}
{% highlight c# %}

			//creating new instance for WeekNumberStyle
			SFWeekNumberStyle weekNumberStyle = new SFWeekNumberStyle();
			weekNumberStyle.TextStyle = UIFont.FromName("Arial", 15);
			weekNumberStyle.BackgroundColor = UIColor.Blue;
			weekNumberStyle.TextColor = UIColor.White;
			monthViewSettings.WeekNumberStyle = weekNumberStyle;
			schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}
{% endtabs %}

![](monthview_images/weeknumberstyle.png)

## Month Label Formatting 
You can change the Format of the Month date and day labels string in the Schedule using [DateLabelFormat](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthLabelSettings~DateLabelFormat.html), [DayLabelFormat](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthLabelSettings~DayLabelFormat.html) and [DateLabelSize](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthLabelSettings~DateLabelSize.html) properties of [LabelSettings](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthLabelSettings.html) in `MonthViewSettings`. 

{% tabs %}
{% highlight c# %}

			//creating new instance for MonthLabelSettings
			MonthLabelSettings monthLabelSettings = new MonthLabelSettings();
			monthLabelSettings.DayLabelFormat = (NSString)"EEEE";
			monthLabelSettings.DateLabelFormat = (NSString)"dd";
			monthLabelSettings.DateLabelSize = 20;
			monthViewSettings.LabelSettings = monthLabelSettings;
			schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthlabelformat.png)

## View Header Appearance  
You can customize the View Header appearance by using [SFViewHeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFViewHeaderStyle.html) property in SfSchedule. View Header [BackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFViewHeaderStyle~BackgroundColor.html), [DayTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFViewHeaderStyle~DayTextColor.html) and [DayTextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFViewHeaderStyle~DayTextSyle.html) can be customized using `SFViewHeaderStyle` properties.

{% tabs %}
{% highlight c# %}

			//creating new instance for viewHeaderStyle 
			SFViewHeaderStyle viewHeaderStyle = new SFViewHeaderStyle();
			viewHeaderStyle.BackgroundColor = UIColor.Blue;
			viewHeaderStyle.DayTextColor = UIColor.White;
			viewHeaderStyle.DayTextStyle = UIFont.FromName("Arial", 15);
			schedule.DayHeaderStyle = viewHeaderStyle;

{% endhighlight %}
{% endtabs %}

![](monthview_images/viewheaderstyle.png)

## MonthCell Appearance 
You can customize the Month view cell in three ways,

* [Customize month cell using style](#customize-month-cell-using-style)
* [Customize month cell using event](#customize-month-cell-using-event)
* [Customize month cell with custom UI](#customize-month-cell-with-custom-ui)

### Customize month cell using style
By using [SFMonthCellStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle.html) of `SfSchedule` you can customize the month cell properties such as [BackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~BackgroundColor.html), [NextMonthBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~NextMonthBackgroundColor.html), [NextMonthTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~NextMonthTextColor.html), [PreviousMonthBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~PreviousMonthBackgroundColor.html), [PreviousMonthTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~PreviousMonthTextColor.html), [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~TextColor.html), [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~TextStyle.html), [TodayBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~TodayBackgroundColor.html) and [TodayTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFMonthCellStyle~TodayTextColor.html).
   
{% tabs %}
{% highlight c# %}

			//creating new instance for SFMonthCellStyle 
			SFMonthCellStyle monthCellStyle = new SFMonthCellStyle();
			monthCellStyle.BackgroundColor = UIColor.Blue;
			monthCellStyle.NextMonthBackgroundColor = UIColor.White;
			monthCellStyle.NextMonthTextColor = UIColor.Gray;
			monthCellStyle.PreviousMonthBackgroundColor = UIColor.White;
			monthCellStyle.PreviousMonthTextColor = UIColor.Gray;
			monthCellStyle.TextColor = UIColor.White;
			monthCellStyle.TextStyle = UIFont.FromName("Arial", 20);
			monthCellStyle.TodayBackgroundColor = UIColor.Red;
			monthCellStyle.TodayTextColor = UIColor.White;
			schedule.MonthCellStyle = monthCellStyle;

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthcellstyle.png)
    
### Customize month cell using event
By using [MonthCellLoaded](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~MonthCellLoaded_EV.html) event in `SfSchedule`, you can customize the month cell properties in the run time. In `MonthCellLoaded` event, arguments such as [CellStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~CellStyle.html), [Appointments](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~Appointments.html), [Date](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~Date.html), [View](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~View.html) and boolean properties such as [IsToday](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~IsToday.html), [IsNextMonthDate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~IsNextMonthDate.html), [IsPreviousMonthDate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~IsPreviousMonthDate.html) and [IsBlackOutDate](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~IsBlackOutDate.html) are in the [MonthCellLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs.html). 

{% tabs %}
{% highlight c# %}

			schedule.MonthCellLoaded += Schedule_MonthCellLoaded;
			...
			void Schedule_MonthCellLoaded(object sender, MonthCellLoadedEventArgs e)
		{
			e.CellStyle = new SFCellStyle();
			if (e.IsToday)
			{
				e.CellStyle.BackgroundColor = UIColor.Red;
				e.CellStyle.TextColor = UIColor.Blue;
				e.CellStyle.TextStyle = UIFont.FromName("Arial-BoldItalicMT", 25);
			}
			else if (e.IsNextMonthDate)
			{
				e.CellStyle.BackgroundColor = UIColor.White;
				e.CellStyle.TextColor = UIColor.Gray;
				e.CellStyle.TextStyle = UIFont.FromName("Arial", 15);
			}
			else if (e.IsPreviousMonthDate)
			{
				e.CellStyle.BackgroundColor = UIColor.White;
				e.CellStyle.TextColor = UIColor.Gray;
				e.CellStyle.TextStyle = UIFont.FromName("Arial", 15);
			}
			else if (e.IsBlackOutDate)
			{
				e.CellStyle.BackgroundColor = UIColor.Black;
				e.CellStyle.TextColor = UIColor.Blue;
				e.CellStyle.TextStyle = UIFont.FromName("Arial", 15);
			}
			else
			{
				e.CellStyle.BackgroundColor = UIColor.Blue;
				e.CellStyle.TextColor = UIColor.White;
				e.CellStyle.TextStyle = UIFont.ItalicSystemFontOfSize(20);
			}
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthcellstyle_event.png)

#### Customize month cell with custom UI 
You can set the Custom UI for the month cell using [View](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthCellLoadedEventArgs~View.html) property of `MonthCellLoadedEventArgs` in the `MonthCellLoaded` event of `SfSchedule`.

{% tabs %}
{% highlight c# %}

			schedule.MonthCellLoaded += Schedule_MonthCellLoaded;
			...
			void Schedule_MonthCellLoaded(object sender, MonthCellLoadedEventArgs e)
		{
			NSCalendar calendar = NSCalendar.CurrentCalendar;
			// Get the year, month, day from the date
			NSDateComponents dateComponents = calendar.Components(NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, e.Date);
			UIButton button = new UIButton();
			button.SetTitle(dateComponents.Day.ToString(), UIControlState.Normal);
			button.SetTitleColor(UIColor.White, UIControlState.Disabled);
			if (e.IsToday)
			{
				button.BackgroundColor = UIColor.Red;
				button.Font = UIFont.FromName("Arial-BoldItalicMT", 20);
			}
			else
			{
				button.BackgroundColor = UIColor.Blue;
				button.Font = UIFont.ItalicSystemFontOfSize(20);
			}
			e.View = button;
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/monthcellcustomview.png)

## Getting Inline Appointment details
Using [Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthInlineAppointmentTappedEventArgs~Appointment.html) argument in the [MonthInlineAppointmentTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthInlineAppointmentTappedEventArgs.html) of [MonthInlineAppointmentTapped](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~MonthInlineAppointmentTapped_EV.html) event, you can get the details Month Inline Appointments details while tapping the specific appointment. You can do the required functions while tapping the inline appointment using this event. 

{% tabs %}
{% highlight c# %}

			schedule.MonthInlineAppointmentTapped += Schedule_MonthInlineAppointmentTapped;
			...
			void Schedule_MonthInlineAppointmentTapped(object sender, MonthInlineAppointmentTappedEventArgs e)
		{
			var appointment = (e.Appointment as ScheduleAppointment);
			UIAlertView alert = new UIAlertView()
			{
				Title = appointment.Subject,
				Message = appointment.StartTime.ToString()
			};
			alert.AddButton("OK");
			alert.Show();
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/inlineappointmentdetails.png)

## InlineView Appearance  
By using [MonthInlineLoaded](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~MonthInlineLoaded_EV.html) in `SfSchedule`, you can customize the month inline view properties in the run time. In `MonthInlineLoadedEvent`, arguments such as [MonthInlineViewStyle](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthInlineLoadedEventArgs~MonthInlineViewStyle.html), [Appointments](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthInlineLoadedEventArgs~Appointments.html) and [Date](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthInlineLoadedEventArgs~Date.html) are in the MonthInlineLoadedEventArgs.

{% tabs %}
{% highlight c# %}

			schedule.MonthInlineLoaded += Schedule_MonthInlineLoaded;
			...
			void Schedule_MonthInlineLoaded(object sender, MonthInlineLoadedEventArgs e)
		{
			SFMonthInlineViewStyle monthInlineViewStyle = new SFMonthInlineViewStyle();
			monthInlineViewStyle.BackgroundColor = UIColor.Black;
			monthInlineViewStyle.TextColor = UIColor.Green;
			monthInlineViewStyle.TextStyle = UIFont.FromName("Times New Roman", 13);
			monthInlineViewStyle.TimeTextColor = UIColor.Green;
			monthInlineViewStyle.TimeTextStyle = UIFont.ItalicSystemFontOfSize(13);
			monthInlineViewStyle.TimeTextFormat = (NSString)"hh mm a";
			e.MonthInlineViewStyle = monthInlineViewStyle;
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/inlineviewstyle.png)

## Inline Appointment Appearance 
You can customize the Month inline view Appointment by using [MonthInlineAppointmentLoaded](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.SFSchedule~MonthInlineAppointmentLoaded_EV.html) event in `SfSchedule`, using [View](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthInlineAppointmentLoadedEventArgs~View.html) of [MonthInlineAppointmentLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthInlineAppointmentLoadedEventArgs.html) argument. You can get the details of Appointment in the [Appointment](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfschedule/Syncfusion.SfSchedule.iOS~Syncfusion.SfSchedule.iOS.MonthInlineAppointmentLoadedEventArgs~Appointment.html) argument.

{% tabs %}
{% highlight c# %}

			schedule.MonthInlineAppointmentLoaded += Schedule_MonthInlineAppointmentLoaded;
			...
			void Schedule_MonthInlineAppointmentLoaded(object sender, MonthInlineAppointmentLoadedEventArgs e)
		{
			UIButton button = new UIButton();
			button.SetTitle(e.Appointment.Subject, UIControlState.Normal);
			button.SetTitleColor(UIColor.White, UIControlState.Disabled);
			button.BackgroundColor = UIColor.Blue;
			button.Font = UIFont.ItalicSystemFontOfSize(20);
			e.View = button;
		}

{% endhighlight %}
{% endtabs %}

![](monthview_images/inlinecustomview.png)


