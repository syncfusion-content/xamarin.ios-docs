---
layout: post
title: Accessing View modes in Syncfusion Calendar control for Xamarin.iOS
description: Calendar Xamarin.Android displays month, year, decade and century views which allows users to easily select and navigate between all built-in views
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Built-in Views

Xamarin.Android calendar control provides 4 different types of views such month, year, decade and century. It allows users to easily select and navigate between all built-in views. This can be achieved by using [ViewMode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_ViewMode) property of SfCalendar.

N> By default calendar control is assigned with month view. 

## Month view

This displays entire dates of a particular month, by default current month will be displayed on loading. The current date is provided with unique color different from the rest of the dates color in a month. The events availability will be denoted within the cell based on its duration.

The dates in month view can be selected by four ways such as single, multiple, range and multi range selections which can be achieved using [SelectionMode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_SelectionMode)

{% highlight c# %}

	calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeMonth;

{% endhighlight %}

![Month View in Xamarin.iOS Calendar](images/xamarin.ios-calendar-month_view.png)

## Trailing and leading days

The `SfCalendar` allows you hide the days of the next month and previous month in calendar to enhance the appearance. This can be achieved by enabling the [ShowLeadingAndTrailingDays]((https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_ShowLeadingAndTrailingDays)) property. The following code demonstrates how to hide the leading and trailing dates in calendar.

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

* Current day text color can be modified using [TodayTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFMonthViewSettings.html#Syncfusion_SfCalendar_iOS_SFMonthViewSettings_TodayTextColor). 
* The month view label settings class has the APIs to change date text size, day text size and format options. 
* The background color of the inline view can be modified using [InlineBackgroundColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFMonthViewSettings.html#Syncfusion_SfCalendar_iOS_SFMonthViewSettings_InlineBackgroundColor) property.

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

### Month view border color customization

You can customize the border color of calendar month cell using [MonthViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.MonthViewSettings.html).

* The border color of month cells can be customized using the [BorderColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFMonthViewSettings.html#Syncfusion_SfCalendar_iOS_SFMonthViewSettings_BorderColor) property, and the lines of month cells can be enabled using the [CellGridOptions](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFMonthViewSettings.html#Syncfusion_SfCalendar_iOS_SFMonthViewSettings_CellGridOptions) property.

{% highlight c# %}

SFMonthViewSettings monthViewSettings = new SFMonthViewSettings();
monthViewSettings.BorderColor = UIColor.FromRGB(255, 0, 0);
monthViewSettings.CellGridOptions = CellGridOptions.Both;
calendar.MonthViewSettings = monthViewSettings;

{% endhighlight %}

![Month view border color in Xamarin.iOS Calendar](images/xamarin.ios-BorderColor.png)

### Today border color customization

You can customize the today border color of calendar month cell using [MonthViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.MonthViewSettings.html).

* The border color of month cells can be customized using the [BorderColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFMonthViewSettings.html#Syncfusion_SfCalendar_iOS_SFMonthViewSettings_BorderColor) property, and the lines of month cells can be enabled using the [CellGridOptions](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFMonthViewSettings.html#Syncfusion_SfCalendar_iOS_SFMonthViewSettings_CellGridOptions) property.

{% highlight c# %}

SFMonthViewSettings monthViewSettings = new SFMonthViewSettings();
monthViewSettings.TodayBorderColor = UIColor.FromRGB(255, 0, 0);
calendar.MonthViewSettings = monthViewSettings;

{% endhighlight %}

![Month today border color in Xamarin.iOS Calendar](images/xamarin.ios-TodayBorderColor.png)

## Week view

The number of weeks in the month view can be changed by setting the [NumberOfWeeksInView](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_NumberOfWeeksInView) property in SfCalendar. By default, `NumberOfWeeksInView` starts from current week, and this can be modified using the [MoveToDate](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_MoveToDate_Foundation_NSDate_) property of calendar. It also supports all existing features such as [FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_FirstDayofWeek), [MinDate](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_MinDate), [MaxDate](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_MaxDate), and [SelectionMode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_SelectionMode).

N>
* Week number ranges from 1 to 6. If lesser or greater than these range is considered, `NumberOfWeeksInView` will be displayed as 6.
* Inline view considers  `NumberOfWeeksInView` as only 6. For other count, only agenda view will be displayed in calendar.
* Dynamically changing `NumberOfWeeksInView` shows the first row of month view dates. It can be handled using the `MoveToDate` property of calendar
* [ShowLeadingAndTrailingDays](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_ShowLeadingAndTrailingDays) is not applicable if the `NumberOfWeeksInView` is lesser than 6.

{% tabs %}

{% highlight c# %}

SFCalendar sfCalendar = new SFCalendar();
sfCalendar.NumberOfWeeksInView = 2;
View.AddSubView(sfCalendar);

{% endhighlight %}

{% endtabs %}

![Week view in Xamarin.iOS Calendar](images/xamarin.ios-NumberOfWeeksInView.png)

## Year view

This displays entire dates/month of a particular year, by default current year will be displayed on loading. The years can be changed by swiping back and forth. The months can be navigated quickly by selecting on the particular month in year view.

{% highlight c# %}

	calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeYear;
	
{% endhighlight %}

![Year View in Xamarin.iOS Calendar](images/xamarin.ios-calendar-year_view.png)      

## Year view mode

You can set the year view as either date or month using [YearViewMode](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFCalendar.html#Syncfusion_SfCalendar_iOS_SFCalendar_YearViewMode). By default, current year and months will be displayed. 

* If the `YearViewMode` is date,it will be displays all the months with dates in a particular year view.
* If the `YearViewMode` is month,it will be displays all the months in a particular year view.


{% tabs %}

{% highlight c# %}

SfCalendar calendar = new SfCalendar(this);
calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeYear;
calendar.YearViewMode = YearViewMode.Date;
this.Content = calendar;
 
{% endhighlight %}

{% endtabs %}
 
![Year view mode in Xamarin.iOS Calendar](images/xamarin.ios-YearViewMode.png)  

N>
* The `YearViewMode` property is only applicable for calendar in Android and iOS platforms.   

                             


## Year view customization

* The month header color can be modified using [MonthHeaderTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_MonthHeaderTextColor) property.
* The year header and date text color can be changed using `YearHeaderTextColor` and [DateTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearCell.html#Syncfusion_SfCalendar_iOS_SFYearCell_DateTextColor) properties respectively.
* The gravity of the month name can be modified using `HeaderLabelAlignment` property, to position it to left, right or center. 
* The complete layout’s background color can be modified using [YearLayoutBackground](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_YearLayoutBackground) property.

{% highlight c# %}

SFYearViewSettings yearViewSettings = new SFYearViewSettings();
yearViewSettings.YearHeaderTextColor = UIColor.FromRGB(27, 121, 214);
yearViewSettings.YearLayoutBackground = UIColor.FromRGB(255, 228, 181);
yearViewSettings.MonthHeaderBackground = UIColor.FromRGB(139, 69, 19);
yearViewSettings.DateTextColor = UIColor.FromRGB(230, 230, 250);
yearViewSettings.HeaderLabelAlignment = NSTextAlignment.NSTextAlignmentCenter;
calendar.YearViewSettings = yearViewSettings;

{% endhighlight %}


## Decade view

This view displays the period of 10 years. By default, current year range of 10 years will be displayed on loading. You can easily navigate between month/year view to decade view by tapping the calendar header. The year can be navigated quickly by selecting a particular year from decade view.

{% tabs %}

{% highlight c# %}

SFCalendar calendar = new SFCalendar();
calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeDecade;
View.AddSubView(calendar);
 
{% endhighlight %}	

{% endtabs %}

![Decade view mode in Xamarin.iOS Calendar](images/xamarin.ios-DecadeView.png)
 
## Decade view customization

* Year text color can be modified using [MonthHeaderTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_MonthHeaderTextColor).
* You can customize the decade view header text and background color by using the [YearHeaderTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_YearHeaderTextColor) and [HeaderBackground](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_YearHeaderBackground) property.
* You can customize the background of decade view by using [LayoutBackground](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_YearLayoutBackground) and [MonthLayoutBackground](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_MonthLayoutBackground).


{% tabs %}

{% highlight c# %}

SFYearViewSettings yearViewSettings = new SFYearViewSettings();
yearViewSettings.YearHeaderTextColor = UIColor.FromRGB(255, 0, 0);
yearViewSettings.YearLayoutBackground = UIColor.FromRGB(211,211,211);
yearViewSettings.MonthHeaderTextColor = UIColor.FromRGB(0,0,255);
yearViewSettings.YearHeaderBackground = UIColor.FromRGB(242,242,242);
yearViewSettings.MonthLayoutBackground = UIColor.FromRGB(242,242,242);
calendar.YearViewSettings = yearViewSettings;

{% endhighlight %}

{% endtabs %}

![Decade view customization in Xamarin.iOS Calendar](images/xamarin.ios-DecadeView-Custom.png)

## Century view

This view displays the period of 100 years. By default, current year range of 100 years will be displayed on loading. You can easily navigate between month/year/decade view to century view by tapping the calendar header. You can easily navigate to decade view by selecting decade years in century view.

{% tabs %}

{% highlight c# %}

SFCalendar calendar = new SFCalendar();
calendar.ViewMode=SFCalendarViewMode.SFCalendarViewModeCentury;
View.AddSubView(calendar);
 
{% endhighlight %}

{% endtabs %}

![Century view mode in Xamarin.iOS Calendar](images/xamarin.ios-CenturyView.png)
 
## Century view customization

* Year text color can be modified using [MonthHeaderTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_MonthHeaderTextColor).
* You can customize the century view header text and background color by using the [YearHeaderTextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_YearHeaderTextColor) and [HeaderBackground](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_YearHeaderBackground) property.
* You can customize the background of century view by using [LayoutBackground](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_YearLayoutBackground) and [MonthLayoutBackground](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfCalendar.iOS.SFYearViewSettings.html#Syncfusion_SfCalendar_iOS_SFYearViewSettings_MonthLayoutBackground).


{% tabs %}

{% highlight c# %}
	
SFYearViewSettings yearViewSettings = new SFYearViewSettings();
yearViewSettings.YearHeaderTextColor = UIColor.FromRGB(255, 0, 0);
yearViewSettings.YearLayoutBackground = UIColor.FromRGB(211,211,211);
yearViewSettings.MonthHeaderTextColor = UIColor.FromRGB(0,0,255);
yearViewSettings.YearHeaderBackground = UIColor.FromRGB(242,242,242);
yearViewSettings.MonthLayoutBackground = UIColor.FromRGB(242,242,242);
calendar.YearViewSettings = yearViewSettings;

{% endhighlight %}

{% endtabs %}

![Century view mode in Xamarin.iOS Calendar](images/xamarin.ios-CenturyView-Custom.png)





