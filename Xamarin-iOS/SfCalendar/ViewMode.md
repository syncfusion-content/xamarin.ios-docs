---
layout: post
title: Accessing View modes in Syncfusion Calendar control for Xamarin.iOS
description: Learn how to change the view mode for calendar
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Built-in Views

SfCalendar control provides two types of views to display dates such as month view and year view. It can be assigned to the SfCalendar control by using view mode property.

By default SfCalendar control is assigned with month view. Based on the user’s preference SfCalendar viewed in any of the available two type.

## Month View

This displays entire dates of a particular month, by default current month will be displayed on loading. The current date is provided with seperate color different from the rest of the dates color in a month. The events availability will be denoted within the cell based on its duration.

The dates in month view can be selected by three ways such as single, multiple and range which can be modified using `SelectionMode`.

{% highlight c# %}

	calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeMonth;

{% endhighlight %}

![](images/month_view.png)                                        


### Month View Settings

* Current day text color can be modified using `TodayTextColor`. 
* The month view label settings class has the APIs to change date text size, day text size and format options. 
* The background color of the inline view can be modified using `InlineBackgroundColor` property.
* The blackoutdate color can be modified with `BlackoutColor` property.

{% highlight c# %}

	SFMonthLabelSettings labelSettings = new SFMonthLabelSettings();
	labelSettings.DateFormat = “dd”;
	labelSettings.DayLabelSize = 20;
	labelSettings.DayFormat = "EEE";
	labelSettings.DateLabelSize =  12;
	SFMonthViewSettings monthViewSettings = new SFMonthViewSettings();
	monthViewSettings.TodayTextColor=UIColor.ParseColor("#1B79D6");
	monthViewSettings.InlineBackgroundColor=UIColor.ParseColor("#E4E8ED");
	monthViewSettings.WeekDayBackGroundColor=UIColor.ParseColor("#F7F7F7");
	monthviewSettings.MonthLabelSettings = labelSettings;
	calendar.MonthViewSettings=monthViewSettings;
	
{% endhighlight %}

N> The view modes can be switched by clicking the Header Text in MonthView or by selecting a month in YearView


## YearView

This displays entire dates/month of a particular year, by default current year will be displayed on loading. The years can be changed by swiping back and forth. The months can be navigated quickly by selecting on the particular month in year view.

{% highlight c# %}

	calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeYear;
	
{% endhighlight %}

![](images/year_view.png)                                        


### Year View Settings

* The month header color can be modified using `MonthHeaderTextColor` property.
* The year header and date text color can be changed using `YearTextColor` and `DateTextColor` properties respectively.
* The gravity of the month name can be modified using `LabelAlignment` property, to position it to left, right or center. 
* The complete layout’s background color can be modified using `YearLayoutBackground` property.

{% highlight c# %}

	SFCalendar calendar = new SFCalendar();
	SFYearViewSettings yearViewSettings = new SFYearViewSettings();
	yearViewSettings.YearHeaderTextColor=Color.parseColor("#1B79D6");
	yearViewSettings.MonthHeaderBackground=Color.parseColor("#E4E8ED");
	yearViewSettings.DateTextColor=Color.RED;
	yearViewSettings.HeaderLabelAlignment=LabelAlignment.Center;
	calendar.YearViewSettings=yearViewSettings;
	this.AddSubview(calendar);

{% endhighlight %}


