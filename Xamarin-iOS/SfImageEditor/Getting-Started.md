---
layout: post
title: Getting Started for Essential Xamarin.iOS ImageEditor
description: This section explains you the steps required to load an image to the image editor. Image editor has a built in toolbar which has options to edit the image with shapes, path, text, crop and flip.
platform: xamarin.ios
control: SfImageEditor
documentation: ug
---
# Getting Started

This section explains you the steps required to load an image to the image editor. Image editor has a built in toolbar which has options to edit the image with shapes, path, text, crop and flip.

## Reference Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, 

{Syncfusion Installed location}\Essential Studio\15.2.0.40\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the iOS project,

ios-unified\Syncfusion.SfImageEditor.iOS.dll

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Initializing the image editor

The following steps explain on how to create a image editor  and configure its elements,

* Create an instance of SfImageEditor.

{% highlight C# %}

       SfImageEditor imageEditor = new SfImageEditor(); 
       imageEditor.Frame = this.View.Frame; 
       View.AddSubview(imageEditor); 


{% endhighlight %}

* Load an image to the Image Editor

You can load the image to the SfImageEditor by set image property in SfImageEditor.

{% highlight C# %}

    SfImageEditor imageEditor = new SfImageEditor(); 
    imageEditor.Image = UIImage.FromBundle("image.png");

{% endhighlight %}


* Loading the image to the SfImageEditor, you can start to edit the image by using the built-in Toolbars.

Following is the final output screenshot,

![SfImageEditor](ImageEditor_images/gettingstarted.png)

