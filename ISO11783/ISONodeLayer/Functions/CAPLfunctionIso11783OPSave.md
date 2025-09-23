# Iso11783OPSave

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSave( dword ecuHandle, char filename[] );
```

## Description

The function saves an object pool file (*.iop).

## Parameters

- **ecuHandle**  
  Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

- **filename**  
  Filename of an object pool file (*.IOP)

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
dword handle = 0;
handle = Iso11783CreateECU( gECUName );

Iso11783OPSave(handle, "ObjectPool.iop");
```
