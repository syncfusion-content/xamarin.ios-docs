---
layout: post
title: CharacterType in DigitalGauge for Xamarin.iOS platform
description: Learn how to define character type in DigitalGauge
platform: Xamarin.iOS
control: DigitalGauge
documentation: ug
---

# CharacterType

The Digital Characters can be drawn in 4 different segments as follows.
 
1. Seven

2. Fourteen

3. Sixteen

4. EightCrossEightDotMatrix

N> SegmentSeven is the default CharacterType in the SfDigitalGauge.

## Seven Segment

{% highlight c# %}

	 digitalGauge.CharacterType=SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypeSegmentSeven;

{% endhighlight %}

![](images/SegmentSeven.png)

## Fourteen Segment

{% highlight c# %}

	 digitalGauge.CharacterType=SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypesegmentFourteen;

{% endhighlight %}

![](images/SegmentFourteen.png)

## Sixteen Segment

{% highlight c# %}

	 digitalGauge.CharacterType=SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypesegmentSixteen;

{% endhighlight %}

![](images/SegmentSixteen.png)

## EightCrossEightDotMatrix Segment

{% highlight c# %}

	 digitalGauge.CharacterType=SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypeEightCrossEightDotMatrix;

{% endhighlight %}

![](images/SegmentMatrix.png)

