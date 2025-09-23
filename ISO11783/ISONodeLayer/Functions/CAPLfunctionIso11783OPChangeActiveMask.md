# Iso11783OPChangeActiveMask

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeActiveMask( dword ecuHandle, dword maskID );
```

## Description

This function changes the active data mask. The **Change Active Mask** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **maskID**: Object ID of the data mask object, which should be activated

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeActiveMask( handle, 1000 );
```
