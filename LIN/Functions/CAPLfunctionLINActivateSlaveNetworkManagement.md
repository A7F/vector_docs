[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINActivateSlaveNetworkManagement.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linActivateSlaveNetworkManagement

# linActivateSlaveNetworkManagement

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linActivateSlaveNetworkManagement(long active);
```

## Description

Activates/deactivates network management for the calling Slave node. Network management is responsible for the automatic setting and resetting of response error signals in the simulated Slave nodes.

## Parameters

- **active**
  - 0: deactivate
  - 1: activate

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linActivateGlobalNetworkManagement](CAPLfunctionLINActivateGlobalNetworkManagement.md) • [linCheckRespError](CAPLfunctionLINCheckRespError.md) • [linGetRespError](CAPLfunctionLINGetRespError.md)
