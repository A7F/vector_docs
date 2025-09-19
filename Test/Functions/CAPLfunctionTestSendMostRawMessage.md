[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestSendMostRawMessage.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestSendMostRawMessage

# TestSendMostRawMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long TestSendMostRawMessage(long aDestinationAddress, long aRType, BYTE aMsgData[], dword aMsgDataLength, dword aTimeout);
long TestSendMostRawMessage(long aDestinationAddress, long aRType, char aMsgDataDesc[], dword aTimeout);
```

## Description

This function immediately sends a MOST raw control message with the specified data and waits for the associated Tx acknowledgment from the recipient. The AckNack bit is evaluated and the return value specifies whether the creation and sending of the message was successful or not.

The first signature specifies the message data by a byte array, the second uses a string to describe the data bytes as a hex dump.

## Parameters

- **aDestinationAddress**: Target address
- **aRType**: MOST control message subtypes. Must be one of the following values:
  - `0`: Normal
  - `1`: RemoteRead
  - `2`: RemoteWrite
  - `3`: Allocate
  - `4`: Deallocate
  - `5`: GetSource
- **aMsgData**: Byte array containing the data bytes of the raw message to be sent.
- **aMsgDataLength**: Length of byte array aMsgData. Data bytes at positions larger than the value of this parameter will be set to 0 automatically.
- **aMsgDataDesc**: String with hexadecimal values describing the message data bytes of the raw message to be sent, starting at byte position 0, e.g., "0A 0B 0C 0D 0E 0F 10 11 12 13 FF". Blanks will be ignored and can be used to enhance readability. Data bytes at positions beyond the ones described in this parameter will be set to 0 automatically.
- **aTimeout**: Maximum wait time [ms]

## Return Values

- `-6`: Parse Error; on specification of a message data description string that contains other characters than hexadecimal digits
- `-3`: Message was sent, however "not acknowledged" appears in the Tx acknowledgment.
- `-2`: The wait condition was triggered due to a constraint violation.
- `-1`: General error e.g. the functionality is not available
- `0`: Resume due to timeout
- `1`: Message could be sent, Tx acknowledgment received

## Example

—

[TestWaitForMostRawSpyMessage](CAPLfunctionTestWaitForMostRawSpyMessage.md) • [TestGetWaitEventMostRawMsgData](CAPLfunctionTestGetWaitEventMostRawMsgData.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
