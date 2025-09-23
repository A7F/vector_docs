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
