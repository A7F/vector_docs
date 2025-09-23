# Iso11783OPSaveAuxAssignment

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSaveAuxAssignment( dword ecuHandle, char filename[] );
```

## Description

The function saves the current auxiliary input assignment as "Preferred Auxiliary Input Assignment" in an ini file.

With the function [Iso11783OPLoadAuxAssignment](CAPLfunctionIso11783OPLoadAuxAssignment.md) the "Preferred Assignment" can be load and used again.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).
- **filename**: Filename of an ini file (*.INI)

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
dword handle = 0;
handle = Iso11783CreateECU( gECUName );
[...]
Iso11783OPSaveAuxAssignment( handle, "Sprayer.INI");
[...]
```
