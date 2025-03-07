[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsDToArr.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsDToArr**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)