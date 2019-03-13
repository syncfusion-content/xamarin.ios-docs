---
layout: post
title: Adding Multiple trackball in Syncfusion SFChart
description: Adding Multiple trackball in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

## Adding Multiple trackball in SFChart

[`SFChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html) allows the user to activate multiple trackballs in chart area by adding two instances of trackball behavior to chart and by using the [`Show`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartTrackballBehavior~Show.html) method. Each trackball will be interacting separately by using [`HitTest`] method which returns the nearest trackball that contains the touch point and the touch override methods of trackball behavior, but these Multiple trackballs having effect only when the [`ActivationMode`] is set as [`None`]. 

The following code sample demonstrates this:

{% highlight c# %}

SFChartTrackballBehavior trackballBehavior1 = new SFChartTrackballBehavior();
trackballBehavior1.ActivationMode = SFChartTrackballActivationMode.None;
chart.Behaviors.Add(trackballBehavior1);

SFChartTrackballBehavior trackballBehavior2 = new SFChartTrackballBehavior();
trackballBehavior2.ActivationMode = SFChartTrackballActivationMode.None;
chart.Behaviors.Add(trackballBehavior2);

{% endhighlight %}

{% highlight c# %}

trackballBehavior1.Show(point);
trackballBehavior2.Show(point);

{% endhighlight %}

{% highlight c# %}

public class TrackballBehaviorExt : SFChartTrackballBehavior
{
    bool isActivate = false;

    public override void TouchesBegan(NSSet touches, UIEvent uiEvent)
    {
        UITouch touch = touches?.AnyObject as UITouch;
        if (touch != null)
        {
            CGPoint location = touch.LocationInView(Chart);
            if (HitTest((float)location.X, (float)location.Y))
            {
                isActivate = true;
                base.TouchesBegan(touches, uiEvent);
            }
        }
    }

    public override void TouchesMoved(NSSet touches, UIEvent uiEvent)
    {
        if (isActivate)
        {
            UITouch touch = touches?.AnyObject as UITouch;
            if (touch != null)
            {
                CGPoint location = touch.LocationInView(Chart);
                if (HitTest((float)location.X, (float)location.Y))
                {
                    Show(location);
                    base.TouchesMoved(touches, uiEvent);
                }
            }
        }
    }

    public override void TouchesEnded(NSSet touches, UIEvent uiEvent)
    {
        isActivate = false;
    }
}

{% endhighlight %}