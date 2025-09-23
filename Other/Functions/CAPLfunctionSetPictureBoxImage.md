# SetPictureBoxImage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
setPictureBoxImage(panel, control, imagefile);
```

## Description

Replaces the image of the Panel Designer control during runtime: [Picture Box](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/Elements/PanelDesignerControlsPictureBox.md).

The panel is accessed by its individual panel name that is entered in the Panel Designer.

## Parameters

- **panel**: Panel name, restricted to 128 characters. "" – references all loaded panels.
- **control**: Name of the control, restricted to 128 characters. "" – references all controls on the panel.
- **imagefile**: Path and name of the image file.

## Return Values

—

## Example

Setting image file using **absolute** path.

```plaintext
on key 'x'
{
    SetPictureBoxImage("Movie", "Picture Box", "D:\\Example\\PictureBoxProject\\Images\\Picture.bmp");
}
```

Setting image file using **relative** path. The image is in the **Images** folder and this folder is parallel to the panel folder.

```plaintext
on key 'y'
{
    SetPictureBoxImage("Movie", "Picture Box", "..\\Images\\Picture.bmp");
}
```

[SetMediaFile](CAPLfunctionSetMediaFile.md)
