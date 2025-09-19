[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionxlAcquireLED.md)

## xlAcquireLED

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » xlAcquireLED

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```plaintext
dword xlAcquireLED(dword ledBitMask);
```

### Description

Acquires the specified LEDs of a hardware device in order to set their operation mode with [xlSetLED](CAPLfunctionxlSetLED.md) afterwards.

This function is only supported on VN8900 devices.

Note that for every successful call of `xlAcquireLED` on a specific LED, you have to call [xlReleaseLED](CAPLfunctionxlReleaseLED.md) to release this LED again.

### Parameters

- **ledBitMask**: The LEDs you want to acquire. Note that you can bitwise combine the values to specify multiple LEDs. The following LEDs are available for VN8900 devices:
  - **Module (M)**: 0x001
  - **CAN Channel 1**: 0x008
  - **CAN Channel 2**: 0x010
  - **CAN Channel 3**: 0x020
  - **CAN Channel 4**: 0x040
  - **FlexRay Channel 1 A**: 0x080
  - **FlexRay Channel 1 B**: 0x100
  - **Keypad S1**: 0x200
  - **Keypad S2**: 0x400

### Return Values

- **0**: no error, function succeeded.
- **!= 0**: error, function failed. Check whether your device supports this function and you have an appropriate driver installed on the device.

### Example

At measurement start three LEDs are acquired, two LEDs are set to condition "orange glowing", and one is set to the condition "orange flashing". At measurement stop the LEDs should be released.

```plaintext
/*@@var:*/
variables
{
   // constants for LED access
   const dword kLedMaskC1         = 0x008;
   const dword kLedMaskC2         = 0x010;
   const dword kLedMaskC3         = 0x020;
   // constants for LED operation modes
   const dword kLedOrangeOn       = 0x00000020;
   const dword kLedOrangeBlinking = 0x00000040;

   dword status;
}
/*@@end*/

/*@@startStart:Start:*/
on start
{
   status = xlAcquireLED(kLedMaskC1 | kLedMaskC2 | kLedMaskC3);
   if( 0 == status)
   {
      xlSetLed(kLedMaskC1 | kLedMaskC2, kLedOrangeOn);
      xlSetLed(kLedMaskC3, kLedOrangeBlinking);
   }
}
/*@@end*/

/*@@stop:StopMeasurement:*/
on stopMeasurement
{
   if( 0 == status)
   {
      xlReleaseLED(kLedMaskC1 | kLedMaskC2 | kLedMaskC3);
   }
}
/*@@end*/
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
