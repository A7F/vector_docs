# coTfsLssAddMasterResponseActivateBitTiming (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssAddMasterResponseActivateBitTiming( dword switchDelay, dword switchDelayMask );
```

## Description

This function adds a single LSS Master request wait condition to the internal list of LSS Master request wait conditions.

## Parameters

- **switchDelay**: Duration (in ms) of the two periods of time to wait until the bit timing parameters switch is done (first period) and before transmitting any CAN message with the new bit timing parameters after performing the switch (second period).

- **switchDelayMask**: Mask for switch delay; set bits are compared, not set bits are not compared.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)
