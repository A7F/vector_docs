[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILSetNodeProperty.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_SetNodeProperty

# Iso11783IL_SetNodeProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_SetNodeProperty( char propertyName[], long propertyValue); // form 1
long Iso11783IL_SetNodeProperty( dbNode node, char propertyName[], long propertyValue); // form 2
```

## Description

Changes an internal property of the node.

## Parameters

- **propertyName**: These properties influence the behavior of the simulated node in the ISO11783 Network - e.g. the transfer of the transport protocol or parts of **DeviceName**.

  - **FP_Interval**: Defines delay (im ms) when sending each FP packet (for Fast Packet transmitting).
    - Value Range: 0..3600000
    - Initial Value: 0 ms

  - **BAM_DT_Interval**: Defines the interval time (in ms) between each TP DT packet (for BAM transmitting).
    - Value Range: 1..3600000
    - Initial Value: 50 ms

  - **FD_BAM_Interval**: CAN FD only: Defines the interval time (in ms) between each TP DT packet and the final TP.CM_EndOfMsgStatus (for FD BAM transmitting).
    - Value Range: 1..3600000
    - Initial Value: 10 ms

  - **CTSLatency**: Defines the interval time (in ms) between the TP.CM_RTS resp. FD.TP.CM_RTS resp. FD.TP.CM_RTS and TP.CM_CTS resp. FD.CM_CTS resp. FD.CM_CTS (for the receiver of the CMDT transmitting).
    - Value Range: 1..3600000
    - Initial Value: 0 ms

  - **EoMALatency**: Defines the interval time (in ms) between the last TP.DT resp. FD.TP.CM_EndOfMsgStatus for CAN FD and TP.CM_ EndOfMsgACK (for the receiver of the CMDT transmitting).
    - Value Range: 1..3600000
    - Initial Value: 0 ms

  - **AbortLatency**: Defines delay (in ms) for sending the TP.Conn_Abort resp. FD.TP.Conn_Abort message (for both the sender and the receiver of the CMDT transmission).
    - Value Range: 1..3600000
    - Initial Value: 0 ms

  - **TPDTLatency**: Defines delay (in ms) when sending each TP.DT resp. FD.TP.DT message (for the transmitter of the CMDT transmitting).
    - Value Range: 1..3600000
    - Initial Value: 0 ms

  - **EoMSLatency**: CAN FD only: Defines the interval time (in ms) between the last FD.TP.DT and FD.TP.CM_ EndOfMsgStatus (for the sender of the CMDT transmitting). Does not affect FD BAM transmissions.
    - Value Range: 1..3600000
    - Initial Value: 0 ms

  - **Max_Transport_Size**: Maximum number of bytes, which can be transferred.
    - Value Range: 9..117440505
    - Initial Value: 100 MByte

  - **Packets_Per_CTS**: Number of packets, which are requested by CTS.
    - Value Range: 1..255
    - Initial Value: 16

  - **Packets_Per_RTS**: Number of packets, which is used with RTS.
    - Value Range: 1..255
    - Initial Value: 255

  - **Packets_Per_Sequence_Ex**: Number of packets, which are requested by ECTS (Extended TP).
    - Value Range: 1..255
    - Initial Value: 64

  - **BAM_with_Destination**: Target address, which is used for BAM.
    - 0: Target address is 0xFF
    - 1: Specific target address is used
    - Value Range: 0..1
    - Initial Value: 0

  - **Max_Number_Of_Requested_Retransmissions**: Maximal number of retransmission that the interaction layer supports. (Retransmission can be requested by the message TP.CM_CTS).
    - Value Range: 1..100000
    - Initial Value: 2

  - **TP_Priority**: Priority used by the transport protocol.
    - Value Range: 0..7
    - Initial Value: 7

  - **AAC**: **Arbitrary Address Capable** field of J1939 NAME
    - Value Range: 0..1
    - Initial Value: Content of the database node attribute **NmJ1939AAC**

  - **IndustryGroup**: **Industry Group** field of J1939 NAME
    - Value Range: 0..7
    - Initial Value: Content of the database node attribute **NmJ1939IndustryGroup**

  - **VehicleSystemInstance**: **Vehicle System Instance** field of J1939 NAME
    - Value Range: 0..15
    - Initial Value: Content of the database node attribute **NmJ1939SystemInstance**

  - **VehicleSystem**: **Vehicle System** field of J1939 NAME
    - Value Range: 0..127
    - Initial Value: Content of the database node attribute **NmJ1939System**

  - **Function**: **Function** field of J1939 NAME
    - Value Range: 0..255
    - Initial Value: Content of the database node attribute **NmJ1939Function**

  - **FunctionInstance**: **Function Instance** field of J1939 NAME
    - Value Range: 0..31
    - Initial Value: Content of the database node attribute **NmJ1939FunctionInstance**

  - **ECUInstance**: **ECU Instance** field of J1939 NAME
    - Value Range: 0..7
    - Initial Value: Content of the database node attribute **NmJ1939ECUInstance**

  - **ManufacturerCode**: **Manufacturer Code** field of J1939 NAME
    - Value Range: 0..2047
    - Initial Value: Content of the database node attribute **NmJ1939ManufacturerCode**

  - **IdentityNumber**: **Identity Number** field of J1939 NAME
    - Value Range: 0..2097151
    - Initial Value: Content of the database node attribute **NmJ1939IdentityNumber**

  - **AddressClaimSupport**: **Type of [Address Claim support](../../../../Shared/ISO11783/J1939andISO11783NMil.md)**
    - 0: No Address Claim support
    - 1: Basic Address Claim support
    - 2: Extended Address Claim support
    - Value Range: 0..2
    - Initial Value: 0

- **propertyValue**: New value for the property

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
if (Iso11783IL_SetNodeProperty("BAM_DT_Interval", 100) < 0)
{
  write( "Can’t set node property 'BAM_DT_Interval' " );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
