# Iso11783OPGetAttribute

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPGetAttribute( dword ecuHandle, dword objectID, dword attributeID );
```

## Description

The function returns a value of an object attribute from the local object pool. A **Get Attribute** command is **not** sent to the Virtual Terminal. The object must exist in the object pool and support the attribute ID.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object identifier of an object in the object pool
- **attributeID**: Attribute identifier, see [ISO11783-6](../../../../CANoeCANalyzer/ISO11783/iso11783basics/documentsISO11783.md)

## Return Values

- Integer value of the object.
- If a value of 0 is returned, you can check with the function [Iso11783GetLastError](CAPLfunctionIso11783Getlasterror.md) if the function succeeded.

## Example

```plaintext
LONG objType;
objType = Iso11783OPGetAttribute( handle, 1000, 0 );
```
