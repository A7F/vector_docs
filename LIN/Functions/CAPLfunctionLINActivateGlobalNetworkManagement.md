[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINActivateGlobalNetworkManagement.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linActivateGlobalNetworkManagement

# linActivateGlobalNetworkManagement

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linActivateGlobalNetworkManagement(long active);
```

## Description

Activates/deactivates network management for the entire LIN network (the channel is determined by the CAPL program context).

Network management is responsible for the automatic setting and resetting of response error signals in the simulated Slave nodes.

## Parameters

- **active**
  - 0: deactivate
  - 1: activate

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linActivateSlaveNetworkManagement](CAPLfunctionLINActivateSlaveNetworkManagement.md) • [linCheckRespError](CAPLfunctionLINCheckRespError.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
