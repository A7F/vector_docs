# OnLastTransmittedMessageIdChanged

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CCSCallback) » OnLastTransmittedMessageIdChanged

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
void OnLastTransmittedMessageIdChanged ( LastTxMessageIdType LastTxMessageId )
```

## Description

This callback is called after a message was transmitted. It is available for the **whole** Distributed Object.

## Parameters

- **LastTxMessageId**: ID of the last message received. See [MessageIDs](../Callbacks/SCC_MessageID.md) for more information.

## Return Values

—

## Example

—
