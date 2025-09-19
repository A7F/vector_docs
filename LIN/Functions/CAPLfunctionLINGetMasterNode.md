[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetMasterNode.md)

# linGetMasterNode

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetMasterNode

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linGetMasterNode();
```

## Description

This function returns a unique internal ID for the current LIN master node of the channel given by the current bus context. See [SetBusContext](../../Other/Functions/CAPLfunctionSetBusContext.md) for how to change the current bus context.

The return value may be used as input parameter to a call to [linSetMasterNode(long nodeId)](CAPLfunctionLINSetMasterNode.md).

The return value must not be used between measurements, as these will be newly generated each time the measurement is started.

## Parameters

—

## Return Values

Node ID of the current master node. If the return value is 0 (zero), the function failed, or there is currently no LIN master node assigned.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
