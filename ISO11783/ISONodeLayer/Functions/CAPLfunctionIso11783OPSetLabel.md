# Iso11783OPSetLabel

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSetLabel( dword ecuHandle, dword objectID, 
 dword stringVarIdD, dword fontType, dword graphID );
```

## Description

A **Set Label** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID which is assigned to the label
- **stringVarID**: Object ID of the string variable object
- **fontType**: Font type
- **graphID**: Object ID of a graphical object

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPSetLabel( handle, 1200, 1250, 1, 1260 );
```
