[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1587/Functions/CAPLfunctionJ1587SetJ1587TP.md)

## CAPL Functions » J1587 » setJ1587TP

### Function Syntax

```plaintext
void setJ1587TP( j1587Param param, dword mode );
```

### Description

Selects the setting for the [transport protocol](../../../CANoeCANalyzer/J1587/J1587TransportProtocol.md) to use when sending a J1587 parameter via the `output` function.

### Parameters

- **param**: J1587 parameter for which the setting is used
- **mode**:
  - **0 (default)**: select the transport protocol by means of the receiver (selector J1587_ReceiverMID)
    - MID 127: Multisection
    - other MID: CMP/CDP
  - **1**: disable use of any transport protocol
  - **2**: use Multisection
  - **3**: use CMP/CDP

### Return Values

—

### Example

—
