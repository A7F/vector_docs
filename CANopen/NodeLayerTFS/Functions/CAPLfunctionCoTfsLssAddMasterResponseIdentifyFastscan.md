# coTfsLssAddMasterResponseIdentifyFastscan (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseIdentifyFastscan( dword idNumber, dword idNumberMask, dword bitCheck, dword bitCheckMask, dword sub, dword subMask, dword next, dword nextMask );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions and sends a response if a request is received.

## Parameters

- **idNumber**: FastScan ID
- **idNumberMask**: Mask for FastScan ID; set bits are compared, not set bits are not compared.
- **bitCheck**: FastScan bitcheck value, used to define the used bitmask for LSS FastScan.
- **bitCheckMask**: Bitmask for LSS FastScan; set bits are compared, not set bits are not compared.
- **sub**: FastScan sub, defines which part of the LSS-ID is transmitted in **idNumber**
  - 0 - vendor-ID
  - 1 - product code
  - 2 - revision number
  - 3 - serial number
- **subMask**: Mask for FastScan sub; set bits are compared, not set bits are not compared.
- **next**: FastScan next, specifies the **sub** for the next request.
- **nextMask**: Mask for FastScan next; set bits are compared, not set bits are not compared.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)
