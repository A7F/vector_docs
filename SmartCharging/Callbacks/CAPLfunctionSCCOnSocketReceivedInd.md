[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCOnSocketReceivedInd.md)

# OnSocketReceivedInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CCSCallback) » OnSocketReceivedInd

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnSocketReceivedInd(MessageIdType messageId, uint32 sourcePort, uint32 destinationPort, inout bytes payload, uint32 payloadLength);
```

## Description

The callback is called each time a TCP/UDP packet containing a Vehicle2Grid or SECC Discovery message is received on the socket by the DO. It allows to query the payload and its length as well as for the source and destination port.

It is available for the whole Distributed Object.

## Parameters

- **messageId**: The id of the received message contained in the packet. See [MessageIDs](SCC_MessageID.md) for more information.
- **sourcePort**: The source port of the received packet.
- **destinationPort**: The destination port of the received packet.
- **payload**: The payload of the received packet.
- **payloadLength**: The length of the payload of the received packet.

## Return Values

—

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)