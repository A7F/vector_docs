[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetClockSource.md)

**CAPL Functions** » **MOST** » **mostSetClockSource**

# mostSetClockSource

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2610.

## Function Syntax

```plaintext
long mostSetClockSource(long channel, long source);
```

## Description

Sets the clock source for the MOST timing master. The function has no effect if the network interface is configured as MOST timing slave.

## Parameters

- **channel**: Channel of the connected interface
- **source**:
  - `0`: Internal oscillator.
  - `1`: Synchronizes the timing master clock to the S/PDIF input signal. The network interface must be configured as S/PDIF timing slave (refer to [mostSetSyncSpdifMode()](CAPLfunctionMOSTSetSyncSpdifMode.md)).

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

**Use case**: External S/PDIF source device connected to the **S/PDIF In** connector of the VN2610

Typically the internal oscillator is used as clock source, since most S/PDIF source devices do not generate a S/PDIF signal with the same clock as the MOST clock (44,1 / 48 kHz).

```plaintext
// use internal oscillators timing master clock
on key 's'
{
  long channel = 1;

  // configure network interface as S/PDIF slave
  mostSetSyncSpdifMode( channel, 0 );
  mostSetSyncSpdifLock( channel, 1 );

  // set the clock source
  mostSetClockSource( channel, 0 );
}
```

In some special cases, e.g. for testing purpose it is possible to synchronize the timing master clock to S/PDIF input signal.

```plaintext
// synchronize the timing master clock to the S/PDIF input signal
on key 's'
{
  long channel = 1;

  // configure network interface as S/PDIF slave
  mostSetSyncSpdifMode( channel, 0 );

  // set the clock source
  mostSetClockSource( channel, 1 );
}
```

More S/PDIF examples see [MOST Access to Digital Audio Channels (S/PDIF In and Out)](../../../CANoeCANalyzer/MOST/MOSTSynchronousChannelDigitalAudio.md).

**Related Functions**:  
[mostSetTimingMode](CAPLfunctionMOSTSetTimingMode.md) • [mostSetSyncSpdifMode](CAPLfunctionMOSTSetSyncSpdifMode.md) • [mostGetSyncSpdifMode](CAPLfunctionMOSTGetSyncSpdifMode.md) • [mostGetClockSource](CAPLfunctionMOSTGetClockSource.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md) • [mostSetSyncSpdif](CAPLfunctionMOSTSetSyncSpdif.md)
