[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTSyncSpdif.md)

## CAPL Functions » MOST » OnMostSyncSpdif

### Function Syntax

`OnMostSyncSpdif(long label, long device, long mode);`

### Description

The event procedure `OnMostSyncSpdif` will be called after routing of S/PDIF input or output of the network interface (see [mostSetSyncSpdif](../Functions/CAPLfunctionMOSTSetSyncSpdif.md)).

### Parameters

- **label**: Connection label.
- **device**:
  - 0: S/PDIF-In: Audio input signals are put on synchronous channels.
  - 1: S/PDIF-Out: Synchronous channel signals are grabbed for audio output.
- **mode**:
  - 0: Routing cancelled.
  - 1: Routing executed.

### Return Values

—

### Example

—
