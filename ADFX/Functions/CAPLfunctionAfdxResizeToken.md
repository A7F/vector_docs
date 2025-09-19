# AfdxResizeToken

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxResizeToken( long packet, char protocolDesignator[], char tokenDesignator[], long newBitLength );
```

## Description

This function sets the length of a token. It can only be used with resizable tokens ("header" and "data"). If a token is not resizable, the error code 46-0125 is returned. The main purpose is to create AFDX messages with or without a sequence number field.

Calling the function with (n = number of bytes):

- `protocolDesignator` = "afdx"
- `tokenDesignator` = "data"
- `newBitLength` = n*8

Results in a "data" field size of n bytes. Additionally, the sequence number field is located after the data field.

Calling the function with (n = number of bytes):

- `protocolDesignator` = "udp"
- `tokenDesignator` = "data"
- `newBitLength` = n*8

Again results in a "data" field size of n bytes. In this case, there is no sequence number field considered.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g., "afdx" or "udp".
- **tokenDesignator**: Name of the token, e.g., "data".
- **newBitLength**: New length of the token in bits.

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```plaintext
long packet;
long packetlen = 60;

packet = AfdxInitPacket(0x0a022600, 0xe0e01a0f, 11121, 0x1a0f, 640);
packetlen = sysGetVariableLong("%NODE_NAME%", "OutputPacketLength");

// adapt frame size with an additional seqNo byte
AfdxResizeToken(packet, "afdx", "data", packetlen*8);
AfdxCompletePacket(packet);
AfdxOutputPacket(packet);
AfdxReleasePacket(packet);
```
