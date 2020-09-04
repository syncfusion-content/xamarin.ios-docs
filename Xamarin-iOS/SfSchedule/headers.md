---     
layout: post     
title: Header appearance and customization in Syncfusion SfSchedule control for Xamarin.iOS     
description: Learn how to customize header in SfSchedule control    
platform: xamarin.ios   
control: SfSchedule     
documentation: ug
---  

# Header

You can customize the header of the Schedule using [HeaderStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_HeaderStyle) and [HeaderHeight](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_HeaderHeight) property in `SFSchedule`.

## Header Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% tabs %}
{% highlight c# %}
schedule.HeaderHeight = 50;
{% endhighlight %}
{% endtabs %}

## Appearance

You can change the header format and style using `HeaderStyle` property in schedule.

You can change the background color,text style and text color using properties such as [BackgroundColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.HeaderStyle.html#Syncfusion_SfSchedule_iOS_HeaderStyle_BackgroundColor), [TextStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.HeaderStyle.html#Syncfusion_SfSchedule_iOS_HeaderStyle_TextStyle), [TextColor](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.HeaderStyle.html#Syncfusion_SfSchedule_iOS_HeaderStyle_TextColor) of Header using `HeaderStyle` property in schedule.

{% tabs %}
{% highlight c# %}
SFHeaderStyle headerStyle = new SFHeaderStyle();
headerStyle.BackgroundColor = UIColor.FromRGB(251, 211, 201);
headerStyle.TextStyle = UIFont.SystemFontOfSize(15,UIFontWeight.Bold);
headerStyle.TextColor=UIColor.White;
schedule.HeaderStyle = headerStyle;
{% endhighlight %}
{% endtabs %}

![](Header_images/HeaderStyle.png) 

### Customize Font Appearance

You can change the appearance of Font by setting the [TextStyle](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.HeaderStyle.html#Syncfusion_SfSchedule_iOS_HeaderStyle_TextStyle) property of  [HeaderStyle](https://help.syncfusion.com/xamarin-ios/sfschedule/headers) property in Schedule.

{% tabs %}
{% highlight c# %}
headerStyle.TextStyle = UIFont.FromName("Lobster-Regular",15);
{% endhighlight %}
{% endtabs %}

Refer [this](https://help.syncfusion.com/xamarin-ios/sfschedule/monthview#custom-font-setting-in-xamarinios) to configure the custom fonts in Xamarin.iOS.

![](Header_images/customfontheader.png)

## Loading Custom Headers

You can collapse the default header of schedule by setting `HeaderHeight` property of `SFSchedule` as 0. Instead you can use your own custom header for it. While navigating views in schedule, text labels available in the header will be changed based on it visible dates, so while using custom header , respective text value can be obtained from the `VisibleDatesChanged` event of `SFSchedule`.

{% tabs %}
{% highlight c# %}
//triggering visible dates changed event.
schedule.VisibleDatesChanged += Schedule_VisibleDatesChanged;

...

private void Schedule_VisibleDatesChanged(object sender, VisibleDatesChangedEventArgs e)
{
    //to get visible dates index value.
    int visibleDatesIndex = 0;
    var headerString = string.Empty;
    if (schedule.ScheduleView == SFScheduleView.SFScheduleViewMonth)
    {
        visibleDatesIndex = 8;//to get current month visible dates.
    }
    else
    {
        visibleDatesIndex = 0;
    }
    NSDate date = e.VisibleDates.GetItem<NSDate>((nuint)visibleDatesIndex);
    NSDateFormatter dateFormat = new NSDateFormatter();
    dateFormat.DateFormat = "MMMM YYYY";
    headerString = dateFormat.ToString(date);
}
{% endhighlight %}
{% endtabs %}

You can get the complete sample for customizing the Header of Schedule [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/HeaderSample_iOS-2097240596.zip)

## Header Date Format

You can customize the date format of SFSchedule Header by using [ScheduleDateHeaderFormat](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html#Syncfusion_SfSchedule_iOS_SFSchedule_ScheduleDateHeaderFormat) property of `SFSchedule`.

{% tabs %}
{% highlight c# %}
//Creating instance of Schedule
SFSchedule schedule = new SFSchedule();
//Customizing date format
schedule.ScheduleDateHeaderFormat = (NSString)"LLL yy";
{% endhighlight %}
{% endtabs %}

![](Header_images/HeaderDateFormat.png)

## Header Tapped Event

You can handle single tap action of Header by using [HeaderTapped](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.SFSchedule.html) event of `SFSchedule`. This event will be triggered when the Header is Tapped. This event contains [HeaderTappedEventArgs](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.HeaderTappedEventArgs.html) argument which holds [Date](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfSchedule.iOS.ViewHeaderTappedEventArgs.html#Syncfusion_SfSchedule_iOS_ViewHeaderTappedEventArgs_Date) details in it.

{% tabs %}
{% highlight c# %}
//Creating  new instance of Schedule
SFSchedule schedule = new SFSchedule();
schedule.HeaderTapped += Handle_HeaderTapped;

...

void Handle_HeaderTapped(object sender, HeaderTappedEventArgs e)
{
    var date = e.Date;
}
{% endhighlight %}
{% endtabs %}

