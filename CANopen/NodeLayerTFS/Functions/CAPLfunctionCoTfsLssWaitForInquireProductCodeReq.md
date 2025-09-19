# coTfsLssWaitForInquireProductCodeRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForInquireProductCodeRequest( dword productCode );
```

## Description

This function waits for the **Inquire product code** request and sends the response.

## Parameters

- **productCode**: Product code part of the LSS address.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* waits for LSS inquire product code request */
if (coTfsLssWaitForInquireProductCodeRequest( 0x12345678) == 1) {
  /* received LSS inquire vendor ID request, sent response with product code */
}
```
