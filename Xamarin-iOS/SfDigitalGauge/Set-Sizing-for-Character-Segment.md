---
layout: post
title: CharacterHeight in DigitalGauge for Xamarin.iOS platform
description: Learn how set the height of Digital Character in DigitalGauge
platform: Xamarin.iOS
control: DigitalGauge
documentation: ug
---

# Set Sizing for Character Segment

The Digital Characters size can be scaled using `CharacterHeight` and `CharacterWidth` properties in the SfDigitalGauge control.

### CharacterHeight

The value of the Digital Characters is scaled by altering the height of the digital characters. It is achieved by setting the `CharacterHeight` property in the Digital GaugeSets the height of character in SfDigitalGauge.

{% tabs %}

{% highlight c# %}

	digitalGauge.CharacterHeight = 36;

{% endhighlight %}

{% endtabs %}

![](images/CharacterHeight.png)

### CharacterWidth

The value of the Digital Characters is scaled by altering the width of the digital characters. It is achieved by setting the CharacterWidth property in SfDigitalGauge.

{% tabs %}

{% highlight c# %}

	digitalGauge.CharacterWidth = 18;

{% endhighlight %}

{% endtabs %}

![](images/CharacterWidth.png)