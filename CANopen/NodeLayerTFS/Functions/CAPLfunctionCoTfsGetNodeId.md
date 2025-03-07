[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsGetNodeId.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsGetNodeId**

# coTfsGetNodeId

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword coTfsGetNodeId( void );
```

## Description

This function returns the internally-stored node-ID that is used for the simplified test functions.

## Parameters

—

## Return Values

Node-ID

## Example

```c
dword nodeID;
nodeID = coTfsGetNodeId();
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)