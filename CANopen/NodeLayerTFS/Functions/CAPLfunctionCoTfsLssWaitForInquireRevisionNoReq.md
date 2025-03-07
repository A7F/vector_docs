[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssWaitForInquireRevisionNoReq.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsLssWaitForInquireRevisionNoRequest**

# coTfsLssWaitForInquireRevisionNoRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
long coTfsLssWaitForInquireRevisionNoRequest( dword revisionNo );
```

## Description

This function waits for the **Inquire revision number** request and sends the response.

## Parameters

- **revisionNo**: Revision number part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
/* waits for LSS inquire revision number request */
if (coTfsLssWaitForInquireRevisionNoRequest( 0x12345678 ) == 1) {
  /* received LSS inquire revision number request, sent response with revision number */
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)