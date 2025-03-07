[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINResetMasterNode.md)

## linResetMasterNode

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linResetMasterNode

### Function Syntax

```plaintext
long linResetMasterNode();
```

### Description

Calling this function reverses the effect of [linSetMasterNode](CAPLfunctionLINSetMasterNode.md). Sending LIN headers (by calling [linTransmitHeader](CAPLfunctionLINTransmitHeader.md) or similar functions) is no longer restricted to the currently assigned LIN master node. If a node is assigned as LDF master node, the LIN scheduler will be reset to its state before [linSetMasterNode](CAPLfunctionLINSetMasterNode.md) was called.

### Parameters

—

### Return Values

Node ID of the previous master node. If the return value is 0 (zero), the function failed, or there was no previous LIN master node.

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)