[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostPkt.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMostPkt

# TestWaitForMostPkt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long TestWaitForMostPkt(long aSourceAddress, long aDestinationAddress, char aPktDataDesc[], long aInstanceID, dword aTimeout);`
- `long TestWaitForMostPkt(long aSourceAddress, long aDestinationAddress, char aPktDataDesc[], dword aTimeout);`
- `long TestWaitForMostPkt(char aPktDataDesc[], long aInstanceID, dword aTimeout);`
- `long TestWaitForMostPkt(char aPktDataDesc[], dword aTimeout);`

## Description

Waits for the occurrence of the specified MOST packet. Should the event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

**Note:** Note, that the first and third signatures are exclusively suited to set up wait conditions for packets having function catalog format, whereas the other signatures also allow the definition of raw packets.

## Parameters

- **aSourceAddress**: Source address
- **aDestinationAddress**: Target address
- **aPktDataDesc**: String containing a symbolic or numeric description of the packet data. Following formats are allowed:
  - `<Raw data byte description>`
  - `<FBlock>.<Instance>.<Function>.<OpType>`
  - `<FBlock>.<Instance>.<Function>.<OpType>(<Raw data byte description>)`
  - `<FBlock>.<Instance>.<Function>.<OpType> (<High Protocol frame description>)`

  For a detailed description of the allowed syntax, see [Definition of MOST packets](../CAPLfunctionsTFSMostPacketDefinition.md).

- **aInstanceId**: Numeric value of InstanceID
- **aTimeout**: Timeout in milliseconds

**Note:** For parameters **aSourceAddress**, **aDestinationAddress**, and **aInstanceId** the following applies:
If **-1** is given, the corresponding field can get any value. This is also the standard for not explicit set values.

## Return Values

- **-6**: Parse Error; on specification of a packet description string, that can’t be resolved with the XML function catalog or that is flawed
- **-2**: Resume based on constraint violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on timeout
- **1**: Resume based on occurred event

## Example

—

[TestWaitForMostSpyPkt](CAPLfunctionTestWaitForMostSpyPkt.md) • [TestJoinMostPktEvent](CAPLfunctionTestJoinMostPktEvent.md) • [TestJoinMostSpyPktEvent](CAPLfunctionTestJoinMostSpyPktEvent.md) • [TestGetWaitEventMostPkt](CAPLfunctionTestGetWaitEventMostPkt.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)