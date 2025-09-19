# ARILCalculateCRC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The function can only be called for PDUs that are potentially sent by this IL instance. (PDUs that are sent from the node, the IL is assigned to).

## Function Syntax

```
long ARILCalculateCRC (char aMsgName[], cahr sigGroupName[], BYTE payload[], dword aPayloadLength, dword crc[]);
```

## Description

Calculates the CRC of the PDU according to the given payload.

## Parameters

- **aMsgName**: The symbolic name of a PDU in the database.
- **sigGroupName**: Full name of the designated signal group.
- **payload**: Byte array with the full payload of the PDU.
- **aPayloadLength**: The length of the payload buffer.
- **crc**: Returns the calculated CRC value.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—
