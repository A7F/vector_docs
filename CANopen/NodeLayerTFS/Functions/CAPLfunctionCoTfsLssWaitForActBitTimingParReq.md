# coTfsLssWaitForActivateBitTimingRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForActivateBitTimingRequest( dword[] pSwitchDelay );
```

## Description

This function waits for **LSS Activate Bit-Timings Parameters** request.

## Parameters

- **pSwitchDelay**: Duration (in ms) of the two periods of time to wait until the bit timing parameters switch is done (first period) and before transmitting any CAN message with the new bit timing parameters after performing the switch (second period).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword pSwitchDelay[1];

/* waits for LSS activate bit timing request */
if (coTfsLssWaitForActivateBitTimingRequest( pSwitchDelay) == 1) {
  /* received LSS activate bit timing request */
  /* received values can be found in pSwitchDelay[0] */
}
```
