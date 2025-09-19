[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetHWReceiveAccuracy.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGetHWReceiveAccuracy

# linGetHWReceiveAccuracy

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linGetHWReceiveAccuracy();
```

## Description

This function can be used to query the receive resolution of the LIN hardware in units of 1 Hz.

## Parameters

—

## Return Values

Returns the receive resolution of the LIN hardware.

## Example

```c
on key 't'
{
    write("Transmit accuracy = %d", linGetHWTransmitAccuracy());
    write("Receive  accuracy = %d", linGetHWReceiveAccuracy());
}
```

[linGetHWTransmitAccuracy](CAPLfunctionLINGetHWTransmitAccuracy.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
