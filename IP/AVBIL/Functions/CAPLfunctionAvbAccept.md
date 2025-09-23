# AvbAccept

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbAccept(dword listenerHandle);
```

## Description

The function accepts an incoming connection request on the specified Listener resulting in a new Listener. If the operation fails, the function will return 0.

## Parameters

- **listenerHandle**: The Listener handle.

## Return Values

- **0**: The function failed. Call [AvbGetLastError](CAPLfunctionAvbGetLastError.md) to get a more specific error code.
- **>0**: New Listener handle.

## Example

—

See Also: [AvbAccept](#aanchor22228), [AvbCloseListener](CAPLfunctionAvbCloseListener.md#aanchor9009), [AvbCloseTalker](CAPLfunctionAvbCloseTalker.md#aanchor27562), [AvbConnect](CAPLfunctionAvbConnect.md#aanchor22984), [AvbGetLastError](CAPLfunctionAvbGetLastError.md#aanchor24787), [AvbGetLastErrorText](CAPLfunctionAvbGetLastErrorText.md#aanchor31644), [AvbGetMediaType](CAPLfunctionAvbGetMediaType.md#aanchor17888), [AvbGetProtocol](CAPLfunctionAvbGetProtocol.md#aanchor12285), [AvbGetStreamId](CAPLfunctionAvbGetStreamId.md#aanchor4409), [AvbGetStreamSourceAddress](CAPLfunctionAvbGetStreamSourceAddress.md#aanchor2859), [AvbGetStreamUniqueId](CAPLfunctionAvbGetStreamUniqueId.md#aanchor28540), [AvbILControlInit](CAPLfunctionAvbILControlInit.md#aanchor11839), [AvbILControlResume](CAPLfunctionAvbILControlResume.md#aanchor16416), [AvbILControlStart](CAPLfunctionAvbILControlStart.md#aanchor25444), [AvbILControlStop](CAPLfunctionAvbILControlStop.md#aanchor13937), [AvbILControlWait](CAPLfunctionAvbILControlWait.md#aanchor492), [AvbListen](CAPLfunctionAvbListen.md#aanchor8040), [AvbOpenListener](CAPLfunctionAvbOpenListener.md#aanchor19250), [AvbOpenTalker](CAPLfunctionAvbOpenTalker.md#aanchor10413), [AvbReceive](CAPLfunctionAvbReceive.md#aanchor27805), [AvbSend](CAPLfunctionAvbSend.md#aanchor11678), [AvbSetMediaType](CAPLfunctionAvbSetMediaType.md#aanchor25463), [AvbSetProperty](CAPLfunctionAvbSetProperty.md#aanchor27483), [AvbSetProtocol](CAPLfunctionAvbSetProtocol.md#aanchor31474), [AvbSetVerbosity](CAPLfunctionAvbSetVerbosity.md#aanchor30291), [OnAvbConnect](CAPLfunctionOnAvbConnect.md#aanchor16657), [OnAvbListen](CAPLfunctionOnAvbListen.md#aanchor7020), [OnAvbReceive](CAPLfunctionOnAvbReceive.md#aanchor13825), [OnAvbSend](CAPLfunctionOnAvbSend.md#aanchor5527), [OnAvbSendPrepare](CAPLfunctionOnAvbSendPrepare.md#aanchor27027), [OnPtpSendPrepare](CAPLfunctionOnPtpSendPrepare.md#aanchor25380), [PtpSetProperty](CAPLfunctionPtpSetProperty.md#aanchor19121), [PtpSimulationTimespanFromPtpTimespan](CAPLfunctionPtpSimulationTimespanFromPtpTimespan.md#aanchor15759), [PtpTimeFromSimulationTime](CAPLfunctionPtpTimeFromSimulationTime.md#aanchor10767), [PtpTimeNow](CAPLfunctionPtpTimeNow.md#aanchor20173)
