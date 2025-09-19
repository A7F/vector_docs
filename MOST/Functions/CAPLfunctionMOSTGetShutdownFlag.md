[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetShutdownFlag.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetShutdownFlag

# mostGetShutdownFlag

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetShutdownFlag(long channel);
```

## Description

Returns the current state of the Shutdown flag.

## Parameters

- **channel**: Application channel number.

## Return Values

- **1**: Shutdown Flag set.
- **0**: Shutdown Flag not set.
- **< 0**: MOST CAPL [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
