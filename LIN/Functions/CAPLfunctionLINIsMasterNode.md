[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINIsMasterNode.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linIsMasterNode

# linIsMasterNode

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long linIsMasterNode();
```

## Description

This function returns 1 if the calling node is the current LIN master node of the network given by the current bus context. This will be the node assigned to the LIN master from the LDF if [linSetMasterNode](CAPLfunctionLINSetMasterNode.md) has not been called before, or the node referred to by the previous call of [linSetMasterNode](CAPLfunctionLINSetMasterNode.md).

See [SetBusContext](../../Other/Functions/CAPLfunctionSetBusContext.md) for how to change the current bus context.

## Parameters

—

## Return Values

1 if the calling node is the current LIN master node, 0 otherwise.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
