[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetSyncSpdifLock.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetSyncSpdifLock

# mostSetSyncSpdifLock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2610.

## Function Syntax

```plaintext
long mostSetSyncSpdifLock(long channel, long mode);
```

## Description

The function locks the internal S/PDIF timing generator on the S/PDIF input data stream.

Unlock the timing generator if frame synchronization is not possible due to a closed loop configuration. A closed loop means that the S/PDIF input signal is locked through an external S/PDIF device on the S/PDIF output of the network interface.

## Parameters

- **channel**: Channel of the connected interface
- **mode**:
  - `0`: Separates the timing generator from the S/PDIF input data stream.
  - `1`: Locks the timing generator on the S/PDIF input data stream.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

**Use Cases:**

- [External S/PDIF source device connected to the S/PDIF In connector of the VN2610](javascript:void(0))
  
  In this case the VN2610 is **S/PDIF Slave** (set by [mostSetSyncSpdifMode()](CAPLfunctionMOSTSetSyncSpdifMode.md)). In case the VN2610 is configured as TimingSlave it automatically locks the internal S/PDIF timing generator on the S/PDIF input data stream. As TimingMaster there are two possibilities for configuring the VN2610: Please refer to the example given for [mostSetClockSource()](CAPLfunctionMOSTSetClockSource.md).

- [External S/PDIF source and sink device connected to the S/PDIF In and Out connector of the VN2610](javascript:void(0))

  This is **not** the typical use case but in case of synchronization problems (mentioned above) the timing generator has to be separated from the S/PDIF input data stream.

  ```plaintext
  on key 's'
  {
    long channel = 1;
    mostSetSyncSpdifLock( channel, 0 );
  }
  ```

More S/PDIF examples see [MOST Access to Digital Audio Channels (S/PDIF In and Out)](../../../CANoeCANalyzer/MOST/MOSTSynchronousChannelDigitalAudio.md).

[mostSetSyncSpdif](CAPLfunctionMOSTSetSyncSpdif.md) • [mostSetSyncSpdifMode](CAPLfunctionMOSTSetSyncSpdifMode.md) • [mostGetSyncSpdifMode](CAPLfunctionMOSTGetSyncSpdifMode.md) • [mostSetClockSource](CAPLfunctionMOSTSetClockSource.md) • [mostGetClockSource](CAPLfunctionMOSTGetClockSource.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
