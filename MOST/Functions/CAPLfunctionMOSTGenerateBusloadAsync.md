[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGenerateBusloadAsync.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGenerateBusloadAsync

# mostGenerateBusloadAsync

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is available with MOST hardware VN2600, VN2610, VN2640, OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, and OptoLyzer MOCCA compact 150c.

## Function Syntax

`long mostGenerateBusloadAsync (long channel, long pkts);`

## Description

The function sends cyclical packets to the asynchronous channel. Use the [mostConfigureBusloadAsync()](CAPLfunctionMOSTConfigureBusloadAsync.md) or [mostSetStressNodeParameter()](CAPLfunctionMOSTSetGetStressNodeParameter.md) function to specify the send parameters and contents of the packets.

**Note for OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e and OptoLyzer MOCCA compact 150c**  
This function shows no effect if the StressNIC is not set to slave mode. For that purpose use [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md) with the proper parameter.

## Parameters

- **channel**: Channel of the connected MOST hardware.
- **pkts**:
  - `0`: Stops the busload generation
  - `>0`: Sends the given number of packets
  - `-1`: Sends continual packets

## Return Values

- `<= 0`: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGenerateBusloadCtrl](CAPLfunctionMOSTGenerateBusloadCtrl.md) • [mostGenerateLightError](CAPLfunctionMOSTGenerateLightError.md) • [mostGenerateLockError](CAPLfunctionMOSTGenerateLockError.md) • [mostConfigureBusloadAsync](CAPLfunctionMOSTConfigureBusloadAsync.md) • [outputMostPkt](CAPLfunctionMOSTOutputMostPkt.md) • [OnMostStress](../EventProcedures/CAPLfunctionOnMOSTStress.md)
