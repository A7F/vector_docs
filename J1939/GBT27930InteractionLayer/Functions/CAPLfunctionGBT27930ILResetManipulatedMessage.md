[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILResetManipulatedMessage.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_ResetManipulatedMessage**

# GBT27930IL_ResetManipulatedMessage

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_ResetManipulatedMessage( dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 1
long GBT27930IL_ResetManipulatedMessage( dbNode node, dword pgn, dword destinationAddress, qword filterMask, qword filterValue ); // form 2
```

## Description

Resets the change of a single [GBT27930IL_ManipulateMessage](CAPLfunctionGBT27930ILManipulateMessage.md) call. The corresponding message is specified by PGN, destination address and a part of the first eight data bytes.

## Parameters

- **pgn**: Use same value as in `GBT27930IL_ManipulateMessage` to stop manipulation of the message.
- **destinationAddress**: Use same value as in `GBT27930IL_ManipulateMessage` to stop manipulation of the message.
- **filterMask**: Use same value as in `GBT27930IL_ManipulateMessage` to stop manipulation of the message.
- **filterValue**: Use same value as in `GBT27930IL_ManipulateMessage` to stop manipulation of the message.
- **node**: Simulation node to apply the function.

## Return Values

- **-1**: There is no matching entry made by `GBT27930IL_ManipulateMessage`
- **-102**: An invalid parameter is used

## Example

See example of [GBT27930IL_ManipulateMessage](CAPLfunctionGBT27930ILManipulateMessage.md).

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)