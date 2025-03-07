[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSetNodeId.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSetNodeId**

# coTfsSetNodeId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
This function must be called before any other test function is called to provide the usage of the correct node-ID.

## Function Syntax

```plaintext
long coTfsSetNodeId( dword nodeID );
```

## Description

The internal node-ID for the simplified test functions is set.

## Parameters

- **nodeID**: 0 < node-ID < 128

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSetNodeId (2); // set node-ID = 2
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)