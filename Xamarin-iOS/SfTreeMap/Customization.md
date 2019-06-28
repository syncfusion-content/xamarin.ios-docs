---
layout: post
title: Customization in Syncfusion TreeMap control for Xamarin.iOS
description: This section explains the steps required to customize the data in Syncfusion TreeMap control for Xamarin.Forms
platform: Xamarin.iOS
control: TreeMap
documentation: ug
---

# Customization

The TreeMap control supports color customization to determine the exact combination of colors for the tree nodes displayed and provides tooltip support to display additional information of TreeMap data.

## Color

You can customize the colors of leaf nodes using the [`ColorMapping`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFColorMapping.html) support.

The [`ColorMapping`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFColorMapping.html) is categorized into the following three different types:

* UniColorMapping
* RangeColorMapping
* DesaturationColorMapping

### UniColorMapping

You can color all the leaf nodes with the same color by setting value to the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFUniColorMapping~Color.html) property of [`UniColorMapping`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFUniColorMapping.html).

{% tabs %}  

{% highlight C# %} 

  SFUniColorMapping uniColorMapping = new SFUniColorMapping();
            uniColorMapping.Color = UIColor.Red;
            treeMap.LeafItemColorMapping = uniColorMapping;

{% endhighlight %}

{% endtabs %}  

![UniColorMapping](TreeMapLevels_images/Unicolor.png)

### RangeColorMapping

You can group the leaf nodes based on the range of color values of data. You can set a unique color for every range. To achieve this, specify the [`To`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRange~To.html) and [`From`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRange~From.html) values as range bound, and specify the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFRange~Color.html) value to fill the leaf nodes of particular range using the `RangeColorMapping` property of TreeMap. You must specify value to ColorValuePath since the ranges `From` and `To` depend on the under bound value of [`ColorValuePath`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFTreeMap~ColorValuePath.html).

{% tabs %}  

{% highlight c# %}

            SFRangeColorMapping colorMapping = new SFRangeColorMapping();

            SFRange range1 = new SFRange();
            range1.LegendLabel = (NSString)"1 % Growth";
            range1.From = 0;
            range1.To = 1;
            range1.Color = UIColor.FromRGB(119, 216, 216);

            SFRange range2 = new SFRange();
            range2.LegendLabel = (NSString)"2 % Growth";
            range2.From = 0;
            range2.To = 2;
            range2.Color = UIColor.FromRGB(174, 217, 96);

            SFRange range3 = new SFRange();
            range3.LegendLabel = (NSString)"3 % Growth";
            range3.From = 0;
            range3.To = 3;
            range3.Color = UIColor.FromRGB(255, 175, 81);

            SFRange range4 = new SFRange();
            range4.LegendLabel = (NSString)"4 % Growth";
            range4.From = 0;
            range4.To = 4;
            range4.Color = UIColor.FromRGB(243, 210, 64);

            colorMapping.Ranges.Add(range1);
            colorMapping.Ranges.Add(range2);
            colorMapping.Ranges.Add(range3);
            colorMapping.Ranges.Add(range4);

            treeMap.LeafItemColorMapping = colorMapping;

{% endhighlight %}

{% endtabs %}  

![RangeColorMapping](TreeMapLevels_images/Flatlevel.png)

### DesaturationColorMapping

You can differentiate all the leaf nodes using the [`DesaturationColorMapping`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFDesaturationColorMapping.html) property of TreeMap. Differentiation can be achieved even though the same color is applied for all the leaf nodes by varying the opacity of the leaf nodes based on the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFDesaturationColorMapping~Color.html) value specified. You can also change the opacity range by setting the [`From`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFDesaturationColorMapping~From.html) and [`To`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFDesaturationColorMapping~To.html) properties of `DesaturationColorMapping`.

{% tabs %}  

