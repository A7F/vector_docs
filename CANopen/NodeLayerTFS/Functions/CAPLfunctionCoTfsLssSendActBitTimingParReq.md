# coTfsLssSendActivateBitTimingRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendActivateBitTimingRequest( dword switchDelay );
```

## Description

This function sends a **LSS Activate Bit-Timing Parameter** request.

## Parameters

- **switchDelay**: Duration (in ms) of the two periods of time to wait until the bit timing parameters switch is done (first period) and before transmitting any CAN message with the new bit timing parameters after performing the switch (second period).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* send LSS activate bit timing protocol request */

if (coTfsLssSendActivateBitTimingRequest( 1000) != 1) {
/* message could not be sent */
}
```
