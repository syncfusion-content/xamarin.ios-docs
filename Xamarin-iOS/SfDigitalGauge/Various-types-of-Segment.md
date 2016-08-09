---
layout: post
title: CharacterType in DigitalGauge for Xamarin.iOS platform
description: Learn how to define character type in DigitalGauge
platform: Xamarin.iOS
control: DigitalGauge
documentation: ug
---

# Various types of Segment

The Digital Characters can be drawn in 4 different segments as follows.
 
1. Seven

2. Fourteen

3. Sixteen

4. EightCrossEightDotMatrix

N> SegmentSeven is the default CharacterType in the SfDigitalGauge.

## Seven Segment

{% tabs %}

{% highlight c# %}

	 digitalGauge.CharacterType=SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypeSegmentSeven;

{% endhighlight %}

{% endtabs %}

![](images/SegmentSeven.png)

## Fourteen Segment

{% tabs %}

{% highlight c# %}

	 digitalGauge.CharacterType=SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypesegmentFourteen;

{% endhighlight %}

{% endtabs %}

![](images/SegmentFourteen.png)

## Sixteen Segment

{% tabs %}

{% highlight c# %}

	 digitalGauge.CharacterType=SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypesegmentSixteen;

{% endhighlight %}

{% endtabs %}

![](images/SegmentSixteen.png)

## EightCrossEightDotMatrix Segment

{% tabs %}

{% highlight c# %}

	 digitalGauge.CharacterType=SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypeEightCrossEightDotMatrix;

{% endhighlight %}

{% endtabs %}

![](images/SegmentMatrix.png)

