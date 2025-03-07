[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoSetSdoAbortOnError.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSDOSetSdoAbortOnError**

# coTfsSDOSetSdoAbortOnError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOSetSdoAbortOnError( dword setSdoAbort );
```

## Description

This function enables/disables sending a SDO abort code by the test module if a SDO access by SDO Level 2 functions or other test functions, that implicitly uses the SDO functionality, has failed. The setting is used until a new call of this function. For this the node-ID of the test module and the SDO abort code 0x8000 0000 (general error) is used.

## Parameters

- **setSdoAbort**
  - 0: no SDO abort message is sent in error cases (default)
  - 1: a SDO abort message is sent in error cases

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSDOSetSdoAbortOnError(1); /* if a SDO error is encountered, the SDO abort message will be sent from now */

coTfsSdoUpload(0x1000,0);

/* set default value – disable automatic sending of SDO abort messages by the test module */
coTfsSDOSetSdoAbortOnError(0);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)