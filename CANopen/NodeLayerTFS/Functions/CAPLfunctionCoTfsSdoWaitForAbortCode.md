# coTfsSDOWaitForAbortCode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOWaitForAbortCode( dword nodeID );
```

## Description

This function waits until either a SDO abort message was received by the selected DUT (Device Under Test) or a time-out has occurred. After this, the abort code can be read out with [coTfsSDOGetAbortCode](CAPLfunctionCoTfsSdoGetAbortCode.md).

## Parameters

- **nodeID**: Node-ID

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if ( coTfsSDOWaitForAbortCode(2) == 1) {
  write("SDO abort message received, use coTfsSdoGetAbortCode to retrieve its data");
}
```
