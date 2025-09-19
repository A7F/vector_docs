# coTfsLssSendConfigureBitTimingResponse (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendConfigureBitTimingResponse( dword errorCode, dword specificError );
```

## Description

This function sends the **LSS Configure Bit-Timings Parameters** response.

## Parameters

- **errorCode**: Error code.
  - 0 - protocol successfully completed
  - 1 - bit timing not supported
  - 255 - implementation specific error occurred

- **specificError**: Manufacturer specific error (used if error code = 255).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* send LSS configure bit timing response with error code and specific error = 0*/

if (coTfsLssSendConfigureBitTimingResponse( 0, 0 ) != 1) {
  /* message could not be sent */
}
```
