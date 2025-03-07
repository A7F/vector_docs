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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)