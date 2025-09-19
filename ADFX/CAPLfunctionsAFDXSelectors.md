# AFDX Selectors

**Valid for**: CANoe DE • CANoe4SW DE

## Note

For programming examples, refer to the help pages:

- [Declaration of AFDX Frames](../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXframe.md)
- [Declaration of AFDX Messages](../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXmessage.md)

More information about [A664Messages Versus A664Frames](../../CANoeCANalyzer/AFDX/capl/afdxA664MessagesVSA664Frames.md).

## Quick Access

- [Selectors for Identification and Timing](#SelectorsIdentificationTiming)
- [Selectors on Ethernet level](#SelectorsEthernetLevel)
- [Selectors on IP level](#SelectorsIPLevel)
- [Selectors on UDP level](#SelectorsUDPLevel)
- [Selectors on AFDX level](#SelectorsAFDXLevel)

## Selectors for Identification and Timing

| Keyword   | Description                                                                                                                | a664 Frame | a664 Message | Type   | Access Limitations |
|-----------|----------------------------------------------------------------------------------------------------------------------------|------------|--------------|--------|---------------------|
| BAG       | Bandwidth allocation GAP. Unit: milliseconds. Value range: 1 …128 (initialization value).                                   | x          | x            | byte   | [read-only](#Read-Only)<sup>3</sup> |
| Data      | Complete raw content of the object. Value range: Initialized with 0.                                                        | x          | x            | byte[] | read-only           |
| DIR       | Direction related to the corresponding event. Value range: Rx = 0 (default), Tx = 1.                                       | x          | x            | byte   | read-only           |
| Distance  | Measured timely distance between two AFDX messages on the same virtual link (VL). Unit: microseconds.                       | x          | x            | word   | read-only           |
| ErrFlag   | Error details for the received message. Value range: see [table below](#ErrFlag).                                           | x          | x            | dword  | read-only           |
| ID        | The message ID is derived from the address information.                                                                     | x          | x            | word   | -                   |
| Length    | Length of the message object in bytes. Unit: bytes. Value range: 60 … 8192 + 42 + 1.                                        | x          | x            | word   | read-only           |
| msgChannel| Transmission channel (output) or the channel which triggered an event handler. Value range: 1..16.                          | x          | x            | word   | -                   |
| name      | Message name from an assigned database (DBC). Value range: \0 or valid name.                                                | x          | x            | char[] | read-only           |
| SIMULATED | Specifies whether the event was caused by your CANoe DE product or not. Value range: 0 (real event), 1 (simulated event).   | x          | x            | byte   | read-only           |
| SkewMax   | Maximum timely difference between a transmission on line A and B. Unit: microseconds. Value range: 0 … 65635.               | x          | x            | dword  | [read-only](#Read-Only)<sup>3</sup> |
| time      | Time stamp of the event. Unit: 10 µs.                                                                                       | x          | x            | dword  | read-only           |
| time_ns   | Time stamp of the event. Unit: nanoseconds.                                                                                 | x          | x            | int64  | read-only           |
| TxCycle   | Transmission cycle of an AFDX message. Unit: Milliseconds.                                                                  |            | x            | dword  | -                   |

### Value Range ErrFlag

| Bit | Value     | Meaning                                                                                                           |
|-----|-----------|-------------------------------------------------------------------------------------------------------------------|
| 0   | 1 (0x0001)| Frame was received on line B (line information).                                                                  |
| 1   | 1 (0x0002)| Frame is redundant; redundancy manager detected a valid redundancy condition.                                     |
| 2   | 1 (0x0004)| Frame is an IP FRAGMENT.                                                                                          |
| 3   | 1 (0x0008)| Frame belongs to a service access point (SAP) connection.                                                         |
| 4   | 1 (0x0010)| Frame received on wrong line; receive line collides with MAC source address.                                      |
| 5   | 1 (0x0020)| Frame is not a valid [AFDX frame](../../CANoeCANalyzer/AFDX/protocols/afdxProtocolAfdx.md#validAfdxFrame).       |
| 6   | 1 (0x0040)| A wrong sequence number was received.                                                                             |
| 7   | 1 (0x0080)| Redundancy error encountered; either a frame was lost or the time for Skew Max was exceeded.                      |
| 8   | 1 (0x0100)| Fragmentation / reassembly error; typically a fragment is missing or misordered.                                  |
| 9   | 1 (0x0200)| Protocol decoding error detected (error on IP, UDP or SNMP level).                                                |
| 10  | 1 (0x0400)| This is a reassembled packet (message).                                                                           |
| 11  | 1 (0x0800)| Frame was checked by redundancy management.                                                                       |
| 12  | 1 (0x1000)| A constant or value violates the AFDX recommendation.                                                             |
| 13  | 1 (0x2000)| Frame size does not match expected size as defined in database.                                                   |
| 14  | 1 (0x4000)| Packet is unknown (not defined in the database).                                                                  |
| 15  | 1 (0x8000)| Frame was checked by integrity management.                                                                        |

## Selectors on Ethernet Level

| Keyword       | Description                                                                                      | a664 Frame | a664 Message | Type     | Access Limitations |
|---------------|--------------------------------------------------------------------------------------------------|------------|--------------|----------|---------------------|
| AfdxSeqNr     | AFDX sequence number.                                                                            | x          | x            | byte     | read-only           |
| EthAdrDst     | Destination MAC address. Constructed from EthAdrDstConst and EthVlId.                            | x          | x            | byte[6]  | [read-only](#Read-Only)<sup>1</sup> |
| EthAdrDstConst| Constant part of destination MAC address.                                                        | x          | x            | dword    | -                   |
| EthAdrSrc     | Source MAC address. Created from EthAdrSrcConst and IpAdrSrc.                                    | x          | x            | byte[6]  | [read-only](#Read-Only)<sup>1</sup> |
| EthAdrSrcConst| Constant part of destination MAC address.                                                        | x          | x            | byte[3]  | -                   |
| EthUserId     | Identifies a specific address part of the source MAC address.                                    | x          | x            | word     | -                   |
| EthVlId       | AFDX Virtual Link Identifier.                                                                    | x          | x            | word     | [read-only](#Read-Only)<sup>1</sup> |

## Selectors on IP Level

| Keyword       | Description                                                                                      | a664 Frame | a664 Message | Type     | Access Limitations |
|---------------|--------------------------------------------------------------------------------------------------|------------|--------------|----------|---------------------|
| IpLength      | Length of an IP frame including 20 bytes of header information.                                  | x          | x            | word     | [read-only](#Read-Only)<sup>2</sup> |
| IpAdrDst      | IP destination address.                                                                          | x          | x            | dword    | [read-only](#Read-Only)<sup>5</sup> |
| IpAdrSrc      | IP source address.                                                                               | x          | x            | dword    | [read-only](#Read-Only)<sup>5</sup> |
| IpFragAllowed | Set the fragmentation attribute for messages to be transmitted over a VL.                        | x          | x            | byte     | [read-only](#Read-Only)<sup>4</sup> |
| IpPayload     | IP payload area. Limited by IpLength.                                                            | x          |              | byte[]   | -                   |
| IpProtocol    | Value of IP protocol field.                                                                      | x          |              | byte     | -                   |
| IpFragOffset  | Fragmentation offset.                                                                            | x          |              | word     | -                   |
| IpIsFragment  | Fragmentation attribute of frame.                                                                | x          |              | word     | -                   |

## Selectors on UDP Level

| Keyword    | Description                                                                                      | a664 Frame | a664 Message | Type   | Access Limitations |
|------------|--------------------------------------------------------------------------------------------------|------------|--------------|--------|---------------------|
| UdpDstPort | UDP destination Port.                                                                            | x          | x            | word   | [read-only](#Read-Only)<sup>1</sup> |
| UdpLength  | Length of the UDP payload (AfdxLength + 8).                                                      | x          | x            | word   | [read-only](#Read-Only)<sup>2</sup> |
| UdpSrcPort | UDP Source Port.                                                                                 | x          | x            | word   | [read-only](#Read-Only)<sup>1</sup> |

## Selectors on AFDX Level

| Keyword      | Description                                                                                      | a664 Frame | a664 Message | Type   | Access Limitations |
|--------------|--------------------------------------------------------------------------------------------------|------------|--------------|--------|---------------------|
| AfdxPayload  | Payload area of AFDX message.                                                                    | x          | x            | byte[] | -                   |
| AfdxLength   | Length of the AFDX payload.                                                                      | x          | x            | word   | [read-only](#Read-Only)<sup>2</sup> |
| IntChk       | Integrity check for VL.                                                                          | x          | x            | byte   | [read-only](#Read-Only)<sup>3</sup> |
| RMA          | Redundancy management.                                                                           | x          | x            | byte   | [read-only](#Read-Only)<sup>3</sup> |
| LineSelect   | Determine the used line A and/or B.                                                              | x          | x            | byte   | [read-only](#Read-Only)<sup>3</sup> |
| MaxFrameSize | Define the maximum frame size for a VL.                                                          | x          | x            | dword  | [read-only](#Read-Only)<sup>3</sup> |
| SubVLNr      | Sub VL number range.                                                                             | x          | x            | byte   | [read-only](#Read-Only)<sup>3</sup> |
| SubVLid      | Used sub VL identifier.                                                                          | x          | x            | byte   | [read-only](#Read-Only)<sup>6</sup> |

### Read-Only Notes

- **read-only<sup>1</sup>** - The value may be modified with the function [A664InitMessage](Functions/CAPLfunctionA664InitMessage.md).
- **read-only<sup>2</sup>** - The value may be modified with the function [A664InitMessage](Functions/CAPLfunctionA664InitMessage.md) or [A664ResizeMessage](Functions/CAPLfunctionA664ResizeMessage.md).
- **read-only<sup>3</sup>** - The value may be modified with the function [A664VLConfig](Functions/CAPLfunctionA664VLConfig.md).
- **read-only<sup>4</sup>** - The value may be modified with the function [A664VLConfig](Functions/CAPLfunctionA664VLConfig.md) or [A664MsgConfig](Functions/CAPLfunctionA664MsgConfig.md).
- **read-only<sup>5</sup>** - The value may be modified with the function [A664InitMessage](Functions/CAPLfunctionA664InitMessage.md) or [A664InitICMP](Functions/CAPLfunctionA664InitICMP.md).
- **read-only<sup>6</sup>** - The value may be modified with the function [A664MsgConfig](Functions/CAPLfunctionA664MsgConfig.md).
