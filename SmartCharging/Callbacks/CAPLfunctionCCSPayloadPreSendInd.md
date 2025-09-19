[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionCCSPayloadPreSendInd.md)

# PayloadPreSendInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CCSCallback) » PayloadPreSendInd

Valid for:  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void PayloadPreSendInd(inout bytes payload, MessageIdType messageID, uint32 payloadLength);
```

## Description

The callback is called each time a TPC/UDP packet containing a Vehicle2Grid or SECC Discovery message is about to be sent by the DO. It allows to peek for the payload and its length before sending. Additionally, the payload and by doing so also the length may be changed for the purpose of fault injection.

It is available for the whole Distributed Object.

## Parameters

- **payload**: The UDP/TCP payload data (writable)
- **messageId**: ID of the message to be sent. See [MessageIDs](SCC_MessageID.md) for more information.
- **payloadLength**: The length of the UDP/TCP payload at the time of the callback. Will automatically match the length of the buffer, once modified payload is passed back to the DO that is about to send this message.

## Return Values

—

## Example

```plaintext
on fct_returning EV.PayloadPreSendInd
{
  const int bufferSize = 200;
  byte payloadBuffer[bufferSize];

  writeLineEx(-3,1,"PayloadPreSendInd for message %d with payloadLength %d", this.messageID, this.payloadLength);

  if(bufferSize < this.payloadLength)
  {
    // Payload bigger than buffer, skipping manipulation
    return;
  }

  // Copy data to buffer to allow manipulation
  memcpy(payloadBuffer, this.payload);

  // Manipulate first byte of header
  payloadBuffer[0] = payloadBuffer[0] + 1;

  // Copy manipulated data back to inout parameter, so that values are sent
  memcpy(this.payload, payloadBuffer, this.payloadLength);

  if(this.payloadLength + 1 <= bufferSize)
  {
    // payload shorter than buffer, appending one byte
    payloadBuffer[this.payloadLength] = 5;
    // Copy manipulated and extended data back to inout parameter, so that values are sent
    memcpy(this.payload, payloadBuffer, this.payloadLength + 1);
  }
  else // payload fills buffer completely, not extending
  {
    // Copy manipulated data back to inout parameter, so that values are sent
    memcpy(this.payload, payloadBuffer, this.payloadLength);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
