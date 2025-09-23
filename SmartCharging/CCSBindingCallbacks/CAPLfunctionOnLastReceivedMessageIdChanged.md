# OnLastReceivedMessageIdChanged

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnLastReceivedMessageIdChanged ( LastRxMessageIdType LastRxMessageId )
```

## Description

This callback is called as soon as a message is received.

It is available for the **whole** Distributed Object and for the following embedded members:

- SLAC
- SDP
- SAP
- ISO20
- ScheduleRenegotiation
- MeteringConfirmation

## Parameters

- **LastRxMessageId**: ID of the last message received. See [MessageIDs](../Callbacks/SCC_MessageID.md) for more information.

## Return Values

—

## Example

—
