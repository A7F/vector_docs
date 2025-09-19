# coTfsDeactivateGenericMonitor (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsDeactivateGenericMonitor( void );
long coTfsDeactivateGenericMonitor( dword canId, dword dlc );
```

## Description

This function stops monitoring and evaluates the monitoring results.

## Parameters

- **canId**: CAN-ID of the monitored message.
- **dlc**: Message length in byte, [0..8].

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

—
