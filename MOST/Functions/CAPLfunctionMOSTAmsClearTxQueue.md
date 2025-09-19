[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAmsClearTxQueue.md)

**CAPL Functions** » **MOST** » **mostAmsClearTxQueue**

# mostAmsClearTxQueue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long mostAmsClearTxQueue(long channel);
```

## Description

Clears all entries in the AMS send buffer.

This command can be used to stop further sending of AMS messages in case of errors (e.g. critical unlock or light off) or if the system state changes to "NotOk".

## Parameters

- **channel**: Channel of the connected interface.

## Return Values

- **<= 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)