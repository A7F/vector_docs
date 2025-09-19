[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTMHPConnection.md)

**CAPL Functions** » **MOST** » **OnMostMHPConnection**

# OnMostMHPConnection

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
`OnMostMHPConnection` can only be used in the **Measurement Setup** and should be inserted under the item "Callback function". For simulation of a MOST High connection sender and receiver in CAPL, the MOST High DLL can be used. The DLL is located in the Exec32 folder of the MOST High Demos.

## Function Syntax

```plaintext
long OnMostMHPConnection(long sourceDevID, long destDevID, long fBlockID, long instID, long functionID, long opType);
```

## Description

The event procedure is called up as soon as a MOST High connection version 2.2 or higher is terminated. Within this event procedure the following functions are available:

- `long mostMHPConnectionIsSpy()`

  Indicates whether the connection was made up of Spy messages.  
  **Parameters**: None  
  **Returns**:  
  0: Comprised of node messages  
  1: Comprised of Spy messages

- `long mostMHPConnectionVersion()`

  Indicates the used MOST High Protocol version.  
  **Parameters**: None  
  **Returns**:  
  0: Version 2.1  
  1: Version 2.2

- `long mostMHPConnectionNegAcks()`

  Indicates the number of negative frame acknowledge messages.  
  **Parameter**: None  
  **Returns**: Number of NegAcks (see MHP specification)

- `long mostMHPConnectionFrameRequests()`

  Indicates the number of single or multiple frame request messages.  
  **Parameter**: None  
  **Returns**: Number of (multiple) frame requests

- `long mostMHPConnectionBlockRequests()`

  Indicates the number of block request messages.  
  **Parameter**: None  
  **Returns**: Number of block requests

- `long mostMHPConnectionWarnings()`

  Indicates the number of MHP observer warnings. Warnings may indicate communication problems.  
  **Parameter**: None  
  **Returns**: Number of Observer warnings

- `long mostMHPConnectionErrors()`

  Indicates the number of MHP Observer errors. Errors indicate MOST High Protocol violations.  
  **Parameter**: None  
  **Returns**: Number of Observer errors

- `long mostMHPConnectionPackets()`

  Indicates the number of connections transmitted during the MHP connection.  
  **Parameter**: None  
  **Returns**: Number of packets

The functions [mostEventChannel()](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime()](../Functions/CAPLfunctionMOSTEvent.md), and [mostEventTimeNS()](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

## Parameters

- **sourceDevID**: Address of the transmitter
- **destDevID**: Address of the receiver
- **fBlockID**: FBlockID of the receiver
- **instID**: Instance ID of the receiver
- **functionID**: FunctionID of the receiver
- **opType**: OpType of the receiver

## Return Values

The return value determines whether the MHP connection event is relayed to the next function block in the Measurement Setup (e.g., a Trace Window).

- **0**: No relay
- **1**: Relay

## Example

—

**Related Links:**

- [MOST High Protocol: Simulation of Sender and Receiver](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md)
- [OnMostMHPBlock](CAPLfunctionOnMOSTMHPBlock.md)
- [OnMostMHPError](CAPLfunctionOnMOSTMHPError.md)
- [mostMHPConnectionSetTraceColors](../Functions/CAPLfunctionMOSTMHPConnectionSetTraceColors.md)
- [MOST High Observer and Combiner](../CAPLfunctionsMOSTHighObserverCombiner.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
