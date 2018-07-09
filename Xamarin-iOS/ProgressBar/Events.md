---
layout: post
title: Events
platform: xamarin.ios
control: ProgressBar
documentation: ug
---

# Events

## ValueChanged

This event is triggered when the progress value is changed. This event contains the following event argument.

* [`Progress`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.ProgressValueEventArgs~Progress.html): Represents the progress value.

The following code example shows how to customize the color of a progress indicator based on progress using this event. 

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();
linearProgressBar.Progress = 100;
linearProgressBar.Frame = new CoreGraphics.CGRect(10,150,this.View.Frame.Width,this.View.Frame.Height);     
linearProgressBar.ValueChanged += this.ProgressBarBase_OnValueChanged;

private void ProgressBarBase_OnValueChanged(object sender, ProgressValueEventArgs e)
{   
    if (e.Progress < 50)
    {
        this.linearProgressBar.ProgressColor = Color.Red;
    }
    else if (e.Progress >= 50)
    {
        this.linearProgressBar.ProgressColor = Color.Green; 
    }
}

{% endhighlight %}

## ProgressCompleted

This event is triggered when the progress attains the [`Maximum`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.ProgressBarBase~Maximum.html) value. This event contains the following argument.

* [`Progress`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.ProgressValueEventArgs~Progress.html):  Represents the progress value.

The following code example shows how to customize the progress bar when progress reaches maximum using this event. 

{% highlight c# %}

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar();
circularProgressBar.Frame = new CoreGraphics.CGRect(10,150,this.View.Frame.Width,this.View.Frame.Height);
circularProgressBar.Minimum = 100;
circularProgressBar.Maximum = 500;
circularProgressBar.Progress = 500;
circularProgressBar.ProgressCompleted += this.ProgressBarBase_OnProgressCompleted;
circularProgressBar.Content = new UITextView();
(circularProgressBar.Content as UITextView).Text="Start";
(circularProgressBar.Content as UITextView).Frame= new CoreGraphics.CGRect(10,10,100,170);
SetContentView(circularProgressBar);

private void ProgressBarBase_OnProgressCompleted(object sender, ProgressValueEventArgs e)
{
    if (e.Progress.Equals(this.circularProgressBar.Maximum))
    {
       (this.circularProgressBar.Content as UITextView).Text="Completed";
    }
}

{% endhighlight %}
 