# coTfsArrToW

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
word coTfsArrToW( byte inByteArray[], dword arraysize );
```

## Description

The function converts the content of a byte array into a word value.

## Parameters

- **inByteArray[]**: Array containing the bytes to be converted, recommended array size: 2 byte.
- **arraysize**: Size of the array.

## Return Values

Converted value or 0 if parameters are invalid.

## Example

```c
/* converts a data from a byte array to a word */
Byte inDataArr[2] = {2,1};
Word outValue;

outValue = coTfsArrToW(inDataArr, 2);
```
