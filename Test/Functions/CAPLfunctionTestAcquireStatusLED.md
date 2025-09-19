[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestAcquireStatusLED.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestAcquireStatusLED

# TestAcquireStatusLED

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestAcquireStatusLED(dword ledBitMask);
```

## Description

Can be used in standalone mode to assign the test module state to an LED.

**States:**

- Off: Test module was never run in current measurement
- Blinking, Green: Test module is currently running, verdict is passed
- Blinking, Red: Test module is currently running, verdict is failed
- On, Green: Test module has ended, verdict is passed
- On, Red: Test module has ended, verdict is failed

## Parameters

- **ledBitMask**: The LED that wants to be used. Available bitmasks under [xlAcquireLED](../../Other/Functions/CAPLfunctionxlAcquireLED.md). The LED’s **Keypad S1** and **Keypad S2** cannot be used for test modules.

## Return Values

- **0**: Success
- **-1**: General error, e.g. not in standalone mode
- **> 0**: Error, function failed. Check whether your device supports this function and you have an appropriate driver installed on the device.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
