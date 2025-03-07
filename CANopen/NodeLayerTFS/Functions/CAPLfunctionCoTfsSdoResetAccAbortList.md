[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoResetAccAbortList.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSDOResetAccAbortList**

# coTfsSDOResetAccAbortList (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**

The extended SDO abort handling feature is not supported on using the following functions:

- [coTfsODChk](CAPLfunctionCoTfsOdChk.md)
- [coTfsODChkNotExist](CAPLfunctionCoTfsOdChkNotExist.md)
- [coTfsODChkSingleEntry](CAPLfunctionCoTfsOdChkSingleEntry.md)
- [coTfsODChkSingleEntryNotExist](CAPLfunctionCoTfsOdChkSingleEntryNotExist.md)
- [coTfsODChkStdEntries](CAPLfunctionCoTfsOdChkStdEntries.md)

The functions maintain SDO abort codes by themselves and execute the function [coTfsSDOResetAccAbortList](#) independently. If you configured any SDO abort code lists before, you have to create them again after using one of the listed functions.

## Function Syntax

```plaintext
long coTfsSDOResetAccAbortList( void );
```

## Description

The function resets the internal list of accepted abort codes.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSDOResetAccAbortList( );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)