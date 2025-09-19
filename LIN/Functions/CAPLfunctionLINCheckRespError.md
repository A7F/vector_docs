[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINCheckRespError.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linCheckRespError

# linCheckRespError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linCheckRespError();
```

## Description

Queries the **response_error** flags of all Slave nodes defined in the LIN network.

## Parameters

—

## Return Values

- **-1**: Function call not allowed or execution failed.
- **0**: None of the slaves has the **response_error** flag set.
- **>0**: At least one of the slaves has the **response_error** flag set.

## Example

—

[linGetRespError](CAPLfunctionLINGetRespError.md) • [linSetRespError](CAPLfunctionLINSetRespError.md) • [linActivateGlobalNetworkManagement](CAPLfunctionLINActivateGlobalNetworkManagement.md) • [linActivateSlaveNetworkManagement](CAPLfunctionLINActivateSlaveNetworkManagement.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
