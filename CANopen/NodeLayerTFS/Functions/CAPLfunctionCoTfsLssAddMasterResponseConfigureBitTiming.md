# coTfsLssAddMasterResponseConfigureBitTiming (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseConfigureBitTiming( dword tableSelector, dword tableSelectorMask, dword tableIndex, dword tableIndexMask, dword errCode, dword specError );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions and sends a response if a request is received.

## Parameters

- **tableSelector**: Selects which bit timing parameter table shall be used.
  - 0 - standard CiA® bit timing table
  - 1..127 - reserved
  - 128..255 - may be used for manufacturer specific bit timings

- **tableSelectorMask**: Mask for table selector; set bits are compared, not set bits are not compared.

- **tableIndex**: CAN bitrate index.
  - 0 = 1 MBit/s
  - 1 = 800 kBit/s
  - 2 = 500 kBit/s
  - 3 = 250 kBit/s
  - 4 = 125 kBit/s
  - 5 = 100 kBit/s (reserved value, do not use)
  - 6 = 50 kBit/s
  - 7 = 20 kBit/s
  - 8 = 10 kBit/s

- **tableIndexMask**: Mask for table index; set bits are compared, not set bits are not compared.

- **errCode**: Error code.
  - 0 - protocol successfully completed
  - 1 - bit timing not supported
  - 255 - implementation specific error occurred

- **specError**: Manufacturer specific error (used if error code = 255).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

---
