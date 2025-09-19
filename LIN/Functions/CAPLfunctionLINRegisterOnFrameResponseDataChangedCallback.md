[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINRegisterOnFrameResponseDataChangedCallback.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linRegisterOnFrameResponseDataChangedCallback

# linRegisterOnFrameResponseDataChangedCallback

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword linRegisterOnFrameResponseDataChangedCallback (char[] callbackName);
```

## Description

Registers a callback function which is invoked whenever the response data of a LIN frame has been changed.

The invocation of the callback happens right before the data is passed to the LIN hardware or the LIN bus simulator. The data of the [linFrame](../Selectors/CAPLfunctionLINMessage.md) parameter can be modified by this function. This can be used to ensure consistency of the frame's data before it is sent.

**Note**: This function may only be called in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **callbackName**: The name of the callback function which should be registered. The callback must have the following signature: `void func (linFrame* frame)`

## Return Values

Returns **1** if the registration succeeded, otherwise **0**.

## Example

```plaintext
on preStart
{
  if (linRegisterOnFrameResponseDataChangedCallback("OnFrameResponseDataChanged"))
  {
    write("linRegisterOnFrameResponseDataChangedCallback succeeded.");
  }
  else
  {
    write("linRegisterOnFrameResponseDataChangedCallback failed.");
  }
}

void OnFrameResponseDataChanged(linFrame* frm)
{
  byte checksum;
  dword i;

  if (frm.id != 50 || frm.msgChannel != 1)
  {
    // filter for one specific frame
    return;
  }

  // pseudo checksum calculation over bytes 1 - dlc
  checksum = 0x55;
  for (i = 1; i < frm.dlc; i++)
  {
    checksum ^= frm.byte(i);
  }

  // set first byte of frame to calculated checksum
  frm.byte(0) = checksum;
}
```
