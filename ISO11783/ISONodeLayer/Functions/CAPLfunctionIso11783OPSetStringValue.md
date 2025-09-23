# Iso11783OPSetStringValue

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSetStringValue( dword ecuHandle, dword objectID, char stringValue[] );
long Iso11783OPSetStringValue( dword ecuHandle, dword objectID, char stringValue[], dword options );
```

## Description

The functions set the string value of an object in the object pool. The object must exist in the object pool and must support a string value. If the Object Pool API is active, a **Change String Value** command is sent to the Virtual Terminal. This can be suppressed with Bit 0 in `options`.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of the object that has an updated value
- **stringValue**: Buffer containing new string value
- **options**: Options  
  Bit 0 = 1 Suppress **Change String Value** command

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../CAPLfunctionsISONLErrorCodes.md)
- **-1109**: String is read only
- **-1110**: Object ID not found
- **-1112**: String Value not supported

## Example

```plaintext
Iso11783OPSetStringValue( handle, 1000, "Hello World" );
```
