[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoSetAbortControl.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSDOSetAbortControl

# coTfsSDOSetAbortControl

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOSetAbortControl(dword controlValue);
```

## Description

The function defines which values are allowed for successful test completion.

## Parameters

- **controlValue**
  - 1: correct response or accepted SDO abort code (see [coTfsSDOAddAccAbortCode](CAPLfunctionCoTfsSdoAddAccAbortCode.md)) is allowed for successful test completion, default
  - 2: correct response or any SDO abort code is allowed
  - 3: correct response is not allowed
  - 4: correct response is not allowed but any SDO abort code

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* Accept correct answer or all SDO abort codes, which are in the list of accepted SDO abort codes to pass a test. */
const kSetAbortControlDefault = 1;

/* Accept correct answer or any SDO abort code to pass a test. */
const kSetAbortControlAllSDOAborts = 2;

/* Accept all SDO abort codes, which are in the list of accepted SDO abort codes to pass a test. The correct answer is not valid. */
const kSetAbortControlOnlySdoAbort = 3;

/* Accept any SDO abort codes to pass a test. The correct answer is not valid. */
const kSetAbortControlOnlyAnySdoAbort = 4;

/* Set internal handling of correct answers and SDO abort codes for level 2 SDO test functions. */
if (coTfsSDOSetAbortControl(kSetAbortControlDefault) != 1)
{
  /* command failed */
} /* if */

/* now run any SDO level 2 function like coTfsSDOUpload(), ... */
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)