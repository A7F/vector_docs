# Iso11783OPSetNumericValue

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSetNumericValue( dword ecuHandle, dword objectID, long numericValue );
long Iso11783OPSetNumericValue( dword ecuHandle, dword objectID, long numericValue, long options );
```

## Description

The function sets the numerical value of an object. The object must exist in the object pool and must support a numerical value. If the Object Pool API is active, a **Change Numeric Value** command is sent to the Virtual Terminal. This can be suppressed with Bit 0 in options.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of the object that has an updated value
- **numericValue**: New value within the value range of the object
- **options**: Options  
  Bit 0 = 1 Suppress **Change Numeric Value** command

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPSetNumericValue( handle, 1000, 100 );
```
