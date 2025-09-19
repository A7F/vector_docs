# C2xGetThisTimeNS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only usable in a CAPL callback that had been registered with [C2xReceivePacket](CAPLfunctionC2xReceivePacket.md).

## Function Syntax

```
qword C2xGetThisTimeNS( void );
```

## Description

This function returns the time stamp of an received WLAN packet in nanoseconds.

## Parameters

— 

## Return Values

Time stamp in nanoseconds

## Example

**Node System - PreStart in CAPL Browser**

```capl
on preStart
{
  C2xReceivePacket("OnC2xPacket");
}
```

**Node Callback Function in CAPL Browser**

```capl
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  float t;
  t = (float)C2xGetThisTimeNS();
  write("Received packet at %f [ns]", t );
}
```
