---
layout: post
title: Custom Content
platform: xamarin.ios
control: ProgressBar
documentation: ug
---

# Custom Content

In the circular progress bar, you can add any view to the center using the [`Content`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfCircularProgressBar~Content.html) property. 

For example, you can include add, start, or pause button to control the progress; add an image that indicates the actual task in progress or add custom text that conveys how far the task is completed. 

The following code example shows how to add custom text content.

{% highlight c# %}

SfCircularProgressBar circular;
public async override void ViewDidLoad()
{
    base.ViewDidLoad();
    circular = new SfCircularProgressBar();
    circular.Progress = 75;
    circular.AnimationDuration = 1;
    await SetCustomContentProgress();            
    circular.Frame = new CoreGraphics.CGRect(0, 160, this.View.Frame.Width, this.View.Frame.Height);
    View.AddSubview(circular);            
}

private async System.Threading.Tasks.Task SetCustomContentProgress()
{
    double progress = 0;
    UIView CustContentLayout;
    while (progress < 75)
    {
        CustContentLayout = new UIView();
        this.circular.Progress = progress += 1;
        CustContentLayout.Frame = new CoreGraphics.CGRect(0, 0, 100, 80);
        string custContent = progress + "%";
        UILabel progressLabel = new UILabel()
        {
            Frame = new CoreGraphics.CGRect(CustContentLayout.Center.X - 20, 25, 40, 20),
            Text = custContent,
            Font = UIFont.FromName("HelveticaNeue", 11f),
            TextAlignment = UITextAlignment.Center,
            TextColor = UIColor.FromRGB(0, 124, 238)
        };
        CustContentLayout.AddSubview(progressLabel);
        UILabel textView = new UILabel()
        {
            Frame = new CoreGraphics.CGRect(CustContentLayout.Center.X - 20, CustContentLayout.Center.Y, 40, 20),
            Text = "used",
            TextAlignment = UITextAlignment.Center,
            Font = UIFont.FromName("HelveticaNeue", 10f),
            TextColor = UIColor.FromRGB(0, 124, 238),
        };
        CustContentLayout.Center = this.circular.Center;
        CustContentLayout.AddSubview(textView);
        this.circular.Content = CustContentLayout;
        await System.Threading.Tasks.Task.Delay(50);       
    }
}

{% endhighlight %}

![](overview_images/customcontent.png)

By default, the progress value will be displayed at the center. You can hide the label in the circular progress bar by setting the [`ShowProgressValue`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfProgressBar.iOS~Syncfusion.iOS.ProgressBar.SfCircularProgressBar~ShowProgressValue.html) property to false. 