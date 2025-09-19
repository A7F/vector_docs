# coTfsLssWaitForInquireSerialNoRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForInquireSerialNoRequest( dword serialNo );
```

## Description

This function waits for the **Inquire serial number** request and sends the response.

## Parameters

- **serialNo**: Serial number part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* waits for LSS inquire serial number request */
if (coTfsLssWaitForInquireSerialNoRequest( 0x12345678 ) == 1) {
  /* received LSS inquire serial number request, sent response with serial number */
}
```
