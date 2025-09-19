[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILSetNodeProperty.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_SetNodeProperty**

# GBT27930IL_SetNodeProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_SetNodeProperty( char propertyName[], long propertyValue); // form 1
long GBT27930IL_SetNodeProperty(dbNode node, char propertyName[], long propertyValue); // form 2
```

## Description

Changes an internal property of the node.

## Parameters

- **propertyName**: These properties influence the behavior of the simulated node in the ISO11783 Network - e.g. the transfer of the transport protocol or parts of **DeviceName**.

  - **BAM_DT_Interval**: Defines the interval time (in millisec) between each TP DT packet (for BAM transmitting).
    - **Value Range**: 1..3600000
    - **Initial Value**: 50 ms

  - **CTSLatency**: Defines the interval time (in millisec) between the TP.CM_RTS and TP.CM_CTS (for the receiver of the CMDT transmitting).
    - **Value Range**: 1..1249
    - **Initial Value**: 0 ms

  - **EoMALatency**: Defines the interval time (in millisec) between the last TP.DT and TP.CM_ EndOfMsgACK (for the receiver of the CMDT transmitting).
    - **Value Range**: 1..1249
    - **Initial Value**: 0 ms

  - **AbortLatency**: Defines delay (in millisec) for sending the TP.Conn_Abort message (for both the sender and the receiver of the CMDT transmission).
    - **Value Range**: 1..199
    - **Initial Value**: 0 ms

  - **TPDTLatency**: Defines delay (in millisec) when sending each TP.DT message (for the transmitter of the CMDT transmitting).
    - **Value Range**: 1..199
    - **Initial Value**: 0 ms

  - **Max_Transport_Size**: Maximum number of bytes, which can be transferred.
    - **Value Range**: 9..117440505
    - **Initial Value**: 100 MByte

  - **Packets_Per_CTS**: Number of packets, which are requested by CTS.
    - **Value Range**: 1..255
    - **Initial Value**: 16

  - **Packets_Per_RTS**: Number of packets, which is used with RTS.
    - **Value Range**: 1..255
    - **Initial Value**: 255

  - **Packets_Per_Sequence_Ex**: Number of packets, which are requested by ECTS (Extended TP).
    - **Value Range**: 1..255
    - **Initial Value**: 64

  - **BAM_with_Destination**: Target address, which is used for BAM.
    - **Value Range**: 0..1
    - **Initial Value**: 0
    - Options:
      - 0: Target address is 0xFF
      - 1: Specific target address is used

  - **Max_Number_Of_Requested_Retransmissions**: Maximal number of retransmission that the interaction layer supports. (Retransmission can be requested by the message TP.CM_CTS).
    - **Value Range**: 1..100000
    - **Initial Value**: 2

  - **TP_Priority**: Priority used by the transport protocol.
    - **Value Range**: 0..7
    - **Initial Value**: 7

- **propertyValue**: new value for the property

- **node**: Simulation node to apply the function

## Return Values

- **0**: property has been set successfully
- **< 0**: an error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
If(GBT27930IL_SetNodeProperty("BAM_DT_Interval", 100) < 0)
{
  write( "Can’t set node property 'BAM_DT_Interval' " );
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
