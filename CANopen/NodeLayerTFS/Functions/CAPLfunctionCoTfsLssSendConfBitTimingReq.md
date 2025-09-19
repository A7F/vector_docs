# coTfsLssSendConfigureBitTimingRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendConfigureBitTimingRequest( dword tableSelector, dword tableIndex, byte[] pErrorCode, byte[] pSpecificError );
```

## Description

This function sends a **LSS Configure Bit-Timings Parameters** request and waits for the response.

## Parameters

- **tableSelector**: Selects which bit timing parameter table shall be used.
  - 0 - standard CiA® bit timing table
  - 1..127 - reserved
  - 128..255 - may be used for manufacturer specific bit timings

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

- **pErrorCode**: Error code.
  - 0 - protocol successfully completed
  - 1 - bit timing not supported
  - 255 - implementation specific error occurred

- **pSpecificError**: Manufacturer specific error (used if error code = 255).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pErrorCode[1];
byte pSpecificError[1];

/* send LSS configure bit timing request and wait for reponse*/

if (coTfsLssSendConfigureBitTimingRequest( 0, 3, pErrorCode, pSpecificError) == 1) {
  /* request sent with parameters tableSelector=0 and tableIndex=3 and DUT replied with correct response. Response values can be found in pErrorCode, pSpecificError */
}
```
