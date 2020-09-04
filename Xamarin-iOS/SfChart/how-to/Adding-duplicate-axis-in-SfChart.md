---
layout: post
title: Adding duplicate axis in Syncfusion SFChart
description: Adding duplicate axis in SFChart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Adding duplicate axis in SFChart

Duplicate axis can be added in the [`SFChart`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFChart.html) using the chart [`Axes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Axes) collection property. The axis added in the [`Axes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Axes) collection will be aligned to the horizontal position by default. The axis position can be changed by using the [`IsVertical`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_IsVertical) bool property of [`SfAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html). When the [`IsVertical`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html#Syncfusion_SfChart_iOS_SFAxis_IsVertical) property is set true, the axis will be placed vertically and vice versa.

N> 
- The [`SFAxis`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.SFAxis.html) added in the [`Axes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Axes) collection will not be removed until removing it from the [`Axes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Axes) collection. 
- The [`Axes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Axes) collection does not support the clear method.
- Same axis cannot be added more than once in [`Axes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Axes); only distinct axis will be added to the [`Axes`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfChart.iOS.ChartBase.html#Syncfusion_SfChart_iOS_ChartBase_Axes) collection.
