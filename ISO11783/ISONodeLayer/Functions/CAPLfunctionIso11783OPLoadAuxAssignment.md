# Iso11783OPLoadAuxAssignment

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPLoadAuxAssignment( dword ecuHandle, char filename[] );
```

## Description

This function loads the "Preferred Auxiliary Input Assignment" from an ini file. If the ECU is active, the "Preferred Assignment Message" is sent immediately. Otherwise, it is sent if the ECU gets active.

The "Preferred Assignment" must be saved with [Iso11783OPSaveAuxAssignment](CAPLfunctionIso11783OPSaveAuxAssignment.md) before.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).
- **filename**: Filename of an INI file

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPLoad( handle, "ObjectPool.iop", "pool001" );
Iso11783OPLoadAuxAssignment( handle, "Sprayer.INI");
Iso11783OPActivate( handle);
```
