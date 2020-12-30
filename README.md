# How to use icon font in Xamarin.Forms badge view (SfBadgeView)
This demo explains how to add a custom icon to the badge using the font icon in the Xamarin badge view control. Please refer KB links for more details,

[How to add a custom icon to the badge in Xamarin.Forms badge view (SfBadgeView)](https://www.syncfusion.com/kb/11338/?utm_medium=listing&utm_source=github-examples)

It has been achieved by setting desired custom view icon text as BadgeText  property of badge view and provide a corresponding icon font family to the FontFamily property of BadgeSetting as shown in the  following code snippet.

**Step 1:** Add the custom font file to your Xamarin.Forms shared project and mark it as an embedded resource.

![Embedded resource badge view custom font](OutputImage/EmbeddedCustomFont.PNG)

**Step 2:** Register the font file with the assembly, in a file such as AssemblyInfo.cs using the ExportFont attribute in your shared project as shown in the following code example. An optional alias can also be specified.

[C#]

**AssemblyInfo.cs**

```
using Xamarin.Forms;

[assembly: ExportFont("BadgeViewFont.ttf", Alias = "BadgeViewFont")]

```

**Step 3:** Initialize the SfBadgeView control by setting the BadgeText property as the desired custom view icon text and provide a corresponding icon font family to the FontFamily property of BadgeSetting as shown in the following code sample.

[XAML]

```
    <badge:SfBadgeView BadgeText="&#xe702;" HorizontalOptions="Center" VerticalOptions="Center">
        <Image Source="People.png"   VerticalOptions="Center"
                           HorizontalOptions="Center"
                           HeightRequest="70" WidthRequest="70"/>
        <badge:SfBadgeView.BadgeSettings>
            <badge:BadgeSetting Offset="-10,-10" Stroke="White" StrokeWidth="2" 
                                FontFamily="BadgeViewFont.ttf" BadgePosition="BottomRight">
            </badge:BadgeSetting>
        </badge:SfBadgeView.BadgeSettings>
    </badge:SfBadgeView>

```

![Output image of badge view custom font](OutputImage/BadgeCustomFont.jpg)

**See also:**

[How can I customize the badge view position?](https://help.syncfusion.com/xamarin/badge-view/position-customization)

[How can I customize the badge in Xamarin.Forms SfBadgeView?](https://help.syncfusion.com/xamarin/badge-view/badge-customization)

[How can I add badge icon in badge view?](https://help.syncfusion.com/xamarin/badge-view/predefined-symbols)

Also refer our [feature tour](https://www.syncfusion.com/xamarin-ui-controls/xamarin-badge-view) page to know more features available in our Badge View.

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.
