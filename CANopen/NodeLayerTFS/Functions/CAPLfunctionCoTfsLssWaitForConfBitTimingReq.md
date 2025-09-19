# coTfsLssWaitForConfigureBitTimingRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForConfigureBitTimingRequest( byte[] pTableSelector, byte[] pTableIndex );
```

## Description

This function waits for **LSS Configure Bit-Timings Parameters** request.

## Parameters

- **pTableSelector**: Selects which bit timing parameter table shall be used.
  - 0 - standard CiA® bit timing table
  - 1..127 - reserved
  - 128..255 - may be used for manufacturer specific bit timings

- **pTableIndex**: CAN bitrate index.
  - 0 = 1 MBit/s
  - 1 = 800 kBit/s
  - 2 = 500 kBit/s
  - 3 = 250 kBit/s
  - 4 = 125 kBit/s
  - 5 = 100 kBit/s (reserved value, do not use)
  - 6 = 50 kBit/s
  - 7 = 20 kBit/s
  - 8 = 10 kBit/s

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pTableSelector[1];
byte pTableIndex[1];

/* waits for LSS configure bit timing request */
if (coTfsLssWaitForConfigureBitTimingRequest( pTableSelector, pTableIndex) == 1) {
  /* received LSS configure bit timing request */
  /* received values can be found in pTableSelector[0], pTableIndex[0] */
} else {
  /* no request received */
  return;
}
```
