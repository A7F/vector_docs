[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionxlReleaseLED.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » xlReleaseLED

# xlReleaseLED

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword xlReleaseLED(dword ledBitMask);
```

## Description

Releases the specified LEDs after they were successfully acquired with a call of [xlAcquireLED](CAPLfunctionxlAcquireLED.md).

This function is supported by the following device: VN8900 (driver version > 7.5)

## Parameters

- **ledBitMask**: The LEDs you want to release. Note that you can bitwise combine the values to specify multiple LEDs.

  The following LEDs are available for VN8900 devices:

  - **Module (M)**: 0x001
  - **CAN Channel 1**: 0x008
  - **CAN Channel 2**: 0x010
  - **CAN Channel 3**: 0x020
  - **CAN Channel 4**: 0x040
  - **FlexRay Channel 1 A**: 0x080
  - **FlexRay Channel 1 B**: 0x100
  - **Keypad S1**: 0x200
  - **Keypad S2**: 0x400

## Return Values

- **0**: no error, function succeeded.
- **!= 0**: error, function failed. Check whether your device supports this function and you have an appropriate driver installed on the device.

## Example

See [xlAcquireLED](CAPLfunctionxlAcquireLED.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
