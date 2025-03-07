[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsWToArr.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsWToArr**

# coTfsWToArr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsWToArr( word wordValue, byte outByteArray[], dword arraysize );
```

## Description

The function converts a word value into a byte array.

## Parameters

- **wordValue**: Value to be converted.
- **outByteArray[]**: Array containing the converted value, recommended array size: 2 byte.
- **arraysize**: Size of the byte array.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
/* converts a word value to a byte array */
Word inValue = 2345;
Byte outDataArr[2];

if (coTfsWToArr(inValue, outDataArr, 2) != 1)
{
  /* conversion failed */
} /* if */
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)