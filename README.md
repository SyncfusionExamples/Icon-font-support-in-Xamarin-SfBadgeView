# How to use icon font in Xamarin.Forms badge view (SfBadgeView)
This demo explains how to use font icon in Xamarin badge view. Please refer KB links for more details,

[How to add a custom icon to the badge in Xamarin.Forms badge view (SfBadgeView)](https://www.syncfusion.com/kb/11338/?utm_medium=listing&utm_source=github-examples)

It has been achieved by setting desired icon text as BadgeText of badge view and provide a corresponding icon fontfamily to the FontFamily property pf BadgeSetting as per in below code snippet 

```

    <badge:SfBadgeView BadgeText="&#xe702;" HorizontalOptions="Center" VerticalOptions="Center">
        <Image Source="People.png"   VerticalOptions="Center"
                           HorizontalOptions="Center"
                           HeightRequest="70" WidthRequest="70"/>
        <badge:SfBadgeView.BadgeSettings>
            <badge:BadgeSetting Offset="-10,-10" Stroke="White" StrokeWidth="2" BadgePosition="BottomRight">
                <badge:BadgeSetting.FontFamily>
                    <OnPlatform x:TypeArguments="x:String">
                        <On Platform="Android" Value="BadgeViewFont.ttf#FONT Sf Badge view" />
                        <On Platform="UWP" Value="Assets/BadgeViewFont.ttf#FONT Sf Badge view" />
                        <On Platform="iOS" Value="BadgeViewFont.ttf" />
                    </OnPlatform>
                </badge:BadgeSetting.FontFamily>
            </badge:BadgeSetting>
        </badge:SfBadgeView.BadgeSettings>
    </badge:SfBadgeView>

```

The following steps describe how to add a custom font file in the platform-specific projects.

## Android
Add a custom font file in the Assets folder and set Build Action to AndroidAsset for the font file.

## iOS

**Step 1:** Add a custom font file in the Resources folder and set Build Action to BundleResource. Then, ensure that the copy to output directory is set to AlwaysCopy.

**Step 2:** Add a custom font file name in the info.plist file as demonstrated in the following code sample.

```

<plist version="1.0">
<dict>
    …
    <key>UIAppFonts</key>
    <array>
    <string>BadgeViewFont.ttf</string>
    </array>
</dict> 

```

## UWP
Add a custom font file in the Assets folder and set Build Action to Content.

See also:

[How can I customize the badge view position?](https://help.syncfusion.com/xamarin/badge-view/position-customization)

[How can I customize the badge in Xamarin.Forms SfBadgeView?](https://help.syncfusion.com/xamarin/badge-view/badge-customization)

[How can I add badge icon in badge view?](https://help.syncfusion.com/xamarin/badge-view/predefined-symbols)

Also refer our [feature tour](https://www.syncfusion.com/xamarin-ui-controls/xamarin-badge-view) page to know more features available in our Badge View.

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.
