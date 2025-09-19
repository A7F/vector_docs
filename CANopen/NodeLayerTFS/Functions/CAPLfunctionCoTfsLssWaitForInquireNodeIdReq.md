# coTfsLssWaitForInquireNodeIdRequest (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForInquireNodeIdRequest( dword nodeId );
```

## Description

This function waits for the **Inquire node-ID** request and sends the response.

## Parameters

- **nodeId**: New node-ID to be configured, valid values range 1..127 and 255.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* waits for LSS inquire node ID request */
if (coTfsLssWaitForInquireNodeIdRequest( 112 ) == 1) {
  /* received LSS inquire node ID request, sent response with node ID */
}
```
