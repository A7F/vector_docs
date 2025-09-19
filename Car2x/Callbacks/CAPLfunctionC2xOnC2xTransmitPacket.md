# `<OnC2xTransmitPacket>` (Callback)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
This callback must be implemented in the CAPL program by the user to use the function [C2xRegisterCallback](../Functions/CAPLfunctionC2xRegisterCallback.md) for Pre Transmit Indications.

## Function Syntax

```plaintext
void <OnC2xTransmitPacket>(long packet); // form 1
long <OnC2xTransmitPacket>(long packet); // form 2
```

## Description

This callback is invoked before a [database defined](../../../CANoeCANalyzer/Car2x/windows/NetworkExplorer/NetworkExplorerSignalSending.md) packet is transmitted (by this network node).

Within this callback the Token functions from the [Packet API](../CAPLfunctionsCar2xOverview.md#PacketAPI) and all Signal functions from the [Car2x IL API](../CAPLfunctionsCar2xOverview.md#SignalAPI) can be used.

Modifications are persistent between invocations of the callback.

When using the form 2 of the callback it is possible to skip the current transmission by returning a 0.

## Parameters

- **packet**: Handle of the packet

## Return Values

Form 1

- **0**: don’t transmit the message
- **1**: transmit the message

## Example

```plaintext
on start
{
  C2xRegisterCallback(1, "OnTxBSM", "BasicSafetyMessage");
}
void OnTxBSM(LONG packet)
{
// do something here
}
```
