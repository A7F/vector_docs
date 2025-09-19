# coTfsArrToD

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword coTfsArrToD( byte inByteArray[], dword arraysize );
```

## Description

The function converts the content of a byte array into a dword value.

## Parameters

- **inByteArray[]**: Array containing the bytes to be converted, recommended array size: 4 byte.
- **arraysize**: Size of the array.

## Return Values

Converted value or 0 if parameters are invalid.

## Example

```c
/* converts data from a byte array to a dword */
Byte inDataArr[4] = {4,3,2,1};
Dword outValue;

outValue = coTfsArrToD(inDataArr, 4);
```
