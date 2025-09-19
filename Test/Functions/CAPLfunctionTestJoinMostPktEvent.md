[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinMostPktEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinMostPktEvent

# TestJoinMostPktEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestJoinMostPktEvent(long aSourceAddress, long aDestinationAddress, char aPktDataDesc[], long aInstanceID)`
- `long TestJoinMostPktEvent(long aSourceAddress, long aDestinationAddress, char aPktDataDesc[])`
- `long TestJoinMostPktEvent(char aPktDataDesc[], long aInstanceID)`
- `long TestJoinMostPktEvent(char aPktDataDesc[])`

## Description

Adds an event condition for MOST packets to the current set of joined event conditions. This function does not wait.

**Note:** Note, that the first and third signatures are exclusively suited to set up wait condition events for packets having function catalog format, whereas the other signatures also allow the definition of raw packet events.

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

**Note:** For parameters **aSourceAddress**, **aDestinationAddress**, and **aInstanceId** the following applies: If **-1** is given, the corresponding field can get any value. This is also the standard for not explicit set values.

## Return Values

- **-6**: Parse Error; on specification of a packet description string, that can’t be resolved with the XML function catalog or that is flawed.
- **-3**: Join error
- **-1**: General error e.g. the functionality is not available
- **> 0**: number of joined events

## Example

—

[TestWaitForMostPkt](CAPLfunctionTestWaitForMostPkt.md) • [TestWaitForMostSpyPkt](CAPLfunctionTestWaitForMostSpyPkt.md) • [TestJoinMostSpyPktEvent](CAPLfunctionTestJoinMostSpyPktEvent.md) • [TestGetWaitEventMostPkt](CAPLfunctionTestGetWaitEventMostPkt.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
