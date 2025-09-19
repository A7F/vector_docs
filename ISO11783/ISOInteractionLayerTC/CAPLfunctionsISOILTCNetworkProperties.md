[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/CAPLfunctionsISOILTCNetworkProperties.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **ISO11783 TC IL Network Properties**

# ISO11783 TC IL Network Properties

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

These properties influence the behavior of the simulated node in the ISO11783 Network - e.g. the transfer of the transport protocol or parts of **DeviceName**.

- **FP_Interval**
  - Description: Defines delay (im ms) when sending each FP packet (for Fast Packet transmitting).
  - Value Range: 0..3600000
  - Initial Value: 0 ms

- **BAM_DT_Interval**
  - Description: Defines the interval time (in ms) between each TP DT packet (for BAM transmitting).
  - Value Range: 1..3600000
  - Initial Value: 50 ms

- **FD_BAM_Interval**
  - Description: CAN FD only: Defines the interval time (in ms) between each TP DT packet and the final TP.CM_EndOfMsgStatus (for FD BAM transmitting).
  - Value Range: 1..3600000
  - Initial Value: 10 ms

- **CTSLatency**
  - Description: Defines the interval time (in ms) between the TP.CM_RTS resp. FD.TP.CM_RTS resp. FD.TP.CM_RTS and TP.CM_CTS resp. FD.CM_CTS resp. FD.CM_CTS (for the receiver of the CMDT transmitting).
  - Value Range: 1..3600000
  - Initial Value: 0 ms

- **EoMALatency**
  - Description: Defines the interval time (in ms) between the last TP.DT resp. FD.TP.CM_EndOfMsgStatus for CAN FD and TP.CM_ EndOfMsgACK (for the receiver of the CMDT transmitting).
  - Value Range: 1..3600000
  - Initial Value: 0 ms

- **AbortLatency**
  - Description: Defines delay (in ms) for sending the TP.Conn_Abort resp. FD.TP.Conn_Abort message (for both the sender and the receiver of the CMDT transmission).
  - Value Range: 1..3600000
  - Initial Value: 0 ms

- **TPDTLatency**
  - Description: Defines delay (in ms) when sending each TP.DT resp. FD.TP.DT message (for the transmitter of the CMDT transmitting).
  - Value Range: 1..3600000
  - Initial Value: 0 ms

- **EoMSLatency**
  - Description: CAN FD only: Defines the interval time (in ms) between the last FD.TP.DT and FD.TP.CM_ EndOfMsgStatus (for the sender of the CMDT transmitting). Does not affect FD BAM transmissions.
  - Value Range: 1..3600000
  - Initial Value: 0 ms

- **Max_Transport_Size**
  - Description: Maximum number of bytes, which can be transferred.
  - Value Range: 9..117440505
  - Initial Value: 100 MByte

- **Packets_Per_CTS**
  - Description: Number of packets, which are requested by CTS.
  - Value Range: 1..255
  - Initial Value: 16

- **Packets_Per_RTS**
  - Description: Number of packets, which is used with RTS.
  - Value Range: 1..255
  - Initial Value: 255

- **Packets_Per_Sequence_Ex**
  - Description: Number of packets, which are requested by ECTS (Extended TP).
  - Value Range: 1..255
  - Initial Value: 64

- **BAM_with_Destination**
  - Description: Target address, which is used for BAM.
    - 0: Target address is 0xFF
    - 1: Specific target address is used
  - Value Range: 0..1
  - Initial Value: 0

- **Max_Number_Of_Requested_Retransmissions**
  - Description: Maximal number of retransmission that the interaction layer supports. (Retransmission can be requested by the message TP.CM_CTS).
  - Value Range: 1..100000
  - Initial Value: 2

- **TP_Priority**
  - Description: Priority used by the transport protocol.
  - Value Range: 0..7
  - Initial Value: 7

- **AAC**
  - Description: **Arbitrary Address Capable** field of J1939 NAME
  - Value Range: 0..1
  - Initial Value: Content of the database node attribute **NmJ1939AAC**

- **IndustryGroup**
  - Description: **Industry Group** field of J1939 NAME
  - Value Range: 0..7
  - Initial Value: Content of the database node attribute **NmJ1939IndustryGroup**

- **VehicleSystemInstance**
  - Description: **Vehicle System Instance** field of J1939 NAME
  - Value Range: 0..15
  - Initial Value: Content of the database node attribute **NmJ1939SystemInstance**

- **VehicleSystem**
  - Description: **Vehicle System** field of J1939 NAME
  - Value Range: 0..127
  - Initial Value: Content of the database node attribute **NmJ1939System**

- **Function**
  - Description: **Function** field of J1939 NAME
  - Value Range: 0..255
  - Initial Value: Content of the database node attribute **NmJ1939Function**

- **FunctionInstance**
  - Description: **Function Instance** field of J1939 NAME
  - Value Range: 0..31
  - Initial Value: Content of the database node attribute **NmJ1939FunctionInstance**

- **ECUInstance**
  - Description: **ECU Instance** field of J1939 NAME
  - Value Range: 0..7
  - Initial Value: Content of the database node attribute **NmJ1939ECUInstance**

- **ManufacturerCode**
  - Description: **Manufacturer Code** field of J1939 NAME
  - Value Range: 0..2047
  - Initial Value: Content of the database node attribute **NmJ1939ManufacturerCode**

- **IdentityNumber**
  - Description: **Identity Number** field of J1939 NAME
  - Value Range: 0..2097151
  - Initial Value: Content of the database node attribute **NmJ1939IdentityNumber**

- **AddressClaimSupport**
  - Description: **Type of [Address Claim support](../../../Shared/ISO11783/J1939andISO11783NMil.md)**
    - 0: No Address Claim support
    - 1: Basic Address Claim support
    - 2: Extended Address Claim support
  - Value Range: 0..2
  - Initial Value: 0

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
