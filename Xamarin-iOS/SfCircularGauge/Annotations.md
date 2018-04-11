---

layout: post
title: Getting Started | SfCircularGauge | iOS | Syncfusion
description: Annotations
platform: xamarin.iOS
control: SfCircularGauge
documentation: ug

---

# Annotations

[`SFCircularGauge`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge.html) supports [`Annotations`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge~Annotations.html), which allows you to mark the specific area of interest in circular gauge. You can place custom views as annotations. The text and images also can be added by using [`Annotations`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFCircularGauge~Annotations.html) property.

##  Setting sub gauge for annotation

When the annotation allows you to place custom elements, a gauge can be initialized to the element, and this can be used to place the annotation in another gauge. The Following properties are used to customize the `Annotations`:

* [`Angle`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFGaugeAnnotation~Angle.html): Used to place the `View` at the given `Angle`. 
* [`Offset`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/sfgauge/Syncfusion.SfGauge.iOS~Syncfusion.SfGauge.iOS.SFGaugeAnnotation~Offset.html): Used to move the `View` from the center to edge of the circular gauge. The value should be range from 0 to 1.

The following code is used to create the `Annotations`.

{% highlight c# %}
 UILabel LabelAnnotation1 = new UILabel();
            LabelAnnotation1.Text = "4:55PM";
            LabelAnnotation1.Font = UIFont.FromName("Helvetica", 12f);
            LabelAnnotation1.TextColor = UIColor.Black;
            LabelAnnotation1.Frame = new CoreGraphics.CGRect(0, 0, 50, 50);

            UILabel LabelAnnotation2 = new UILabel();
            LabelAnnotation2.Text = "10s";
            LabelAnnotation2.Font = UIFont.FromName("Helvetica", 12f);
            LabelAnnotation2.TextColor = UIColor.Black;
            LabelAnnotation2.Frame = new CoreGraphics.CGRect(0, 0, 50, 50);

            UILabel LabelAnnotation3 = new UILabel();
            LabelAnnotation3.Text = "55M";
            LabelAnnotation3.Font = UIFont.FromName("Helvetica", 12f);
            LabelAnnotation3.TextColor = UIColor.Black;
            LabelAnnotation3.Frame = new CoreGraphics.CGRect(10, 10, 50, 50);

            SFCircularGauge Annotation1 = new SFCircularGauge();

            SFGaugeAnnotation annotations = new SFGaugeAnnotation();

            SFGaugeAnnotation gaugeAnnotation = new SFGaugeAnnotation();
            gaugeAnnotation.View = LabelAnnotation2;
            gaugeAnnotation.Angle = 300;
            gaugeAnnotation.Offset = (float)0.6;
            Annotation1.Annotations.Add(gaugeAnnotation);

            ObservableCollection<SFCircularScale> scales = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale = new SFCircularScale();
            scale.StartAngle = -180;
            scale.SweepAngle = 180;
            scale.ShowLabels = false;
            scale.StartValue = 0;
            scale.EndValue = 60;
            scale.Interval = 5;
            scale.RimColor = UIColor.FromRGB(237, 238, 239);
            scale.MajorTickSettings.Color = UIColor.Black;
            scale.MajorTickSettings.StartOffset = 1;
            scale.MajorTickSettings.EndOffset = .85f;
            scale.MajorTickSettings.Width = 2;
            scale.MinorTickSettings.Color = UIColor.Black;
            scale.MinorTickSettings.StartOffset = 1;
            scale.MinorTickSettings.EndOffset = .90f;
            scale.MinorTickSettings.Width = 0.5f;

            ObservableCollection<SFCircularRange> ranges = new ObservableCollection<SFCircularRange>();
            SFCircularRange range = new SFCircularRange();
            range.StartValue = 0;
            range.EndValue = 30;
            range.Color = UIColor.Gray;
            range.InnerStartOffset = 0.925f;
            range.OuterStartOffset = 1;
            range.InnerEndOffset = 0.925f;
            range.OuterEndOffset = 1;
            ranges.Add(range);
            scale.Ranges = ranges;

            ObservableCollection<SFCircularPointer> pointers = new ObservableCollection<SFCircularPointer>();
            SFNeedlePointer needlePointer = new SFNeedlePointer();
            needlePointer.PointerType = SFCiruclarGaugePointerType.SFCiruclarGaugePointerTypeTriangle;
            needlePointer.KnobRadius = 4;
            needlePointer.Width = 3;
            needlePointer.EnableAnimation = false;
            needlePointer.KnobColor = UIColor.Black;
            needlePointer.Color = UIColor.Black;
            pointers.Add(needlePointer);
            scale.Pointers = pointers;

            scales.Add(scale);
            Annotation1.Scales = scales;

            SFCircularGauge Annotation2 = new SFCircularGauge();

            SFGaugeAnnotation gaugeAnnotation1 = new SFGaugeAnnotation();
            gaugeAnnotation1.View = LabelAnnotation3;
            gaugeAnnotation1.Angle = 300;
            gaugeAnnotation1.Offset = (float)0.55;
            Annotation2.Annotations.Add(gaugeAnnotation1);

            ObservableCollection<SFCircularScale> scales1 = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale1 = new SFCircularScale();
            scale1.StartAngle = -180;
            scale1.SweepAngle = 180;
            scale1.StartValue = 0;
            scale1.EndValue = 60;
            scale1.Interval = 5;
            scale1.ShowLabels = false;
            scale1.RimColor = UIColor.FromRGB(237, 238, 239);
            scale1.MajorTickSettings.Color = UIColor.Black;
            scale1.MajorTickSettings.StartOffset = 1;
            scale1.MajorTickSettings.EndOffset = 0.85f;
            scale1.MajorTickSettings.Width = 2;
            scale1.MinorTickSettings.Color = UIColor.Black;
            scale1.MinorTickSettings.StartOffset = 1;
            scale1.MinorTickSettings.EndOffset = 0.90f;
            scale1.MinorTickSettings.Width = 0.5f;

            ObservableCollection<SFCircularRange> ranges1 = new ObservableCollection<SFCircularRange>();
            SFCircularRange range1 = new SFCircularRange();
            range1.StartValue = 0;
            range1.EndValue = 30;
            range1.Color = UIColor.Gray;
            range1.InnerStartOffset = 0.925f;
            range1.OuterStartOffset = 1;
            range1.InnerEndOffset = 0.925f;
            range1.OuterEndOffset = 1;
            ranges1.Add(range1);
            scale1.Ranges = ranges1;

            ObservableCollection<SFCircularPointer> pointers1 = new ObservableCollection<SFCircularPointer>();
            SFNeedlePointer needlePointer1 = new SFNeedlePointer();
            needlePointer1.PointerType = SFCiruclarGaugePointerType.SFCiruclarGaugePointerTypeTriangle;
            needlePointer1.KnobRadius = 4;
            needlePointer1.Width = 3;
            needlePointer1.EnableAnimation = false;
            needlePointer1.KnobColor = UIColor.Black;
            needlePointer1.Color = UIColor.Black;
            pointers1.Add(needlePointer1);
            scale1.Pointers = pointers1;

            scales1.Add(scale1);
            Annotation2.Scales = scales1;

            SFCircularGauge gauge = new SFCircularGauge();
            gauge.BackgroundColor = UIColor.White;
            Annotation1.Frame = new CGRect(0, 0, 70, 70);
            Annotation2.Frame = new CGRect(0, 0, 70, 70);
            SFGaugeAnnotation gaugeAnnotation2 = new SFGaugeAnnotation();
            gaugeAnnotation2.View = Annotation1;
            gaugeAnnotation2.Angle = 90;
            gaugeAnnotation2.Offset = (float)0.5;
            gauge.Annotations.Add(gaugeAnnotation2);

            SFGaugeAnnotation gaugeAnnotation3 = new SFGaugeAnnotation();
            gaugeAnnotation3.View = LabelAnnotation1;
            gaugeAnnotation3.Angle = 00;
            gaugeAnnotation3.Offset = (float)0.5;
            gauge.Annotations.Add(gaugeAnnotation3);

            SFGaugeAnnotation gaugeAnnotation4 = new SFGaugeAnnotation();
            gaugeAnnotation4.View = Annotation2;
            gaugeAnnotation4.Angle = 180;
            gaugeAnnotation4.Offset = (float)0.5;
            gauge.Annotations.Add(gaugeAnnotation4);

            ObservableCollection<SFCircularScale> scales2 = new ObservableCollection<SFCircularScale>();
            SFCircularScale scale2 = new SFCircularScale();
            scale2.StartValue = 0;
            scale2.EndValue = 12;
            scale2.Interval = 1;
            scale2.MinorTicksPerInterval = 4;
            scale2.RimColor = UIColor.FromRGB(237, 238, 239);
            scale2.LabelColor = UIColor.Gray;
            scale2.LabelOffset = 0.8f;
            scale2.ScaleEndOffSet = .925f;
            scale2.StartAngle = -180;
            scale2.SweepAngle = 180;
            scale2.LabelFont = UIFont.FromName("Helvetica", 14f);
            scale2.ShowFirstLabel = false;
            scale2.MinorTickSettings.Color = UIColor.Black;
            scale2.MinorTickSettings.StartOffset = 1;
            scale2.MinorTickSettings.EndOffset = 0.95f;
            scale2.MinorTickSettings.Width = 1;
            scale2.MajorTickSettings.Color = UIColor.Black;
            scale2.MajorTickSettings.StartOffset = 1;
            scale2.MajorTickSettings.EndOffset = 0.9f;
            scale2.MajorTickSettings.Width = 3;

            ObservableCollection<SFCircularRange> ranges2 = new ObservableCollection<SFCircularRange>();
            SFCircularRange range2 = new SFCircularRange();
            range2.StartValue = 0;
            range2.EndValue = 3;
            range2.Color = UIColor.Gray;
            range2.InnerStartOffset = 0.925f;
            range2.OuterStartOffset = 1;
            range2.InnerEndOffset = 0.925f;
            range2.OuterEndOffset = 1;
            ranges2.Add(range2);
            scale2.Ranges = ranges2;

            ObservableCollection<SFCircularPointer> pointers2 = new ObservableCollection<SFCircularPointer>();
            SFNeedlePointer needlePointer2 = new SFNeedlePointer();
            needlePointer2.EnableAnimation = false;
            needlePointer2.KnobRadius = 6;
            needlePointer2.LengthFactor = .75f;
            needlePointer2.KnobColor = UIColor.White;
            needlePointer2.Color = UIColor.Black;
            needlePointer2.Width = 3.5f;
            needlePointer2.KnobStrokeColor = UIColor.Black;
            needlePointer2.KnobStrokeWidth = 5;
            needlePointer2.TailLengthFactor = 0.20f;
            needlePointer2.TailColor = UIColor.Black;
            pointers2.Add(needlePointer2);

            SFNeedlePointer needlePointer3 = new SFNeedlePointer();
            needlePointer3.EnableAnimation = false;
            needlePointer3.KnobRadius = 6;
            needlePointer3.LengthFactor = .4f;
            needlePointer3.KnobColor = UIColor.White;
            needlePointer3.Color = UIColor.Black;
            needlePointer3.Width = 5;
            needlePointer.PointerType = SFCiruclarGaugePointerType.SFCiruclarGaugePointerTypeTriangle;
            pointers2.Add(needlePointer3);

            SFNeedlePointer needlePointer4 = new SFNeedlePointer();
            needlePointer4.EnableAnimation = false;
            needlePointer4.KnobRadius = 6;
            needlePointer4.LengthFactor = .65f;
            needlePointer4.KnobColor = UIColor.White;
            needlePointer4.Color = UIColor.Black;
            needlePointer4.Width = 5;
            needlePointer4.PointerType = SFCiruclarGaugePointerType.SFCiruclarGaugePointerTypeTriangle;
            pointers2.Add(needlePointer4);

            scale2.Pointers = pointers2;

            scales2.Add(scale2);
            gauge.Scales = scales2;
            this.View.AddSubview(gauge);
     
{% endhighlight %}

![](annotations_images/annotations.png)