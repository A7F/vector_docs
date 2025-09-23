# AvbSetProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AvbSetProperty(char propertyName[], int64 value); //form 1`
- `dword AvbSetProperty(dword objHandle, char propertyName[], int64 value); // form 2`
- `dword AvbSetProperty(dword objHandle, char propertyName[], dword length, byte value[]); // form 3`

## Description

The behavior of the AVB IL can be configured using properties. Properties can be set for the current bus context (form 1) as well as on an object-specific basis for talkers (form 2, 3). The default settings for the properties can be obtained from the table below.

## Parameters

- **propertyName**: Name of the property to be set.
  - **Current bus context**
    - **StreamReservation**: Default Value: 1. Stream Reservation is not supported. Set this property to 0.
  - **Listener/Talker**
    - **VlanId**: Default Value: 2. The VLAN ID to be used for sending or receiving AVB packets.
    - **RtpPort**: Default Value: 1024 (Listener), Dynamically chosen (Talker). Local client port = destination port of the stream (Listener). Local server port = source port of the stream (Talker) used for RTP via UDP. For talkers set the destination port of the stream by calling [AvbConnect](CAPLfunctionAvbConnect.md). RTP is always used in conjunction with RTCP. The RTCP UDP destination port number is one higher than the RTP port number.
  - **Listener**
    - **RtspAddress**: Default Value: Not set/0. Remote server address used for RT(S)P via TCP. If not set, no connection attempt to an RTSP server is made when AvbListen is called.
  - **Talker**
    - **FramesPerPacket**: Default Value: Deduced from SR class and frame rate (if possible). Constant number of frames per AVTPDU.
    - **VlanPriority**: Default Value: 2. The VLAN Priority to be used for sending AVB packets.
    - **PresentationTimeOffset**: Default Value: Deduced from SR class and frame rate (if possible). Presentation Time Offset in [ns]. The Presentation Time Offset is the time difference between the Presentation Time and the time the sample is handed over to the MAC's egress buffer as part of an AVB packet that is automatically filled with the corresponding Presentation Timestamp. This time must account for the Max Transit Time inherent to the SR class of the network as illustrated in IEEE 1722-2011, Figure 6 - AVTP Timing Reference Planes.
    - **RtpPayloadType**: Default Value: Automatically deduced from Media Type. The RTP Payload Type describes the media encoding of the RTP stream's payload samples. This parameter is automatically set according to the first entry defined in the mapping table in the [Options](../../../../CANoeCANalyzer/Ribbon/File/Options/BussystemsProtocols/BussystemsProtocolsEthernet.md) dialog for a specific media type. If a distinct type should be used set this property on the talker.
    - **MaxFuSize**: Default Value: 1464 (AVTP) / 64K (RTP). Sets the maximum size the lower fragmentation layer uses for transmitting sample data. Lowering this value does not limit the possible overall sample size (which is controlled by the protocol's own packetization mode, e. g. FU-A for RTP). If desired, for RTP the use of IP fragmentation can be omitted entirely by setting this property to a value that is smaller than the maximum payload size possible as of the TCP/IP stack's current MTU setting.

- **objHandle**: Handle of a talker or listener.

- **length**: Length of the value buffer passed.

- **value**: New value of the property.

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

```c
dword talkerHandle;

talkerHandle = AvbOpenTalker();
AvbSetProperty(talkerHandle, "FramesPerPacket", 64);
```

[See Also](javascript:void(0);)
