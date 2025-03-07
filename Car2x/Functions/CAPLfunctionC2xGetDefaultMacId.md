[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetDefaultMacId.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetDefaultMacId

# C2xGetDefaultMacId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xGetDefaultMacId(byte macId[]);
```

## Description

This function reads the MAC-ID of a WLAN interface.

## Parameters

- **macId**: Destination array for the read MAC-ID with six elements.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
on start
{
  byte macId[6];
  if (C2xGetDefaultMacId(macId) == 0)
  {
    write("MAC ID is %.2X:%.2X:%.2X:%.2X:%.2X:%.2X:", macId[0], macId[1], macId[2], macId[3], macId[4], macId[5]);
  }
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)