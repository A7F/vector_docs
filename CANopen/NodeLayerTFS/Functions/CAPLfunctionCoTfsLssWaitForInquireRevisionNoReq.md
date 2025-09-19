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
