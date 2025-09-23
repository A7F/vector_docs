# TestWaitForMostSpyPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestWaitForMostSpyPkt(long aSourceAddress, long aDestinationAddress, char aPktDataDesc[], long aInstanceID, dword aTimeout);`
- `long TestWaitForMostSpyPkt(long aSourceAddress, long aDestinationAddress, char aPktDataDesc[], dword aTimeout);`
- `long TestWaitForMostSpyPkt(char aPktDataDesc[], long aInstanceID, dword aTimeout);`
- `long TestWaitForMostSpyPkt(char aPktDataDesc[], dword aTimeout);`

## Description

Waits for the occurrence of the specified MOST (spy) packet. Should the event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

The first and third signatures are exclusively suited to set up wait conditions for packets having function catalog format, whereas the other signatures also allow the definition of raw packets.

**Note**: Spy packets, but also node packets (with any direction) will resolve a wait condition set up by this function, since CANoe does not double an incoming packet on a channel that has asynchronous spy activated.

## Parameters

**Note**: For parameters **aSourceAddress**, **aDestinationAddress**, and **aInstanceId** the following applies:

If **-1** is given, the corresponding field can get any value. This is also the standard for not explicit set values.

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

## Return Values

- **-6**: Parse Error; on specification of a packet description string, that can’t be resolved with the XML function catalog or that is flawed
- **-2**: Resume based on constraint violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on timeout
- **1**: Resume based on occurred event

## Example

—

[TestWaitForMostPkt](CAPLfunctionTestWaitForMostPkt.md) • [TestJoinMostPktEvent](CAPLfunctionTestJoinMostPktEvent.md) • [TestJoinMostSpyPktEvent](CAPLfunctionTestJoinMostSpyPktEvent.md) • [TestGetWaitEventMostPkt](CAPLfunctionTestGetWaitEventMostPkt.md)
