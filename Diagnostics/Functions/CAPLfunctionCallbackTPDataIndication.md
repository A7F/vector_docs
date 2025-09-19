# CallbackTPDataIndication

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CallbackTPDataIndication( dword timeStart, dword timeFinish,
    WORD channel, dword CanIdTx, dword additionalTx,
    dword CanIdRx, BYTE data[], char source[], char target[])

long CallbackTPDataIndication( dword timeStart, dword timeFinish,
    WORD channel, dword CanIdTx, dword additionalTx,
    dword CanIdRx, BYTE data[])
```

## Description

Indicates the transmission of an ISO TP data packet on a CAN channel where the ISO TP Observer is configured to supervise the communication.

## Parameters

- **timeStart, timeFinish**: Start and end of data transmission (resolution: 10µs).
- **channel**: CAN channel the transmission took place on.
- **CanIdTx**: CAN id used by the sending node.
- **additionalTx**: Address extension, if used.
- **CanIdRx**: CAN id configured for FlowControl frames for this transmission.
- **data**: The data transferred.
- **source, target**: Names of the source and target nodes, also displayed in the Trace Window events.

## Return Values

- **1**: Forward the event further down the measurement branch.
- **0**: Do NOT forward the event down the measurement branch.
- **Other**: reserved

## Example

See [Filter Diagnostic Objects using CAPL Filter in the Measurement Setup](../../../CANoeCANalyzer/Diagnostics/Analysis/DiagnosticsFeaturesAnlyzDisplay.md)
