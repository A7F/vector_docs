[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetMediaStream.md)

**CAPL Functions** » **General** » **Function Overview** » **SetMediaStream**

# SetMediaStream

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
SetMediaStream(panel, control, busType, channel, streamIndex, streamId[]);
```

## Description

Replaces the media stream at the specified index of the **Panel Designer** during runtime: [Media Stream Control](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/Elements/PanelDesignerControlsMediaStream.md).

The panel is accessed by its individual panel name that is entered in the **Panel Designer**.

## Parameters

- **panel**: Panel name, restricted to 128 characters. "" – references all loaded panels.
- **control**: Name of the control, restricted to 128 characters. "" – references all controls on the panel.
- **busType**: Bus system of the source media stream (e.g. eCAN, eFlexRay, eEthernet, ...). Currently only bus system eEthernet is supported.
- **channel**: Channel number of the source media stream.
- **streamIndex**: Target stream index of the Media Stream Control.
- **streamId**: Stream ID of the source media stream.

## Return Values

—

## Example

Setting media stream from Ethernet channel 1.

```plaintext
on key 'x'
{
  byte streamId[8] = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x00, 0x01 };
  SetMediaStream("AVTP Video H.264", "Media Stream Control", eEthernet, 1, 0, streamId);
}
```

[SetPictureBoxImage](CAPLfunctionSetPictureBoxImage.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
