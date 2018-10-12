---
layout: post
title: Technical Indicators | SFChart | Xamarin.iOS | Syncfusion
description: How to enable and customize the technical indicator behavior in Essential Xamarin.Forms Chart
platform: xamarin.ios
control: SFChart
documentation: ug
---

# Technical Indicators

The different types of technical indicators available in chart are follows:

* [`AverageTrueIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFATRIndicator.html)
* [`SimpleMovingAverageIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSMAIndicator.html)
* [`RSITechnicalIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFRSIIndicator.html)
* [`AccumulationDistributionIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFADIndicator.html)
* [`MomentumIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFMomentumIndicator.html) 
* [`StochasticIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFStochasticIndicator.html)
* [`ExponentialMovingAverageIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFEMAIndicator.html)
* [`TriangularMovingAverageIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTMAIndicator.html)
* [`BollingerBandIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFBBIndicator.html)
* [`MACDIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFMACDIndicator.html)

## Adding technical indicators to chart

The following section illustrates how to add technical indicators to chart.

**Initializing indicator**

Create an instance for any technical indicator, and add it to the [`TechnicalIndicators`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.ChartBase~TechnicalIndicators.html) collection.

Here, for an instance, the [`AccumulationDistributionIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFADIndicator.html) is added.


{% highlight c# %}

SfChart chart = new SfChart();
...
AccumulationDistributionIndicator indicator= new AccumulationDistributionIndicator();

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}


**Binding data**

Set the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~ItemsSource.html) and binding paths ([`Open`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~Open.html), [`High`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~High.html), [`Low`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~Low.html), [`Close`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~Close.html) and [`XBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~XBindingPath.html) to fetch the values from model.


