# coTfsDToArr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
long coTfsDToArr( dword dwordValue, byte outByteArray[], dword arraysize );
```

## Description

The function converts a dword value into a byte array.

## Parameters

- **dwordValue**: Value to be converted.
- **outByteArray[]**: Array containing the converted value, recommended array size: 4 byte.
- **arraysize**: Size of the byte array.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
/* converts a dword value to a byte array */
Dword inValue = 234567;
Byte outDataArr[4];

if (coTfsDToArr(inValue, outDataArr, 4) != 1)
{
  /* conversion failed */
} /* if */
```
