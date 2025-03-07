[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoAddAccAbortCode.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSDOAddAccAbortCode**

# coTfsSDOAddAccAbortCode (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

### Note
The extended SDO abort handling feature is not supported on using the following functions:
- [coTfsODChk](CAPLfunctionCoTfsOdChk.md)
- [coTfsODChkNotExist](CAPLfunctionCoTfsOdChkNotExist.md)
- [coTfsODChkSingleEntry](CAPLfunctionCoTfsOdChkSingleEntry.md)
- [coTfsODChkSingleEntryNotExist](CAPLfunctionCoTfsOdChkSingleEntryNotExist.md)
- [coTfsODChkStdEntries](CAPLfunctionCoTfsOdChkStdEntries.md)

The functions maintain SDO abort codes by themselves and execute the function [coTfsSDOResetAccAbortList](CAPLfunctionCoTfsSdoResetAccAbortList.md) independently. If you configured any SDO abort code lists before, you have to create them again after using one of the listed functions.

## Function Syntax

```plaintext
long coTfsSDOAddAccAbortCode( dword abortCode );
long coTfsSDOAddAccAbortCode( dword abortCode, dword definedByStandard);
```

## Description

The function adds an abort code to the internal list of accepted abort codes for testing devices. If the DUT (Device under test) responds with one of the abort codes in the list, the test is set to **passed**.

The functions must be called before executing SDO downloads or uploads.

## Parameters

- **abortCode**: Abort code that is added to the internal list

  **Note**: These reserved values are deprecated and replaced by values of [coTfsSDOSetAbortControl](CAPLfunctionCoTfsSdoSetAbortControl.md):
  - `0x00000000`: a correct response of the DUT is not accepted
  - `0xFFFFFFFF`: each abort code is accepted

  **Note**: If the SDO abort code is set to 0, the response behavior of all test functions (except the object dictionary tests) is modified. A reset of the abort code list with [coTfsSDOResetAccAbortList](CAPLfunctionCoTfsSdoResetAccAbortList.md) is necessary after using this function.

- **definedByStandard**:
  - `0`: the abort code is interpreted as a user-specific abort code and marked with "Warning" in the test report, default
  - `!=0`: the abort code is interpreted as a standard abort code and marked with "Pass" in the test report

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* SDO abort code 0x06090000 will be accepted as a valid answer to pass a level 2 SDO function test, if coTfsSDOSetAbortControl is set to value 1 and 3. */
if (coTfsSDOAddAccAbortCode(0x06090000) != 1)
{
  /* failed */
} /* if */
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)