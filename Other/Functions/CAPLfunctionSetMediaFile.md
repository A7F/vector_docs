# SetMediaFile

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
SetMediaFile(panel, control, mediafile);
```

## Description

Replaces the media file of the Panel Designer control during runtime: [Media Player](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/Elements/PanelDesignerControlsMediaPlayer.md)

The panel is accessed by its individual panel name that is entered in the Panel Designer.

## Parameters

- **panel**: Panel name, restricted to 128 characters. `""` – references all loaded panels.
- **control**: Name of the control, restricted to 128 characters. `""` – references all controls on the panel.
- **mediafile**: Path and name of the media file.

## Return Values

—

## Example

Setting media file using **absolute** path.

```plaintext
on key 'x'
{
    SetMediaFile("Movie", "Media Player", "D:\\Example\\MediaPlayerProject\\Videos\\song.mpg");
}
```

Setting media file using **relative** path. The media file is in the **Videos** folder and this folder is parallel to the panel folder.

```plaintext
on key 'y'
{
    SetMediaFile("Movie", "Media Player", "..\\Videos\\song.mpg");
}
```

[SetPictureBoxImage](CAPLfunctionSetPictureBoxImage.md)
