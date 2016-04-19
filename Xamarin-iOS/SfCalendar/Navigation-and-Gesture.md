---
layout: post
title: Date Navigation and Gestures with Syncfusion Calendar control for Xamarin.iOS
description: Learn the complete navigating and gestures support
platform: Xamarin.iOS
control: Calendar
documentation: ug
---

# Navigation and Gesture

## Move to Date 

Visible dates can be moved to specific date using `moveToDate` property available in Calendar. It will move to any specific month if the `viewMode` is month view or move to year if it is a year view.

{% highlight c# %}

	Calendar moveToDate = Calendar.getInstance();   
    moveToDate.Set
        (
                2010,
                Calendar.AUGUST,
                25,
                0,
                0,
                0
        );
    calendar.MoveToDate=moveToDate;

{% endhighlight %}

N>  The specified date should lie between minDate and maxDate, if  the specified date is greater than maxDate then the view will be moved to maxDate and if the specified date is lesser than the minDate then the view will be moved to minDate.

## Toggle  navigation

This navigation, using touch gesture can be enabled and disabled using `navigationEnabled` property available in Calendar control. By default, `navigationEnabled` property is enabled.

N> By default, calendar views can be moved backwards and forwards using touch swipe gesture. 

{% highlight c# %}

    calendar.ViewMode=ViewMode.MonthView;
	calendar.NavigationEnable=false;

{% endhighlight %}

## Transition modes

Dates can be navigated by using swipe gesture. By default those navigation are performed along with Scroll animation. Other than the default scroll animation, there are other options available like card, reveal, float animations. It can be changed by using  transitionMode property of Calendar control.

{% highlight c# %}

    calendar.TransitionMode=TransitionMode.Card;
	
{% endhighlight %}

