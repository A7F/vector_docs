# coTfsSDOChkForUnexpectedAbort (Level 2)

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
dword coTfsSDOChkForUnexpectedAbort( void );
```

## Description

This functions checks for unexpected SDO abort codes that are not in the list of accepted SDO abort codes. Therefore the function compares the list of received SDO abort codes with the list of accepted SDO abort codes.

- If a SDO abort code was received which is not in the list of accepted SDO abort codes, the function result is passed.
- If a SDO abort code was received which is in the list of accepted SDO abort codes, this code is considered to be expected, so the function result is failed.
- If no SDO abort code was received, then there is no unexpected SDO abort code. The function result is failed.

**Note**: The user has to reset both SDO abort code lists: the list of [received SDO abort codes](CAPLfunctionCoTfsSdoResetAbortList.md) and the list of [accepted SDO abort codes](CAPLfunctionCoTfsSdoResetAccAbortList.md).

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* clear list with received SDO abort codes first */
coTfsSDOResetAbortList();

/* no SDO abort code is accepted to pass this test, configured accepted SDO abort codes are treated like expected responses */
coTfsSDOResetAccAbortList();

/* Try to read a non-existing object. The DUT will answer with an SDO abort code */
coTfsSdoUpload(0x999,0);

if (coTfsSDOChkForUnexpectedAbort() != 1)
{
  /* no SDO abort code occurred: object exists or device is not connected ? */
} /* if */
```
