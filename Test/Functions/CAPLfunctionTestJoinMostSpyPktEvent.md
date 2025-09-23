# TestJoinMostSpyPktEvent

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinMostSpyPktEvent

**Valid for**: CANoe DE

## Function Syntax

- `long TestJoinMostSpyPktEvent(long aSourceAddress, long aDestinationAddress, char aPktDataDesc[], long aInstanceID)`
- `long TestJoinMostSpyPktEvent(long aSourceAddress, long aDestinationAddress, char aPktDataDesc[])`
- `long TestJoinMostSpyPktEvent(char aPktDataDesc[], long aInstanceID)`
- `long TestJoinMostSpyPktEvent(char aPktDataDesc[])`

## Description

Adds an event condition for MOST spy packets to the current set of joined event conditions. This function does not wait. The first and third signatures are exclusively suited to set up wait condition events for spy packets having function catalog format, whereas the other signatures also allow the definition of raw spy packet events.

**Note:** Spy packets, but also node packets (with any direction) will resolve a wait condition set up by this function, since CANoe does not double an incoming packet on a channel that has asynchronous spy activated.

## Parameters

- **aSourceAddress**: Source address
- **aDestinationAddress**: Target address
- **aPktDataDesc**: String containing a symbolic or numeric description of the packet data. Following formats are allowed:
  - `<Raw data byte description\>`
  - `<FBlock\>.<Instance\>.<Function\>.<OpType\>`
  - `<FBlock\>.<Instance\>.<Function\>.<OpType\>(<Raw data byte description\>)`
  - `<FBlock\>.<Instance\>.<Function\>.<OpType\> (<High Protocol frame description\>)`

  For a detailed description of the allowed syntax, see [Definition of MOST packets](../CAPLfunctionsTFSMostPacketDefinition.md).

- **aInstanceId**: Numeric value of InstanceID

**Note:** For parameters `aSourceAddress`, `aDestinationAddress`, and `aInstanceId` the following applies: If `-1` is given, the corresponding field can get any value. This is also the standard for not explicit set values.

## Return Values

- **-6**: Parse Error; on specification of a packet description string, that can’t be resolved with the XML function catalog or that is flawed
- **-3**: Join error
- **-1**: General error e.g. the functionality is not available
- **\> 0**: number of joined events

## Example

—

## Related Links

- [TestWaitForMostSpyPkt](CAPLfunctionTestWaitForMostSpyPkt.md)
- [TestWaitForMostPkt](CAPLfunctionTestWaitForMostPkt.md)
- [TestJoinMostPktEvent](CAPLfunctionTestJoinMostPktEvent.md)
- [TestGetWaitEventMostPkt](CAPLfunctionTestGetWaitEventMostPkt.md)
