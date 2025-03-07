[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetRespError.md)

# linSetRespError

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetRespError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long linSetRespError(long activate);
```

## Description

Sets/resets the response error flag for a calling slave node.

**Note**: This function has no effect with LIN 1.x.

## Parameters

- **activate**
  - `0`: reset
  - `1`: set

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linGetRespError](CAPLfunctionLINGetRespError.md) • [linCheckRespError](CAPLfunctionLINCheckRespError.md) • [linActivateGlobalNetworkManagement](CAPLfunctionLINActivateGlobalNetworkManagement.md) • [linActivateSlaveNetworkManagement](CAPLfunctionLINActivateSlaveNetworkManagement.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)