# xlSetLED

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » xlSetLED

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
dword xlSetLED(dword ledBitMask, dword ledMode);
```

## Description

Sets the LEDs specified by **ledBitMask** to the operation mode specified by **ledMode**. A successful call of [xlAcquireLED](CAPLfunctionxlAcquireLED.md) is necessary before the operation mode of an LED can be set with this function.

This function is only supported on **VN8900** devices.

Note that for every successful call of **xlAcquireLED** on a specific LED, you have to call [xlReleaseLED](CAPLfunctionxlReleaseLED.md) to release this LED again.

## Parameters

- **ledBitMask**: The LEDs you want to set. You can bitwise combine the values to specify multiple LEDs. The following LEDs are available for **VN8900** devices:
  - Module (M): `0x001`
  - CAN Channel 1: `0x008`
  - CAN Channel 2: `0x010`
  - CAN Channel 3: `0x020`
  - CAN Channel 4: `0x040`
  - FlexRay Channel 1 A: `0x080`
  - FlexRay Channel 1 B: `0x100`
  - Keypad S1: `0x200`
  - Keypad S2: `0x400`

- **ledMode**: The operation mode which shall be valid for the specified LEDs. The operation modes are mutually exclusive and only one LED can be in one operation mode. The following operation modes are available:
  - No Change: `0x00000000`
  - LED Off: `0x00000001`
  - LED On Red: `0x00000002`
  - LED Blinking Red: `0x00000004`
  - LED On Green: `0x00000008`
  - LED Blinking Green: `0x00000010`
  - LED On Orange: `0x00000020`
  - LED Blinking Orange: `0x00000040`

  **Note**: For the LEDs **S1** and **S2** only the **No Change**, **LED Off** and **LED On Green** operation modes are valid.

## Return Values

- **0**: no error, function succeeded.
- **!= 0**: error, function failed. Check whether your device supports this function and you have an appropriate driver installed on the device.

## Example

See [xlAcquireLED](CAPLfunctionxlAcquireLED.md)
