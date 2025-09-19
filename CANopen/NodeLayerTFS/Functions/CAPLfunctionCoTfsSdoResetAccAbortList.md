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
