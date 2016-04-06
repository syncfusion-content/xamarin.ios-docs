---
layout: post
title: Barcode Customization | SfBarcode | iOS | Syncfusion
description: barcode customization
platform: ios
control: SfBarcode
documentation: ug
---

# Barcode Customization

## Bar Customization

The color of the Barcode can be customized by using the properties of `DarkBarColor` and `LightBarColor` in the SfBarcode. 

The darkBarColor represents the color of the dark bar (Black color by default) and the lightBarColor represents the color of the gap between two adjacent black bars (White color by default).


{% highlight c# %}

    //Changes the color of darker area of Barcode.
    barcode.DarkBarColor = UIColor.Blue;
    //Changes the color of lighter area of Barcode.
    barcode.LightBarColor = UIColor.Yellow;

{% endhighlight %}

![](Barcode-Customization_images/Barcode-Customization_img1.png)     
 
Barcode with bar color customization
{:.caption}


>**NOTE** The darkBarColor and lightBarColor customizations are applicable only for one dimensional Barcodes. In order, to recognize a Barcode symbol by a scanner, there must be an adequate contrast between the dark bars and the light spaces. All the Barcode scanners do not have support for colored Barcodes.

## Text Customization

The text representing the Barcode can be customized by using the following properties.

* The color of text can be altered by using the `TextColor` property.
* The horizontal alignment of text can be customized with the help of the `TextAlignment` property.
* The gap between Barcode and text can be adjusted by setting property of `TextGapHeight`.
* To change the location of text vertically, you can make use of the `TextLocation` property with options of top and bottom location.

{% highlight c# %}

    barcode.TextColor = UIColor.Blue;
    barcode.TextFont = UIFont.BoldSystemFontOfSize (30);
    barcode.TextGapHeight = 20;
    barcode.TextLocation = SFBarcodeTextLocation.SFBarcodeTextLocationBottom;
    barcode.TextAlignment =SFBarcodeTextAlignment.SFBarcodeTextAlignmentCenter;

{% endhighlight %}

![](Barcode-Customization_images/Barcode-Customization_img3.png)     

Barcode with text customization
{:.caption}
