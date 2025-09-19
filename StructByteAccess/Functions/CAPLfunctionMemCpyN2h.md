[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/StructByteAccess/Functions/CAPLfunctionMemCpyN2h.md)

**CAPL Functions** » [Struct Byte Access](../CAPLfunctionsStructByteAccessOverview.md) » memcpy_n2h

# memcpy_n2h

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void memcpy_n2h(struct dest, byte source[]); // form 1`
- `void memcpy_n2h(struct dest, byte source[], int offset); // form 2`

## Description

Fills the struct with bytes from the array, and translates the byte order of the elements from big-endian to little-endian (n2h stands for "network to host").

## Parameters

- **source**: Array whose bytes shall be copied
- **dest**: Struct into which the bytes shall be copied
- **offset (form 2)**: Offset in the array where the data begins

## Return Values

—

## Example

See example [memcpy_h2n](CAPLfunctionMemCpyH2n.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