{% highlight c# %}

            SFDesaturationColorMapping desaturationColorMapping = new SFDesaturationColorMapping();
            desaturationColorMapping.From = 1;
            desaturationColorMapping.To = 0.2f;
            desaturationColorMapping.Color = UIColor.FromRGB(65, 184, 196);
            treeMap.LeafItemColorMapping = desaturationColorMapping;

{% endhighlight %}

{% endtabs %}  

![DesaturationColorMapping](TreeMapLevels_images/Desaturation.png)

### Palette color mapping

Leaf nodes were colored based on the colors mentioned in the [`Colors`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFPaletteColorMapping~Colors.html) collection of the [`PaletteColorMapping`](https://help.syncfusion.com/cr/cref_files/xamarin-ios/Syncfusion.SfTreeMap.iOS~Syncfusion.SfTreeMap.iOS.SFPaletteColorMapping.html). 

{% tabs %}  

{% highlight c# %}

            SFPaletteColorMapping paletteColorMapping = new SFPaletteColorMapping();
            paletteColorMapping.Colors.Add(UIColor.FromRGB(189, 142, 194));
            paletteColorMapping.Colors.Add(UIColor.FromRGB(255, 211, 78));
            paletteColorMapping.Colors.Add(UIColor.FromRGB(85, 185, 73));
            paletteColorMapping.Colors.Add(UIColor.FromRGB(0, 178, 218));
            paletteColorMapping.Colors.Add(UIColor.FromRGB(116, 74, 148));
            paletteColorMapping.Colors.Add(UIColor.FromRGB(161, 166, 22));
            paletteColorMapping.Colors.Add(UIColor.FromRGB(7, 83, 161));
            treeMap.LeafItemColorMapping = paletteColorMapping;

{% endhighlight %}

{% endtabs %} 

![DesaturationColorMapping](TreeMapLevels_images/Palette.png)

## Tooltip

You can enable the tooltip support for TreeMap by setting the [`ShowTooltip`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.SfTreeMap~ShowTooltip.html) property to true. By default, it takes the property of bound object that is referenced in [`GroupPath`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.TreeMapFlatLevel~GroupPath.html) and displays its content when the corresponding node is tapped.

{% tabs %}  

{% highlight c# %}

           treeMap.ShowTooltip = true;

{% endhighlight %}

{% endtabs %} 


![Tooltip](TreeMapLevels_images/Tooltip.png)

### Tooltip customization

Tooltip can be customized by inheriting the [`TooltipSetting`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.SfTreeMap~TooltipSettings.html) and can define our own customized view.

{% tabs %} 

{% highlight C# %} 

treeMap.ShowTooltip = true;
            CustomTooltipSetting tooltip = new CustomTooltipSetting(this);
            treeMap.TooltipSettings = tooltip;

{% endhighlight %}

{% endtabs %}  

Refer the below code snippet for defining the custom tooltip.

{% tabs %} 

{% highlight C# %} 

public class CustomTooltipSetting : TooltipSetting
    {
        Context context;
        public CustomTooltipSetting(Context con)
        {
            context = con;
        }

        public override View GetView(object data, Context context)
        {
            LinearLayout layout = new LinearLayout(context);
            LinearLayout.LayoutParams linearlayoutParams = new LinearLayout.LayoutParams(LinearLayout.LayoutParams.WrapContent,
                    LinearLayout.LayoutParams.WrapContent);
            layout.Orientation = Orientation.Vertical;
            layout.LayoutParameters = linearlayoutParams;
            layout.SetGravity(GravityFlags.CenterHorizontal);

            TextView topLabel = new TextView(context);
            topLabel.Text = ((JSONObject)data).GetString("Country");
            topLabel.TextSize = 12;
            topLabel.SetTextColor(Color.ParseColor("#FFFFFF"));
            topLabel.Gravity = GravityFlags.CenterHorizontal;

            TextView SplitLine = new TextView(context);
            SplitLine.Text = "-------";
            SplitLine.SetTextColor(Color.Gray);
            SplitLine.Gravity = GravityFlags.CenterHorizontal;


            TextView bottoLabel = new TextView(context);
            var growth = ((JSONObject)data).GetDouble("Growth");
            bottoLabel.Text = ((int)growth).ToString() + "%";
            bottoLabel.TextSize = 12;
            bottoLabel.SetTextColor(Color.ParseColor("#FFFFFF"));
            bottoLabel.Gravity = GravityFlags.CenterHorizontal;

            layout.AddView(topLabel);
            layout.AddView(SplitLine);
            layout.AddView(bottoLabel);

            return layout;
        }
    }

{% endhighlight %}

{% endtabs %}  

![CustomTooltip](TreeMapLevels_images/CustomTooltip.png)

## Selection

The TreeMap control provides selection support, which allows you to select the tree map items. The selection can be enabled by setting the [`HighlightOnSelection`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.SfTreeMap~HighlightOnSelection.html) property to true in TreeMap. You can specify the highlight color and border width using the [`HighlightStrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.SfTreeMap~HighlightStrokeColor.html) and [`HighlightStrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.SfTreeMap~HighlightStrokeColor.html) properties, respectively.

{% tabs %}  

{% highlight C# %} 

 treeMap.HighlightOnSelection = true;
            treeMap.HighlightStrokeColor = Color.Red;
            treeMap.HighlightStrokeWidth = 8;

{% endhighlight %}

{% endtabs %}  

![Selection](Getting-Started_images/Selection.png)

## Item customization

Treemap control provides support to customize the items which allows any type of custom view to replace the item.
To achieve this derive a class from [`TreeMapAdapter`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfTreeMap.Android~Com.Syncfusion.Treemap.TreeMapAdapter.html) and override the GetTreeMapItemView method and return the needed custom view as in the below snippet.

{% tabs %} 

{% highlight C# %} 

 public class CustomAdapter: TreeMapAdapter
    {
        Context context;
        public CustomAdapter(Context con)
        {
            context = con;
        }
        public override View GetTreeMapItemView(TreeMapItem item)
        {
            LinearLayout layout = new LinearLayout(context);
            layout.SetBackgroundColor(Color.Red);
            LinearLayout.LayoutParams linearlayoutParams = new LinearLayout.LayoutParams(LinearLayout.LayoutParams.WrapContent,
                    LinearLayout.LayoutParams.WrapContent);
            layout.Orientation = Orientation.Vertical;
            layout.LayoutParameters = linearlayoutParams;
            layout.SetGravity(GravityFlags.CenterHorizontal);

            TextView topLabel = new TextView(context);
            topLabel.Text = item.Label;
            topLabel.TextSize = 12;
            topLabel.SetTextColor(Color.ParseColor("#FFFFFF"));
            topLabel.Gravity = GravityFlags.Left;            

            ImageView imageView = new ImageView(context);           
            if (item.Label == "Archery")
                imageView.SetImageResource(Resource.Drawable.Archery);
            else if(item.Label == "Boxing")
                imageView.SetImageResource(Resource.Drawable.Boxing);
            else if (item.Label == "Cycling")
                imageView.SetImageResource(Resource.Drawable.Cycling);
            else if (item.Label == "Diving")
                imageView.SetImageResource(Resource.Drawable.Diving);
            else if (item.Label == "Gymnastics")
                imageView.SetImageResource(Resource.Drawable.Gymnastics);
            else if (item.Label == "Shooting")
                imageView.SetImageResource(Resource.Drawable.Shooting);

            else if (item.Label == "Soccer")
                imageView.SetImageResource(Resource.Drawable.Soccer);
            else if (item.Label == "Swimming")
                imageView.SetImageResource(Resource.Drawable.Swimming);
            else if (item.Label == "Track and Field")
                imageView.SetImageResource(Resource.Drawable.TrackAndField);
            else if (item.Label == "Wrestling")
                imageView.SetImageResource(Resource.Drawable.Wrestling);

            layout.AddView(topLabel);
            layout.AddView(imageView);
           
            return layout;

        }
    }

{% endhighlight %}

{% endtabs %}  

Set the custom view to the tree map item as per the below code snippet.

{% tabs %} 

{% highlight C# %} 

SfTreeMap treeMap = new SfTreeMap(this);
            treeMap.ColorValuePath = "TotalMedals";
            treeMap.WeightValuePath = "TotalMedals";
            treeMap.LayoutType = Com.Syncfusion.Treemap.Enums.LayoutType.Squarified;          

            LeafItemSetting leafItemSetting = new LeafItemSetting();
            leafItemSetting.ShowLabels = false;
            leafItemSetting.Gap = 2;
            leafItemSetting.LabelPath = "GameName";
            treeMap.LeafItemSettings = leafItemSetting;

            treeMap.DataSource = GetDataSource();
            CustomAdapter customAdapter = new CustomAdapter(this);
            treeMap.Adapter = customAdapter;
            SetContentView(treeMap);

{% endhighlight %}

{% endtabs %}  

Refer the below code snippet for the under bound data of tree map item customization.

{% tabs %} 

{% highlight C# %} 

JSONArray GetDataSource()
        {
            JSONArray array = new JSONArray();
            array.Put(getJsonObject("US", "Swimming", 16, 9, 6, 31, "Swimming.png"));
            array.Put(getJsonObject("US", "Track and Field", 9, 13, 7, 29, "TrackAndField.png"));
            array.Put(getJsonObject("US", "Gymnastics", 3, 1, 2, 6, "Gymnastics.png"));
            array.Put(getJsonObject("US", "Boxing", 1, 0, 1, 2, "Boxing.png"));

            array.Put(getJsonObject("US", "Cycling", 1, 2, 1, 4, "Cycling.png"));
            array.Put(getJsonObject("US", "Shooting", 3, 0, 1, 4, "Shooting.png"));
            array.Put(getJsonObject("US", "Wrestling", 2, 0, 2, 4, "Wrestling.png"));
            array.Put(getJsonObject("US", "Diving", 1, 1, 2, 4, "Diving.png"));
            return array;
        }

        JSONObject getJsonObject(string country, string gameName, double goldMedals, double silverMedals,
            double bronzeMedals, double totalMedals, string imageName)
        {
            JSONObject obj = new JSONObject();

            obj.Put("Country", country);
            obj.Put("GameName", gameName);
            obj.Put("GoldMedals", goldMedals);
            obj.Put("SilverMedals", silverMedals);
            obj.Put("BronzeMedals", bronzeMedals);
            obj.Put("TotalMedals", totalMedals);
            obj.Put("ImageName", imageName);
            return obj;

        }

{% endhighlight %}

{% endtabs %}  

![ItemTemplate](TreeMapLevels_images/ItemCustomization.png)
