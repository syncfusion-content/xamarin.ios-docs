---
layout: post
title: RTL | TreeView for Xamarin.iOS | Syncfusion
description: Describes how to enable right-to-left localization treeview.
platform: Xamarin.iOS
control: SfTreeView
documentation: ug
---

# Right-to-left localization.

 TreeView supports right-to-left localization when the device language is set to right to left languages such as Arabic, Hebrew. 

## Application setup to support RTL

To notify your application that it’s allowed to recognize a right-to-left layout. Add the right-to-left language in the `CFBundleLocalizations` section of your `Info.plist`, and make sure you’re targeting version should `iOS 9+`.

{% tabs %}
{% highlight xml %}

<key>CFBundleDevelopmentRegion</key> 
<string>en</string> 
<key>CFBundleLocalizations</key> 
<array> 
    <string>en</string> 
    <string>ar</string> 
</array>
{% endhighlight %}
{% endtabs %}

## Device setup to support RTL

Right-to-left localization can then be tested by changing the device/emulator to use any of right-to-left language in `Settings > General > Language & Region`.

N> Right-to-left localization requires the use of `iOS 9` or higher.