{% highlight c# %}

SFChart chart = new SFChart()
{
      ...                
      TechnicalIndicators =
      {
          new SFADIndicator()
          {
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close"
          }
    }
};

{% endhighlight %}


**Binding the items source of chart series**

By setting [`Name`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~Name.html) property of chart series to the [`SeriesName`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~SeriesName.html) property of [`FinancialTechnicalIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator.html) you can bind the items source of chart series to technical indicators, including x and y axis.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    Series =
      {
          new SFOHLCSeries()
          {
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
              Name = "OHLC"
          }
    },

    TechnicalIndicators =
      {
          new SFADIndicator()
          {
              SeriesName = "OHLC"              
          }
    }
};

{% endhighlight %}


Technical indicators have the below properties as common; 

 * [`Period`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFBBIndicator~Period.html) - used to indicates the moving average period.
 * [`SignalLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~SignalLineColor.html) - used to defines the color for the respective indicator line.

**Adding axis**

The [`XAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~XAxis.html) and [`YAxis`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~YAxis.html) properties of technical indicators are used to set the x and y-axes.

You can define the axis using the following code example.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFADIndicator()
          {
              SeriesName = "OHLC",
              XAxis = new NumericalAxis()
          }
      }
};

{% endhighlight %}


**Animation**

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChart.html) provides animation support for technical indicators. Technical indicators will be animated whenever the ItemsSource changes. Animation can be enabled by setting the [`EnableAnimation`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~EnableAnimation.html) property to true. You can also control the duration of the animation using the [`AnimationDuration`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSeries~AnimationDuration.html) property.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFADIndicator()
          {
              SeriesName = "OHLC",
              EnableAnimation = true,
              AnimationDuration = 0.8      
          }
      }
};


{% endhighlight %}


## Average true range indicator 

ATR indicator is a technical analysis volatility indicator. This indicator does not provide an indication of price trend; simply the degree of price volatility. The average true range is an N-day smoothed moving average (SMMA) of the true range values.

You can define the [`AverageTrueIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFATRIndicator.html) using the following code example.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFATRIndicator()
          {
              Period = 14,
              SignalLineColor = UIColor.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}


The following screenshot illustrates an ATR indicator.

![Average true range indicator type in Xamarin.iOS Chart](technicalindicators_images/averagetrue.png)

## Simple moving average indicator

A SMA indicator is a simple, arithmetic moving average that is calculated by adding the closing price for number of time periods and dividing the total value by the number of time periods.

The following code example demonstrates the usage of [`SimpleMovingAverageIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSMAIndicator.html).


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFSMAIndicator()
          {
              Period = 14,
              SignalLineColor = UIColor.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}


The following screenshot illustrates an SMA indicator.

![Simple moving average indicator type in Xamarin.iOS Chart](technicalindicators_images/simplemovingaverage.png)

## Relative strength index indicator

The RSI indicator has additional two lines other than signal line; they indicate the overbought and oversold region.

The [`UpperLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFRSIIndicator~UpperLineColor.html) property is used to define the color for the line that indicates overbought region, and the [`LowerLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFRSIIndicator~LowerLineColor.html) property is used to define the color for the line that indicates oversold region.

To define the [`RSITechnicalIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFRSIIndicator.html), use the following code example.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFRSIIndicator()
          {
              Period = 14,
              SignalLineColor = UIColor.Blue,
              UpperLineColor = UIColor.Teal,
              LowerLineColor = UIColor.Red,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}


The following screenshot illustrates an RSI technical indicator.

![Relative strength index indicator type in Xamarin.iOS Chart](technicalindicators_images/rsi.png)


## Accumulation distribution indicator

Accumulation distribution indicator is a volume-based indicator designed to measure the accumulative flow of money into and out of a security. It requires [`Volume`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFADIndicator~Volume.html) property additionally with the data source to calculate the signal line. 

The following code example helps you to add [`AccumulationDistributionIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFADIndicator.html).


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFADIndicator()
          {
              SignalLineColor = UIColor.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
              Volume = "Volume"
          }
      }
};

{% endhighlight %}


The following screenshot illustrates an accumulation distribution indicator.

![Accumulation distribution indicator type in Xamarin.iOS Chart](technicalindicators_images/accumulation.png)


## Momentum indicator

This indicator is having two lines, momentum line and center line. The [`SignalLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~SignalLineColor.html) property and [`UpperLineColor`] property is used to define the color for the momentum and center line respectively.
You can define [`MomentumIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFMomentumIndicator.html) using the following code example.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFMomentumIndicator()
          {
              Period = 14,
              SignalLineColor = UIColor.Blue,
              UpperLineColor = UIColor.Red,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};


{% endhighlight %}

![Momentum indicator type in Xamarin.iOS Chart](technicalindicators_images/momentum.png)


## Stochastic indicator

This indicator is used to measure the range and momentum of price movements. It contains [`KPeriod`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFStochasticIndicator~KPeriod.html) and [`DPeriod`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFStochasticIndicator~DPeriod.html) property defining the ‘K’ percentage and ‘D’ percentage respectively. No signal line in this indicator.
The [`UpperLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFStochasticIndicator~UpperLineColor.html), [`LowerLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFStochasticIndicator~LowerLineColor.html) and [`PeriodLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFStochasticIndicator~PeriodLineColor.html) property are used to define the color for the Stochastic indicator lines.
You can define [`StochasticIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFStochasticIndicator.html) using the following code example.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFStochasticIndicator()
          {
              Period = 14,
              SignalLineColor = UIColor.Yellow,
              UpperLineColor = UIColor.Red,
              LowerLineColor = UIColor.Teal,
              PeriodLineColor = UIColor.DarkBlue,
              KPeriod = 8,
              DPeriod = 5,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};
{% endhighlight %}

![Stochastic indicator type in Xamarin.iOS Chart](technicalindicators_images/stochastic.png)

## Exponential moving average indicator

The [`ExponentialMovingAverageIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFEMAIndicator.html) is similar to [`SimpleMovingAverageIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFSMAIndicator.html) and this can be defined using the following code examples.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFEMAIndicator()
          {
              Period = 14,
              SignalLineColor = UIColor.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}

![Exponential moving average indicator type in Xamarin.iOS Chart](technicalindicators_images/exponentialmovingaverage.png)


## Triangular moving average indicator

A triangular moving average is simply a double-smoothed simple moving average of data calculated over a period of time where the middle portion of the data has more weight. 
The [`TriangularMovingAverageIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTMAIndicator.html) can be defined as in the following code example.


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFTMAIndicator()
          {
              Period = 14,
              SignalLineColor = UIColor.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};


{% endhighlight %}

![Triangular moving average indicator type in Xamarin.iOS Chart](technicalindicators_images/triangularmovingaverage.png)

## Bollinger band indicator

This indicator also having [`UpperLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFBBIndicator~UpperLineColor.html), [`LowerLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFBBIndicator~LowerLineColor.html)  and [`SignalLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFTechnicalIndicator~SignalLineColor.html) property for defining the brushes for the indicator lines.

Also, we can specify standard deviation values for BollingerBand indicator using [`StandardDeviation`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFBBIndicator~StandardDeviation.html) property.
You can define the [`BollingerBandIndicator`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFBBIndicator.html).


{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFBBIndicator()
          {
              Period = 14,
              SignalLineColor = UIColor.Blue,
              UpperLineColor = UIColor.Red,
              LowerLineColor = UIColor.Teal,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};


{% endhighlight %}

![Bollinger band indicator type in Xamarin.iOS Chart](technicalindicators_images/bollingerband.png)

## MACD indicator

This is mostly using indicator having [`ShortPeriod`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFMACDIndicator~ShortPeriod.html) and [`LongPeriod`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFMACDIndicator~LongPeriod.html) for defining the motion of the indicator.
Also you can draw [`Line`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFChartMACDType.html), Histogram MACD or Both using the [`MACDType`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFMACDIndicator~MACDType.html) property, which defines the type of MACD to be drawn.

The [`MACDLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFMACDIndicator~MACDLineColor.html) property is used to define the color for the MACD line  and the  [`HistogramColor`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SFChart.iOS~Syncfusion.SfChart.iOS.SFMACDIndicator~HistogramColor.html) property is used to define the color for the MACD histogram.
You can specify the MACD indicator using the following code example.

{% highlight c# %}

SFChart chart = new SFChart()
{
    ...        
    TechnicalIndicators =
      {
          new SFMACDIndicator()
          {
              MACDType = MACDType.Both,
              ShortPeriod = 2,
              LongPeriod = 10,
              Trigger = 14,
              SignalLineColor = UIColor.Blue,
              HistogramColor = UIColor.LightSkyBlue,
              MACDLineColor = UIColor.Orange,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}

![MACD indicator type in Xamarin.iOS Chart](technicalindicators_images/macd.png)
