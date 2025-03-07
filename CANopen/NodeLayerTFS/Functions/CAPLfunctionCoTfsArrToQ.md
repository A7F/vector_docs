[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsArrToQ.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsArrToQ

# coTfsArrToQ

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

`qword coTfsArrToQ( byte inByteArray[], dword arraysize );`

## Description

The function converts the content of a byte array into a qword value.

## Parameters

- **inByteArray[]**: Array containing the bytes to be converted, recommended array size: 8 byte.
- **arraysize**: Size of the array.

## Return Values

Converted value or 0 if parameters are invalid.

## Example

```c
/* converts data from a byte array to a qword */
Byte inDataArr[8] = {8,7,6,5,4,3,2,1};
qword outValue;

outValue = coTfsArrToQ(inDataArr, 8);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)