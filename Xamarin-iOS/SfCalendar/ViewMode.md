---
layout: post
title: Accessing View modes in Syncfusion Calendar control for Xamarin.iOS
description: Learn how to change the view mode for calendar
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Built-in Views

`SfCalendar` control provides two types of views to display dates such as month view and year view. It can be assigned to the `SfCalendar` control by using view mode property.

By default `SfCalendar` control is assigned with month view. Based on the user’s preference `SfCalendar` viewed in any of the available two type.

## Month view

This displays entire dates of a particular month, by default current month will be displayed on loading. The current date is provided with unique color different from the rest of the dates color in a month. The events availability will be denoted within the cell based on its duration.

The dates in month view can be selected by three ways such as single, multiple and range which can be modified using `SelectionMode`.

{% highlight c# %}

	calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeMonth;

{% endhighlight %}

![Month View in Xamarin.iOS Calendar](images/xamarin.ios-calendar-month_view.png)

## Trailing and leading days

The `SfCalendar` allows you hide the days of the next month and previous month in calendar to enhance the appearance. This can be achieved by enabling the [ShowLeadingAndTrailingDays]((https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfcalendar/Syncfusion.SfCalendar.iOS~Syncfusion.SfCalendar.iOS.ShowLeadingAndTrailingDays.html)) property. The following code demonstrates how to hide the leading and trailing dates in calendar.

{% tabs %}

{% highlight c# %}

SFCalendar calendar = new SFCalendar();
calendar.ViewMode = SFCalendarViewMode.SFCalendarViewModeMonth;;
calendar.ShowLeadingAndTrailingDays = true;
View.AddSubView(calendar);

{% endhighlight %}

{% endtabs %}

![Month View in Xamarin.iOS Calendar](images/Xamarin.iOS-Calendar-HideLeadingTrailingDates.png)

N>
* The DrawMonthCell event is triggered for the current month dates.
* The VisibleDates in the MonthChanged event will return the current month dates.                                        


## Month view customization

* Current day text color can be modified using [TodayTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfcalendar/Syncfusion.SfCalendar.iOS~Syncfusion.SfCalendar.iOS.SFMonthViewSettings~TodayTextColor.html). 
* The month view label settings class has the APIs to change date text size, day text size and format options. 
* The background color of the inline view can be modified using [InlineBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfcalendar/Syncfusion.SfCalendar.iOS~Syncfusion.SfCalendar.iOS.SFMonthViewSettings~InlineBackgroundColor.html) property.

{% highlight c# %}

SFMonthViewSettings monthViewSettings = new SFMonthViewSettings();
monthViewSettings.TodayTextColor = UIColor.FromRGB(27, 121, 214);
monthViewSettings.InlineBackgroundColor = UIColor.FromRGB(228, 232, 237);
monthViewSettings.CurrentMonthBackgroundColor = UIColor.FromRGB(128, 0, 128);
monthViewSettings.PreviousMonthBackgroundColor =UIColor.FromRGB(152, 149, 240);
monthViewSettings.PreviousMonthTextColor = UIColor.FromRGB(0, 0, 0);
monthViewSettings.DateSelectionColor = UIColor.FromRGB(255, 255, 255);
calendar.MonthViewSettings = monthViewSettings;
	
{% endhighlight %}

N> The view modes can be switched by clicking the Header Text in MonthView or by selecting a month in YearView

### Month cell border color customization

You can customize the border color of calendar month cell using [MonthViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings.html).

* The border color of month cells can be customized using the [BorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~BorderColor.html) property, and the lines of month cells can be enabled using the [CellGridOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~CellGridOptions.html) property.

{% highlight c# %}

SFMonthViewSettings monthViewSettings = new SFMonthViewSettings();
monthViewSettings.BorderColor = UIColor.FromRGB(255, 0, 0);
calendar.MonthViewSettings = monthViewSettings;

{% endhighlight %}

### Today border color customization

You can customize the today border color of calendar month cell using [MonthViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings.html).

* The border color of month cells can be customized using the [BorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~BorderColor.html) property, and the lines of month cells can be enabled using the [CellGridOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~CellGridOptions.html) property.

{% highlight c# %}

SFMonthViewSettings monthViewSettings = new SFMonthViewSettings();
monthViewSettings.TodayBorderColor = UIColor.FromRGB(255, 0, 0);
calendar.MonthViewSettings = monthViewSettings;

{% endhighlight %}

## Week view

The number of weeks in the month view can be changed by setting the [NumberOfWeeksInView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~NumberOfWeeksInView.html) property in SfCalendar. By default, `NumberOfWeeksInView` starts from current week, and this can be modified using the [MoveToDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~MoveToDate.html) property of calendar. It also supports all existing features such as [FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~FirstDayOfWeek.html), [MinDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~MinDate.html), [MaxDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~MaxDate.html), and [SelectionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~SelectionMode.html).

N>
* Week number ranges from 1 to 6. If lesser or greater than these range is considered, `NumberOfWeeksInView` will be displayed as 6.
* Inline view considers  `NumberOfWeeksInView` as only 6. For other count, only agenda view will be displayed in calendar.
* Dynamically changing `NumberOfWeeksInView` shows the first row of month view dates. It can be handled using the `MoveToDate` property of calendar
* [ShowLeadingAndTrailingDays](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~ShowLeadingAndTrailingDays.html) is not applicable if the `NumberOfWeeksInView` is lesser than 6.

{% tabs %}

{% highlight c# %}

SFCalendar sfCalendar = new SFCalendar();
sfCalendar.NumberOfWeeksInView = 3;
View.AddSubView(sfCalendar);

{% endhighlight %}

{% endtabs %}

## Year view

This displays entire dates/month of a particular year, by default current year will be displayed on loading. The years can be changed by swiping back and forth. The months can be navigated quickly by selecting on the particular month in year view.

{% highlight c# %}

	calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeYear;
	
{% endhighlight %}

![Year View in Xamarin.iOS Calendar](images/xamarin.ios-calendar-year_view.png)                                        


## Year view customization

* The month header color can be modified using [MonthHeaderTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfcalendar/Syncfusion.SfCalendar.iOS~Syncfusion.SfCalendar.iOS.SFYearViewSettings~MonthHeaderTextColor.html) property.
* The year header and date text color can be changed using `YearHeaderTextColor` and [DateTextColor](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfcalendar/Syncfusion.SfCalendar.iOS~Syncfusion.SfCalendar.iOS.SFYearCell~DatetextColor.html) properties respectively.
* The gravity of the month name can be modified using `HeaderLabelAlignment` property, to position it to left, right or center. 
* The complete layout’s background color can be modified using [YearLayoutBackground](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfcalendar/Syncfusion.SfCalendar.iOS~Syncfusion.SfCalendar.iOS.SFYearViewSettings~YearLayoutBackground.html) property.

{% highlight c# %}

SFYearViewSettings yearViewSettings = new SFYearViewSettings();
yearViewSettings.YearHeaderTextColor = UIColor.FromRGB(27, 121, 214);
yearViewSettings.YearLayoutBackground = UIColor.FromRGB(255, 228, 181);
yearViewSettings.MonthHeaderBackground = UIColor.FromRGB(139, 69, 19);
yearViewSettings.DateTextColor = UIColor.FromRGB(230, 230, 250);
yearViewSettings.HeaderLabelAlignment = NSTextAlignment.NSTextAlignmentCenter;
calendar.YearViewSettings = yearViewSettings;

{% endhighlight %}


