---
layout: post
title: Symbology Settings | SfBarcode | iOS | Syncfusion
description: symbology settings
platform: xamarin.iOS
control: SfBarcode
documentation: ug
---

# Symbology Settings


Each and every Barcode symbology can be personalized with optional settings that may affect the appearance of specific Barcode. 


## One Dimensional Barcode settings


One dimensional Barcodes can be customized by using the following properties and they are commonly used for all categories of supported one dimensional Barcodes.

* By setting the `BarHeight` property, the height of linear bars can be changed.
* By setting the `NarrowBarWidth` property, the width ratio of wide and narrow bars can be customized.

One dimensional Barcodes can also have error detection settings.

* By enabling the `EncodeStartStopSymbols` property, start and stop symbols are added to signal a Barcode reader that a Barcode has been scanned. 
* The `EnableCheckDigit` property enables or disables the redundancy check by using a check digit that is the decimal equivalent of a binary parity bit.
* With the help of `ShowCheckDigit` property, the check digit can be shown or hidden.

The following code example shows how to change the settings of `Code39` linear Barcode.

{% highlight c# %}

    SFCode39Settings settings = new SFCode39Settings();
    settings.BarHeight = 100;
    settings.NarrowBarWidth = 2;
    settings.EncodeStartStopSymbols = true;
    settings.EnableCheckDigit = false;
    settings.ShowCheckDigit = false;

{% endhighlight %}

Similarly, you can specify the settings of other linear Barcodes corresponding to specified symbology.

## Two Dimensional Barcode Settings

Two dimensional Barcodes are customized by using `XDimension` property that modifies its block size and it is commonly used for all kinds of supported two dimensional Barcodes.

### Data Matrix Settings

The Data Matrix symbology can be customized with the help of the following settings.

{% highlight c# %}

    SFDataMatrixSettings settings = new SFDataMatrixSettings();
    settings.XDimension = 8;
    settings.Size = SFBarcodeDataMatrixSize.SFBarcodeDataMatrixSizeAuto; 
    settings.Encoding = SFBarcodeDataMatrixEncoding.SFBarcodeDataMatrixEncodingAuto;

{% endhighlight %}

* The `Encoding` property is used to specify the encoding technique from enumeration of `SfDataMatrixEncoding` that contains encoding techniques such as ASCII, ASCIINumeric, Auto and Base256.
* The `Size` property allows the user to specify the size of the Barcode from a set of predefined sizes available in the `SFDataMatrixSize` enumeration.

<table>
<tr>
<td>
Data Matrix Size</td><td>
Description</td></tr>
<tr>
<td>
Auto</td><td>
Size is chosen based on the input data</td></tr>
<tr>
<td>
Size10x10</td><td>
Square matrix with 10 rows and 10 columns.</td></tr>
<tr>
<td>
Size12x12</td><td>
Square matrix with 12 rows and 12 columns.</td></tr>
<tr>
<td>
Size14x14</td><td>
Square matrix with 14 rows and 14 columns.</td></tr>
<tr>
<td>
Size16x16</td><td>
Square matrix with 16 rows and 16 columns.</td></tr>
<tr>
<td>
Size18x18</td><td>
Square matrix with 18 rows and 18 columns.</td></tr>
<tr>
<td>
Size20x20</td><td>
Square matrix with 20 rows and 20 columns.</td></tr>
<tr>
<td>
Size22x22</td><td>
Square matrix with 22 rows and 22 columns.</td></tr>
<tr>
<td>
Size24x24</td><td>
Square matrix with 24 rows and 24 columns.</td></tr>
<tr>
<td>
Size26x26</td><td>
Square matrix with 26 rows and 26 columns.</td></tr>
<tr>
<td>
Size32x32</td><td>
Square matrix with 32 rows and 32 columns.</td></tr>
<tr>
<td>
Size36x36</td><td>
Square matrix with 36 rows and 36 columns.</td></tr>
<tr>
<td>
Size40x40</td><td>
Square matrix with 40 rows and 40 columns.</td></tr>
<tr>
<td>
Size44x44</td><td>
Square matrix with 44 rows and 44 columns.</td></tr>
<tr>
<td>
Size48x48</td><td>
Square matrix with 48 rows and 48 columns.</td></tr>
<tr>
<td>
Size52x52</td><td>
Square matrix with 52 rows and 52 columns.</td></tr>
<tr>
<td>
Size64x64</td><td>
Square matrix with 64 rows and 64 columns.</td></tr>
<tr>
<td>
Size72x72</td><td>
Square matrix with 72 rows and 72 columns.</td></tr>
<tr>
<td>
Size80x80</td><td>
Square matrix with 80 rows and 80 columns.</td></tr>
<tr>
<td>
Size88x88</td><td>
Square matrix with 88 rows and 88 columns.</td></tr>
<tr>
<td>
Size96x96</td><td>
Square matrix with 96 rows and 96 columns.</td></tr>
<tr>
<td>
Size104x104</td><td>
Square matrix with 104 rows and 104 columns.</td></tr>
<tr>
<td>
Size120x120</td><td>
Square matrix with 120 rows and 120 columns.</td></tr>
<tr>
<td>
Size132x132</td><td>
Square matrix with 132 rows and 132 columns.</td></tr>
<tr>
<td>
Size144x144</td><td>
Square matrix with 144 rows and 144 columns.</td></tr>
<tr>
<td>
Size8x18</td><td>
Rectangular matrix with 8 rows and 18 columns.</td></tr>
<tr>
<td>
Size8x32</td><td>
Rectangular matrix with 8 rows and 32 columns.</td></tr>
<tr>
<td>
Size12x26</td><td>
Rectangular matrix with 12 rows and 26 columns.</td></tr>
<tr>
<td>
Size12x36</td><td>
Rectangular matrix with 12 rows and 36 columns.</td></tr>
<tr>
<td>
Size16x36</td><td>
Rectangular matrix with 16 rows and 36 columns.</td></tr>
<tr>
<td>
Size16x48</td><td>
Rectangular matrix with 16 rows and 48 columns.</td></tr>
</table>


### QR Code Settings

The Data Matrix symbology can be customized by using the following settings.

{% highlight c# %}

    SFQRBarcodeSettings settings = new SFQRBarcodeSettings();
	settings.XDimension = 5;
    settings.InputMode= SFBarcodeQRInputMode.SFBarcodeQRInputModeBinary;
    settings.ErrorCorrectionLevel = SFBarcodeQRErrorCorrectionLevel.SFBarcodeQRErrorCorrectionLevelLow;
    settings.Version = SFBarcodeQRVersion.SFBarcodeQRVersionAuto;
    
{% endhighlight %}

* The `Version` property allows you to set various types of version for QR code from SFQRVersion enumeration.  By default, its value is set as Auto.

SFQRVersion enumeration details

<table>
<tr>
<td>
SFQRVersion</td><td>
Description</td></tr>
<tr>
<td>
Version01</td><td>
Measures 21 x 21 modules</td></tr>
<tr>
<td>
Version02</td><td>
Measures 25 x 25 modules</td></tr>
<tr>
<td>
Version03</td><td>
Measures 29 x 29 modules</td></tr>
<tr>
<td>
Version04</td><td>
Measures 33 x 33 modules</td></tr>
<tr>
<td>
Version05</td><td>
Measures 37 x 37 modules</td></tr>
<tr>
<td>
Version06</td><td>
Measures 41 x 41 modules</td></tr>
<tr>
<td>
Version07</td><td>
Measures 45 x 45 modules</td></tr>
<tr>
<td>
Version08</td><td>
Measures 49 x 49 modules</td></tr>
<tr>
<td>
Version09</td><td>
Measures 53 x 53 modules</td></tr>
<tr>
<td>
Version10</td><td>
Measures 57 x 57 modules</td></tr>
<tr>
<td>
Version11</td><td>
Measures 61 x 61 modules</td></tr>
<tr>
<td>
Version12</td><td>
Measures 65 x 65 modules</td></tr>
<tr>
<td>
Version13</td><td>
Measures 69 x 69 modules</td></tr>
<tr>
<td>
Version14</td><td>
Measures 73 x 73 modules</td></tr>
<tr>
<td>
Version15</td><td>
Measures 77 x 77 modules</td></tr>
<tr>
<td>
Version16</td><td>
Measures 81 x 81 modules</td></tr>
<tr>
<td>
Version17</td><td>
Measures 85 x 85 modules</td></tr>
<tr>
<td>
Version18</td><td>
Measures 89 x 89 modules</td></tr>
<tr>
<td>
Version19</td><td>
Measures 93 x 93 modules</td></tr>
<tr>
<td>
Version20</td><td>
Measures 97 x 97 modules</td></tr>
<tr>
<td>
Version21</td><td>
Measures 101 x 101 modules</td></tr>
<tr>
<td>
Version22</td><td>
Measures 105 x 105 modules</td></tr>
<tr>
<td>
Version23</td><td>
Measures 109 x 109 modules</td></tr>
<tr>
<td>
Version24</td><td>
Measures 113 x 113 modules</td></tr>
<tr>
<td>
Version25</td><td>
Measures 117 x 117 modules</td></tr>
<tr>
<td>
Version26</td><td>
Measures 121 x 121 modules</td></tr>
<tr>
<td>
Version27</td><td>
Measures 125 x 125 modules</td></tr>
<tr>
<td>
Version28</td><td>
Measures 129 x 129 modules</td></tr>
<tr>
<td>
Version29</td><td>
Measures 133 x 133 modules</td></tr>
<tr>
<td>
Version30</td><td>
Measures 137 x 137 modules</td></tr>
<tr>
<td>
Version31</td><td>
Measures 141 x 141 modules</td></tr>
<tr>
<td>
Version32</td><td>
Measures 145 x 145 modules</td></tr>
<tr>
<td>
Version33</td><td>
Measures 149 x 149 modules</td></tr>
<tr>
<td>
Version34</td><td>
Measures 153 x 153 modules</td></tr>
<tr>
<td>
Version35</td><td>
Measures 157 x 157 modules</td></tr>
<tr>
<td>
Version36</td><td>
Measures 161 x 161 modules</td></tr>
<tr>
<td>
Version37</td><td>
Measures 165 x 165 modules</td></tr>
<tr>
<td>
Version38</td><td>
Measures 169 x 169 modules</td></tr>
<tr>
<td>
Version39</td><td>
Measures 173 x 173 modules</td></tr>
<tr>
<td>
Version40</td><td>
Measures 177 x 177 modules</td></tr>
</table>


* The `ErrorCorrectionLevel` property employs error correction to generate a series of error correction code words that are added to the data code word sequence in order to enable the symbol to withstand damage without loss of data. By default, its value is set as Low.

<table>
<tr>
<td>
Error Correction Level</td><td>
Recovery Capacity % (approx.)</td></tr>
<tr>
<td>
Low</td><td>
7</td></tr>
<tr>
<td>
Medium</td><td>
15</td></tr>
<tr>
<td>
Quartile</td><td>
25</td></tr>
<tr>
<td>
High</td><td>
30</td></tr>
</table>


* The `InputMode` property allows you to select specific set of input characters. You may select the most suitable input mode. By default, its value is set as Binary Mode.


<table>
<tr>
<td colspan = "2">
Input Mode</td><td>
Possible characters</td></tr>
<tr>
<td>
NumericMode</td><td colspan = "2">
0,1,2,3,4,5,6,7,8,9</td></tr>
<tr>
<td>
AlphanumericMode</td><td colspan = "2">
0 to 9, A to Z, space, $, %, *, +, -,., /, :</td></tr>
<tr>
<td>
BinaryMode</td><td colspan = "2">
Shift JIS characters</td></tr>
</table>