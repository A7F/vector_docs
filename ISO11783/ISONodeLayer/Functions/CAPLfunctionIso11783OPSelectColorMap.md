# Iso11783OPSelectColorMap

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSelectColorMap( dword ecuHandle, dword  colorMapID );
```

## Description

The function selects a color map object. A **Select Color Map** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **colorMapID**: Object ID of the color map objects

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPSelectColorMap( handle, 1400 );
```
