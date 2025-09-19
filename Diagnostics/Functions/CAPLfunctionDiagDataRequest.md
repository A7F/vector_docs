# _Diag_DataRequest

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void _Diag_DataRequest (BYTE data[], dword count, long furtherSegments);
```

## Description

With this function CANoe triggers the CAPL interface to transmit data.

## Parameters

- **data**: The data of the diagnostic primitive (byte stream of request or response) that the node should transmit on the bus. This may be several hundred or thousand bytes, therefore a suitable transport protocol has to be used here to forward the data.
- **count**: The actual number of bytes to be sent.
- **furtherSegments**:
  - `0`: This is the last segment of a segmented transmission (see [diag_SetDataSegmentation](CAPLfunctionDiagSetDataSegmentation.md)), typical value for ISO TP.
  - `1`: Further segments follow.
  - `other`: reserved

## Return Values

—

## Example

See [DoIP_DataReq](CAPLfunctionDoIPDataReq.md)
