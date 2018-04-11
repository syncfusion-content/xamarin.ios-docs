---
layout: post
title: Popup Animations | SfPopupLayout |Xamarin.iOS | Syncfusion
description: Animations in SfPopupLayout
platform: Xamarin.iOS
control: SfPopupLayout
documentation: ug
--- 

# Popup Animations

Built-in animations are available in SfPopupLayout, which is applied when the PopupView opens and closes in the screen.
SfPopupLayout has different animation modes as listed below.

<table>
<tr>
<th> Modes </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[Zoom](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  Zoom-out animation will be applied if the PopupView opens and zoom-in animation will be applied if the PopupView closes. This is the default AnimationMode</td>
</tr>
<tr>
<td> {{'[Fade](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  Fade-out animation will be applied if the PopupView opens and Fade-in animation will be applied if the PopupView closes</td>
</tr>
<tr>
<td> {{'[SlideOnLeft](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  PopupView will be animated from left-to-right, when it opens and it will be animated from right-to-left when the PopupView closes.</td>
</tr>
<tr>
<td> {{'[SlideOnTop](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  PopupView will be animated from top-to-bottom, when it opens and it will be animated from bottom-to-top when the PopupView closes.</td>
</tr>
<tr>
<td> {{'[None](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfpopuplayout/Syncfusion.SfPopupLayout.iOS~Syncfusion.iOS.PopupLayout.AnimationMode.html)'| markdownify }} </td>
<td>  Animation will not be applied.</td>
</tr>
</table>

N> Setting of AnimationMode is same for both TypeA and TypeB.

## Zoom 

Zoom-out animation will be applied if the PopupView opens and Zoom-in animation will be applied if the PopupView closes.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.AnimationMode = AnimationMode.Zoom;
    this.View.AddSubview(popupLayout);
    ....
}

{% endhighlight %}

If we run the above sample with `AnimationMode` as `Zoom`, the output will look like on iOS device as shown below.

![](GettingStarted_images/ZoomAnimation.gif)

## Fade 

Fade-out animation will be applied if the PopupView opens and Fade-in animation will be applied if the PopupView closes

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.AnimationMode = AnimationMode.Fade;
    this.View.AddSubview(popupLayout);
    ....
}

{% endhighlight %}

If we run the above sample with `AnimationMode` as `Fade`, the output will look like on iOS device as shown below.

![](GettingStarted_images/FadeAnimation.gif)

## SlideOnLeft 

PopupView will be animated from left-to-right, when it opens and it will be animated from right-to-left when the PopupView closes.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnLeft;
    this.View.AddSubview(popupLayout);  
    ....
}

{% endhighlight %}

If we run the above sample with `AnimationMode` as `SlideOnLeft`, the output will look like on iOS device as shown below.

![](GettingStarted_images/SlideOnLeftAnimation.gif)

## SlideOnTop 

PopupView will be animated from top-to-bottom, when it opens and it will be animated from bottom-to-top when the PopupView closes.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnTop;
    this.View.AddSubview(popupLayout);  
    ....
}

{% endhighlight %}

If we run the above sample with `AnimationMode` as `SlideOnTop`, the output will look like on iOS device as shown below.

![](GettingStarted_images/SlideOnTopAnimation.gif)

## None

Animation will not be applied.

{% highlight c# %}

//MyViewController.cs

public MyViewController()
{
    ....
    popupLayout = new SfPopupLayout();
    popupLayout.Content = GetContentOfPopup();
    popupLayout.PopupView.AnimationMode = AnimationMode.None;
    this.View.AddSubview(popupLayout);
    ....
}

{% endhighlight %}

If we run the above sample with `AnimationMode` as `None`, the output will look like on iOS device as shown below.

![](GettingStarted_images/AnimationMode_None.gif)
