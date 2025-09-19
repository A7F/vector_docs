[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetTxLightPower.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetTxLightPower

# mostSetTxLightPower

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This functionality is only available for VN2600/VN2610/VN2640 hardware.

## Function Syntax

```plaintext
long mostSetTxLightPower(long channel, long power);
```

## Description

Sets the intensity of the light at the Fiber Optical Transmitter (FOT).

The result is reported by means of the callback function [OnMostStress()](../EventProcedures/CAPLfunctionOnMOSTStress.md).

## Parameters

- **channel**: Channel of the interface to be driven
- **power**: valid values:
  - **50**: 3db attenuated to normal intensity
  - **100**: normal intensity

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetTxLight](CAPLfunctionMOSTSetTxLight.md) • [mostGetTxLight](CAPLfunctionMOSTGetTxLight.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
