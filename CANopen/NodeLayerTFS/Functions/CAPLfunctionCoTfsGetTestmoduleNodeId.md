[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsGetTestmoduleNodeId.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsGetTestModuleNodeId**

# coTfsGetTestModuleNodeId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword coTfsGetTestModuleNodeId( void );
```

## Description

The function gets the node-ID of the tester.

## Parameters

—

## Return Values

Node-ID of the tester.

## Example

```c
dword nodeId;
nodeId = coTfsGetTestModuleNodeId();
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)