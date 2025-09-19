# C2xRegisterCallback

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xRegisterCallback(long callbackType, char* callbackFunction);
long C2xRegisterCallback(long callbackType, char* callbackFunction, char* dbMessage);
```

## Description

Register a callback function.

The callback can be registered for all or for a specific message. If the dbMessage parameter is present, the function can be called earliest in the On Start event handler. With multiple calls of this function it is possible to register several callback functions for the same message or to register the same callback function for several messages.

## Parameters

- **callbackType**
  - 0: Register a [Receive Indication](../Callbacks/CAPLfunctionC2xOnC2xPacket.md) callback
  - 1: Register a [Pre Transmit Indication](../Callbacks/CAPLfunctionC2xOnC2xTransmitPacket.md) callback

- **dbMessage**
  - Name of a database message for which the callback is invoked.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
on start
{
  enum CallbackType { OnRx, PreTx };
  C2xRegisterCallback(OnRx,  "OnRxCAM", "CAM" );
  C2xRegisterCallback(PreTx, "OnPreTxDENM", "DENM" );
}

// Callback function on receiving CAM message
void OnRxCAM(long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet)
{

}

// Callback function before sending DENM message
void OnPreTxDENM(LONG packet)
{

}
```

