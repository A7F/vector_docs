[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFDXConfigureSequenceCounting.md)

## CAPL Functions » General » Function Overview » FDXConfigureSequenceCounting

### FDXConfigureSequenceCounting

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```plaintext
long FDXConfigureSequenceCounting(long fdxClientHandle, long mode);
```

### Description

This function sets the behavior with which CANoe DE product should fill out the field **seqNrOrDgramLen** in the FDX datagram header.

Prerequisite for the function is to configure **UPD/IPv4** or **UDP/IPv6** as transport layer for the FDX feature.

### Parameters

- **fdxClientHandle**: FDX client for which the sequence counting should be configured.
- **mode**: Mode that should set for the Sequence Counting.
  - 0: Automatic mode (default for new connections)
    - The Sequence Counting automatically adapts to the FDX client.
  - 1: Enabled
    - The Sequence Counting is activated for the client.
  - 2: Disabled
    - The Sequence Counting is deactivated for this client.

### Return Values

- **0**: Successful function call
- **-1**: The parameter **fdxClientHandle** is invalid.
- **-2**: The parameter **mode** is invalid.
- **-3**: The configured transport layer does not support **Sequence Counting**.

### Example

[Coupling of two CANoe Instances using the FDX Protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocolCouplingCANoeInstances.md)
