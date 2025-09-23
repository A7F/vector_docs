# TransportLayerDisconnectInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void TransportLayerDisconnectInd ( uint32 Port, bool IsInitiator )
```

## Description

This callback is called as soon as a TCP connection is closed.

## Parameters

- **Port**: Port number of the TCP connection
- **IsInitiator**:
  - 1 if the simulation DO initiated the shutdown.
  - 0 if the simulation DO received the shutdown request.

## Return Values

—

## Example

—
