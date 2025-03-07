[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSendFastScanReq.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsLssSendFastScanRequest

# coTfsLssSendFastScanRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendFastScanRequest( dword idNumber, dword bitCheck, dword sub, dword next );
```

## Description

This function sends a **LSS fast scan protocol** request.

## Parameters

- **idNumber**: FastScan ID
- **bitCheck**: FastScan bitcheck value, used to define the used bitmask for LSS FastScan.
- **sub**: FastScan sub, defines which part of the LSS-ID is transmitted in **idNumber**.
  - 0 - vendor-ID
  - 1 - product code
  - 2 - revision number
  - 3 - serial number
- **next**: FastScan next, specifies the **sub** for the next request.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* send LSS fast scan protocol request */

if (coTfsLssSendFastScanRequest(0x000002, 28, 1, 1) == 1) {
  /* request sent */
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)