# Iso11783OPGetNumericValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPGetNumericValue( dword ecuHandle, dword objectID );
```

## Description

The function returns a numeric value of an object. The object must exist in the object pool and must support a numeric value.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object Identifier of the object

## Return Values

- Integer value of the object.
- If a value of 0 is returned, you can check with the function [Iso11783GetLastError](CAPLfunctionIso11783Getlasterror.md) if the function succeeded.

## Example

```plaintext
LONG val;
val = Iso11783OPGetNumericValue( handle, 1000 );
```
