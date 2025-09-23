# Iso11783OPGetStringValue

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPGetStringValue( dword ecuHandle, dword objectID, dword bufferSize, char buffer[] );
```

## Description

The function copies a string value of an object in the object pool into a buffer. The object must exist in the object pool and support a string value.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object Identifier of the object
- **bufferSize**: Size of the string buffer
- **buffer**: String buffer in which the string is copied

## Return Values

- **≥ 0**: number of copied characters
- **< 0**: an error has occurred, see [error codes](../CAPLfunctionsISONLErrorCodes.md)
- **-1110**: Object ID does not exist
- **-1112**: String Value not supported

## Example

```plaintext
char buffer[100];
Iso11783OPGetStringValue( handle, 1000, elCount(buffer), buffer );
```
