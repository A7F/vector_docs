[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsNmtStopNode.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsNmtStopNode**

# coTfsNmtStopNode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsNmtStopNode( void );
long coTfsNmtStopNode( dword broadcastFlag );
```

## Description

This call triggers a NMT message that sets the in DUT (Device Under Test) to the stopped state. The new state is not checked because SDO transfers are not allowed in stopped mode.

## Parameters

- **broadcastFlag**: 
  - `!=0`: NMT message is sent to all nodes (broadcast)

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if ( coTfsNmtStopNode() != 1) {
  write("stop node failed");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)