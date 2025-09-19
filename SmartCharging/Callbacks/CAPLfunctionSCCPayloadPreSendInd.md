[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCPayloadPreSendInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_PayloadPreSendInd

# SCC_PayloadPreSendInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Notes**

- This callback is called after [SCC_PreSendInd](CAPLfunctionSCCSignaturePreSendInd.md) (EVSE only), but before [SCC_MessageTxInd](CAPLfunctionSCCMessageTxInd.md).
- The usual restrictions of the protocol apply once sending starts, i.e. minimum length of Ethernet packets, TCP fragmentation and retransmission.
- The payload field of the application header is not affected when setting the payload length with this function. However, it can be altered as part of the payload.

## Function Syntax

```plaintext
void SCC_PayloadPreSendInd(byte SessionOrRunID[], dword MessageID, byte Payload[], dword& PayloadLength)
```

## Description

The callback is called each time a Vehicle2Grid, SECC Discovery or SLAC message is ready to be sent by the simulation DLL. It allows to peek for the payload and its length before sending. Also, both payload and length may be changed for the purpose of fault injection.

## Parameters

- **SessionOrRunID**: 8-byte long SessionID (V2G) or RunID (SLAC) of the connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **[MessageID](SCC_MessageID.md)**: Type of sent message:
  - For SLAC messages, MMType (2 byte) according to specification.
  - For V2G messages see help page [MessageID](SCC_MessageID.md).
- **Payload**: The ETH/UDP/TCP payload data (writable).
- **PayloadLength**: The length of the ETH/UDP/TCP payload (writable).

## Return Values

—

## Example

```plaintext
SCC_PayloadPreSendInd(byte SessionOrRunID[], dword MessageID, byte Payload[], dword& PayloadLength)
{
  Write("PayloadPreSend: message %i with payload %i", MessageID, PayloadLength);

  if (MessageID == 20) // PowerDeliveryRes
  {
    PayloadLength += 2;  // increase length by two bytes
    
    // dummy values for additional bytes
    Payload [25] = 0x99;
    Payload [26] = 0x99;
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
