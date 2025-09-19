# coTfsLssWaitForFastScanRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForFastScanRequest( dword[] pId, byte[] pBitCheck, byte[] pSub, byte[] pNext );
```

## Description

This function waits for the **Fast Scan** message.

## Parameters

- **pId**: FastScan ID
- **pBitCheck**: FastScan bitcheck value, used to define the used bitmask for LSS FastScan.
- **pSub**: FastScan sub, defines which part of the LSS-ID is transmitted in `idNumber`.
  - 0 - vendor-ID
  - 1 - product code
  - 2 - revision number
  - 3 - serial number
- **pNext**: FastScan next, specifies the **sub** for the next request.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword pId[1];
byte  pBitCheck[1];
byte  pSub[1];
byte  pNext[1];

/* waits for the fast scan request */
if (coTfsLssWaitForFastScanRequest( pId, pBitCheck, pSub, pNext ) == 1) {
  /* request received */
  /* received values can be found in pId, pBitCheck, pSub, pNext */
}
```
