[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetSyncSpdifMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetSyncSpdifMode

# mostSetSyncSpdifMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2610/VN2640.

## Function Syntax

```plaintext
long mostSetSyncSpdifMode(long channel, long mode);
```

## Description

Sets the timing mode for the S/PDIF signal.

## Parameters

- **channel**: Channel of the connected interface
- **mode**:
  - `0`: S/PDIF slave.
  - `1`: S/PDIF master.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

**Use Cases:**

- **External S/PDIF sink device connected to the S/PDIF Out connector of the VN2610**

  In this case, the VN2610 is **S/PDIF Master** and the S/PDIF mode has to be set accordingly (mode = 1).

  ```plaintext
  on key 's'
  {
    long channel = 1;
    mostSetSyncSpdifMode(channel, 1);
  }
  ```

- **External S/PDIF source device connected to the S/PDIF In connector of the VN2610**

  In this case, the VN2610 is **S/PDIF Slave** and the S/PDIF mode has to be set accordingly (mode = 0).

  ```plaintext
  on key 's'
  {
    long channel = 1;
    mostSetSyncSpdifMode(channel, 0);
  }
  ```

More S/PDIF examples see [MOST Access to Digital Audio Channels (S/PDIF In and Out)](../../../CANoeCANalyzer/MOST/MOSTSynchronousChannelDigitalAudio.md).

[mostSetSyncSpdif](CAPLfunctionMOSTSetSyncSpdif.md) • [mostSetSyncSpdifLock](CAPLfunctionMOSTSetSyncSpdifLock.md) • [mostGetSyncSpdifMode](CAPLfunctionMOSTGetSyncSpdifMode.md) • [mostSetClockSource](CAPLfunctionMOSTSetClockSource.md) • [mostGetClockSource](CAPLfunctionMOSTGetClockSource.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)