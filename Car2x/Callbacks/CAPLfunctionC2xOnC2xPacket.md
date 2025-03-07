[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Callbacks/CAPLfunctionC2xOnC2xPacket.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » `<OnC2xPacket>`

# `<OnC2xPacket>` (Callback)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This callback must be implemented in the CAPL program by the user to use the function [C2xReceivePacket](../Functions/CAPLfunctionC2xReceivePacket.md) or the function [C2xRegisterCallback](../Functions/CAPLfunctionC2xRegisterCallback.md) for Receive Indications.

## Function Syntax

```plaintext
void <OnC2xPacket>( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet );
```

## Description

This callback is called when a registered WLAN packet is received.

Within this callback the following functions can be used to retrieve the received packet data:

- [C2xGetThisData](../Functions/CAPLfunctionC2xGetThisData.md)
- [C2xGetThisTimeNS](../Functions/CAPLfunctionC2xGetThisTimeNS.md)
- [C2xGetThisValue8](../Functions/CAPLfunctionC2xGetThisValue8.md)
- [C2xGetThisValue16](../Functions/CAPLfunctionC2xGetThisValue16.md)
- [C2xGetThisValue32](../Functions/CAPLfunctionC2xGetThisValue32.md)
- [C2xGetThisValue64](../Functions/CAPLfunctionC2xGetThisValue64.md)
- [C2xGetThisMotorolaValue16](../Functions/CAPLfunctionC2xGetThisMotorolaValue16.md)
- [C2xGetThisMotorolaValue32](../Functions/CAPLfunctionC2xGetThisMotorolaValue32.md)
- [C2xGetThisMotorolaValue64](../Functions/CAPLfunctionC2xGetThisMotorolaValue64.md)

These functions access the payload of the highest interpretable protocol. Offset 0 starts at the beginning of the payload.

## Parameters

- **channel**: WLAN channel on which the packet was received
- **dir**: Direction of the packet
  - 0: Rx
  - 1: Tx
- **radioChannel**: Radio channel, i.e. 176 or 180
- **signalStrength**: Signal strength of the received packet in [dBm]
- **signalQuality**: Signal quality of the received packet
- **packet**: Handle of the received packet

## Return Values

—

## Example

**Node System - PreStart in CAPL Browser**

```plaintext
on preStart
{
  C2xReceivePacket( "OnC2xPacket");
}
```

**Node Callback Function in CAPL Browser**

```plaintext
void <OnC2xPacket>( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  byte rx_data[100];
  long rx_length;
  // get the payload of the packet
  rx_length = C2xGetThisData( 0, elCount(rx_data), rx_data );
  // do something with rx_data
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)