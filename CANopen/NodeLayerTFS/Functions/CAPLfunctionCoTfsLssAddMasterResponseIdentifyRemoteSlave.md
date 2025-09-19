# coTfsLssAddMasterResponseIdentifyRemoteSlave (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
If you want to use this function, you have to call [coTfsLssSetMasterResponseIdentifyRemoteSlaveMask](CAPLfunctionCoTfsLssSetMasterResponseIdentifyRemoteSlaveMask.md) before. In that function the necessary masks for the function parameters are set.

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseIdentifyRemoteSlave( dword vendorId, dword productCode, dword revisionNoLow, dword revisionNoHigh, dword serialNoLow, dword serialNoHigh );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions and sends a response if a request is received.

## Parameters

- **vendorId**: Vendor-ID
- **productCode**: Product code
- **revisionNoLow**: Low boundary of the revision number.
- **revisionNoHigh**: High boundary of the revision number.
- **serialNoLow**: Low boundary of the serial number.
- **serialNoHigh**: High boundary of the serial number.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)
