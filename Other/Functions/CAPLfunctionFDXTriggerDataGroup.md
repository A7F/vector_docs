# FDXTriggerDataGroup

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long FDXTriggerDataGroup (WORD goupID);
```

## Description

This function triggers the transmission of a data group via [FDX protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocol.md).

## Parameters

- **groupID**: ID of the FDX data group that should be transmitted.

## Return Values

- **0**: Success
- **-1**: The given data group is not configured.
- **-2**: No client is registered to receive this data group.

## Example

```plaintext
// CANoe FDX data exchange synchronously to FlexRay cycle
// Whenever slot 5 of the FlexRay cycle will be reached, the FDX data group 10 is transmitted one time 

on frSlot 5
{
   FDXTriggerDataGroup(10);
}
```
