---
layout : post
title : Undo, Redo in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to perform undo and redo in ImageEditor for Xamarin.iOS
platform : xamarin.ios
control : ImageEditor
documentation : ug
---

# Undo-Redo support

One of the important features of the image editor control is to perform `Undo` and `Redo` operations for adding shapes, text and drawing paths.

## Undo

The `Undo` method is used to revert the changes done previously over an image.

Undo can be performed for the following operations:

* Add/delete shapes or text.
* Change positions.
* Color/fill changes.
* Path drawings.

{% tabs %}

{% highlight C# %}

editor.Undo();

{% endhighlight %}

{% endtabs %}

## Redo

The `Redo` method is used to redo the changes that are reverted by undo operation.

{% tabs %}

{% highlight C# %}

editor.Redo();

{% endhighlight %}

{% endtabs %}

N> Undo and redo cannot be applied for cropping and transformations.

![SfImageEditor](ImageEditor_images/undoredo.gif)