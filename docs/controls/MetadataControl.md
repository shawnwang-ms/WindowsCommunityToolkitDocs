---
title: MetadataControl
author: vgromfeld
description: The MetadataControl control displays a list of labels and hyper-links separated by a bullet.
keywords: windows 10, uwp, windows community toolkit, uwp community toolkit, uwp toolkit, metadata, metadatacontrol
dev_langs:
  - csharp
---

# MetadataControl

The [MetadataControl](/dotnet/api/microsoft.toolkit.uwp.ui.controls.metadatacontrol) control displays a
list of labels and hyper-links separated by a bullet.
It also generates an accessible string representing its content.

The bullet separator can be customized using the `Separator` property.
`AccessibleSeparator` is used as a replacement for `Separator` to generate the accessible string.

The control needs a list of [MediadataItem](https://github.com/windows-toolkit/WindowsCommunityToolkit/blob/main/Microsoft.Toolkit.Uwp.UI.Controls.Core/MetadataControl/MetadataItem.cs).
Each item will be displayed either as a text or as an hyper-link (if the `Command`property is set).

The default control template is using on a `TextBlock`. The style of this `TextBlock` can be customized using the `TextBlockStyle` property.

> [!div class="nextstepaction"]
> [Try it in the sample app](uwpct://CategoryName?sample=MetadataControl)

## Example

Add the control in the page:

```xaml
<controls:MetadataControl
    x:Name="metadataControl"
    Separator=" � "
    AccessibleSeparator=", "/>
```

Add items to control:

```cs
metadataControl.Items = new[]
{
    new MetadataItem { Label = "Hello" },
    new MetadataItem { Label = "World", Command = myCommand },
};
```

## MediadataItem

A `MediadataItem` contains the information about one entry which will be displayed in the `MetadataControl`

| Property | Type | Description |
| -- | -- | -- |
| Label | String | Gets or sets the label of the item |
| AccessibleLabel | String | Gets or sets the automation name that will be set on the item. If not set, `Label` will be used. |
| Command | ICommand | Gets or sets the command associated to the item. If null, the item will be displayed as a text field. If set, the item will be displayed as an hyperlink. |
| CommandParameter | Object | Gets or sets the parameter that will be provided to the `Command`|

## Sample Project

<!-- Link to the sample page in the Windows Community Toolkit Sample App -->
[MetadataControl sample page Source](https://github.com/windows-toolkit/WindowsCommunityToolkit/tree/main/Microsoft.Toolkit.Uwp.SampleApp/SamplePages/MetadataControl).

You can [see this in action](uwpct://CategoryName?sample=MetadataControl) in [Windows Community Toolkit Sample App](https://aka.ms/windowstoolkitapp).

## Source Code

[MetadataControl name source code](https://github.com/windows-toolkit/WindowsCommunityToolkit/blob/main/Microsoft.Toolkit.Uwp.UI.Controls.Core/MetadataControl)
