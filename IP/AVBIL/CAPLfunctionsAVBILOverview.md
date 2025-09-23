[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/CAPLfunctionsAVBILOverview.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » AVB Interaction Layer

# AVB Interaction Layer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Ethernet**  
Only available with Option Ethernet.  
To use the CAPL functions the [AVB_IL.vmodule](../../../CANoeCANalyzer/Ethernet/ILAVB/ILAVBInclude.md) must be included.

**ON THIS PAGE:**

- [Callback Functions](#Callback)
- [Control Functions](#Control)
- [General Functions](#General)
- [Listener Functions](#Listener)
- [Listener/Talker Functions](#ListenerTalker)
- [Talker](#Talker)

## Callback Functions

- [OnAvbConnect](Functions/CAPLfunctionOnAvbConnect.md): Is dispatched when an asynchronous connection operation completes.
- [OnAvbListen](Functions/CAPLfunctionOnAvbListen.md): Is dispatched when a connection request for the specified Listener is received.
- [OnAvbReceive](Functions/CAPLfunctionOnAvbReceive.md): Is dispatched when an asynchronous receive operation on a Listener completes.
- [OnAvbSend](Functions/CAPLfunctionOnAvbSend.md): Is dispatched when an asynchronous send operation on a Talker completes.
- [OnAvbSendPrepare](Functions/CAPLfunctionOnAvbSendPrepare.md): Is called right before a packet will be sent by the AVB stack.
- [OnPtpSendPrepare](Functions/CAPLfunctionOnPtpSendPrepare.md): Is called right before a packet will be sent by the gPTP stack.

## Control Functions

- [AvbILControlInit](Functions/CAPLfunctionAvbILControlInit.md): Initialization of the AVB IL.
- [AvbILControlResume](Functions/CAPLfunctionAvbILControlResume.md): Resumes AVB/TSN automatic message sending behavior after a previous suspension.
- [AvbILControlStart](Functions/CAPLfunctionAvbILControlStart.md): Starts the AVB IL.
- [AvbILControlStop](Functions/CAPLfunctionAvbILControlStop.md): Stops the AVB IL.
- [AvbILControlWait](Functions/CAPLfunctionAvbILControlWait.md): Stops sending AVB/TSN related messages.

## General Functions

- [AvbGetLastError](Functions/CAPLfunctionAvbGetLastError.md): Checks whether the last called function of AVB IL has been successfully executed.
- [AvbGetLastErrorText](Functions/CAPLfunctionAvbGetLastErrorText.md): Retrieves the last error which occurs in the AVB IL as string.
- [AvbSetProperty](Functions/CAPLfunctionAvbSetProperty.md): Sets the properties to configure the behavior of the AVB IL.
- [AvbSetVerbosity](Functions/CAPLfunctionAvbSetVerbosity.md): Sets the verbosity level of AVB IL messages in the Write Window.
- [PtpSetPropery](Functions/CAPLfunctionPtpSetProperty.md): The behavior of the PTP layer can be configured using properties.
- [PtpSimulationTimespanFromPtpTimespan](Functions/CAPLfunctionPtpSimulationTimespanFromPtpTimespan.md): Returns the simulation timespan equivalent to the corresponding PTP timespan.
- [PtpTimeFromSimulationTime](Functions/CAPLfunctionPtpTimeFromSimulationTime.md): Returns the global PTP time corresponding to the simulation time.
- [PtpTimeNow](Functions/CAPLfunctionPtpTimeNow.md): Returns the current global PTP time.

## Listener Functions

- [AvbAccept](Functions/CAPLfunctionAvbAccept.md): Accepts an incoming connection request on the specified Listener resulting in a new Listener.
- [AvbCloseListener](Functions/CAPLfunctionAvbCloseListener.md): Closes the Listener.
- [AvbListen](Functions/CAPLfunctionAvbListen.md): Causes the Listener to listen for incoming connection requests.
- [AvbOpenListener](Functions/CAPLfunctionAvbOpenListener.md): Creates a Listener for use in connection-based, message-oriented communications.
- [AvbReceive](Functions/CAPLfunctionAvbReceive.md): Receives data into the specified buffer.

## Listener/Talker Functions

- [AvbGetMediaType](Functions/CAPLfunctionAvbGetMediaType.md): Gets the media type for a Listener or a Talker.
- [AvbGetProtocol](Functions/CAPLfunctionAvbGetProtocol.md): Retrieves the bit depth of an AAF sample in the stream received by the Listener or originated by the Talker.
- [AvbGetStreamId](Functions/CAPLfunctionAvbGetStreamId.md): Retrieves the Stream Identifier (ID) of the Listener or Talker.
- [AvbGetStreamSourceAddress](Functions/CAPLfunctionAvbGetStreamSourceAddress.md): Retrieves the stream’s Source Address of the Listener or Talker.
- [AvbGetStreamUniqueId](Functions/CAPLfunctionAvbGetStreamUniqueId.md): Retrieves the stream’s Unique Identifier (ID) of the Listener or Talker as part of the Stream Identifier (ID).

## Talker

- [AvbCloseTalker](Functions/CAPLfunctionAvbCloseTalker.md): Closes the Talker.
- [AvbConnect](Functions/CAPLfunctionAvbConnect.md): Establishes a connection with the specified location.
- [AvbOpenTalker](Functions/CAPLfunctionAvbOpenTalker.md): Creates a Talker for use in connection-based, message-oriented communications.
- [AvbSend](Functions/CAPLfunctionAvbSend.md): Receives data into the specified buffer.
- [AvbSetMediaType](Functions/CAPLfunctionAvbSetMediaType.md): Sets the media type for a Talker.
- [AvbSetProtocol](Functions/CAPLfunctionAvbSetProtocol.md): Sets the AVTP protocol of the Talker.

[Media API](../../Media/CAPLfunctionsMediaOverview.md)
