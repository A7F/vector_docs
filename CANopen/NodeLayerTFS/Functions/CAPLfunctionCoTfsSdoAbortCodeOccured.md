[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoAbortCodeOccured.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSDOAbortCodeOccurred

# coTfsSDOAbortCodeOccurred (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**

The extended SDO abort handling feature is not supported on using the following functions:

- [coTfsODChk](CAPLfunctionCoTfsOdChk.md)
- [coTfsODChkNotExist](CAPLfunctionCoTfsOdChkNotExist.md)
- [coTfsODChkSingleEntry](CAPLfunctionCoTfsOdChkSingleEntry.md)
- [coTfsODChkSingleEntryNotExist](CAPLfunctionCoTfsOdChkSingleEntryNotExist.md)
- [coTfsODChkStdEntries](CAPLfunctionCoTfsOdChkStdEntries.md)

The functions maintain SDO abort codes by themselves and execute the function [coTfsSDOResetAccAbortList](CAPLfunctionCoTfsSdoResetAccAbortList.md) independently. If you configured any SDO abort code lists before, you have to create them again after using one of the listed functions.

## Function Syntax

```plaintext
long coTfsSDOAbortCodeOccurred( dword resetAbortList );
```

## Description

This function checks if a previously executed coTfsSDO… command can be finished with a received and accepted SDO abort code.

## Parameters

- **resetAbortList**: `!=0`: resets the list with received and accepted SDO abort codes (see [coTfsSDOResetAbortList](CAPLfunctionCoTfsSdoResetAbortList.md))

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* clear list with received SDO abort codes first */
coTfsSDOResetAbortList();

/* Try to read a non-existing object. The DUT will answer with an SDO abort code */
coTfsSdoUpload(0x999,0);

/* perform other SDO accesses ... */
/* did any SDO abort code occur ? */
if (coTfsSDOAbortCodeOccurred(1) != 1)
{
  /*
   * no SDO abort code occurred
   * object exists or device is not connected ?
  */
} /* if */
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)