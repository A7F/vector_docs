# TestWaitForMostRawSpyMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long TestWaitForMostRawSpyMessage(long aSourceAddress, long aDestinationAddress, long aRType, BYTE aMsgData [], dword aMsgDataLength, dword aTimeout);
```

```c
long TestWaitForMostRawSpyMessage(long aSourceAddress, long aDestinationAddress, long aRType, char aMsgDesc[], dword aTimeout);
```

## Description

This function waits for the occurrence of the specified MOST raw spy control message. Should the message not occur before the expiration of the time aTimeout, the wait condition is resolved nevertheless.

## Parameters

- **aSourceAddress**: Source address
- **aDestinationAddress**: Target address
- **aRType**: MOST control message subtypes. Must be one of the following values:
  - **0**: Normal
  - **1**: RemoteRead
  - **2**: RemoteWrite
  - **3**: Allocate
  - **4**: Deallocate
  - **5**: GetSource
- **aMsgData**: Byte array containing the data bytes of the raw message to be matched.
- **aMsgDataLength**: Length of byte array aMsgData. Data bytes at positions larger than the value of this parameter will not be considered when comparing with incoming messages.
- **aMsgDataDesc**: String with hexadecimal values describing the message data bytes of the raw spy message to be matched, starting at byte position 0, e.g. "0A 0B 0C 0D 0E 0F 10 11 12 13 FF". Blanks will be ignored and can be used to enhance readability. Wildcards can be applied by replacing a nibble with "_", e.g. "0A 0B 0C ___ __ 10". Data bytes at positions beyond the ones described in this parameter will not be considered when comparing with incoming messages.
- **aTimeout**: Maximum wait time [ms]

## Return Values

- **-6**: Parse Error; on specification of a message data description string that contains other characters than hexadecimal digits or wildcards ("_").
- **-2**: Resumed based on Constraint violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on timeout
- **1**: Resume based on occurred event

## Example

—

[TestSendMostRawMessage](CAPLfunctionTestSendMostRawMessage.md) • [TestGetWaitEventMostRawMsgData](CAPLfunctionTestGetWaitEventMostRawMsgData.md)
