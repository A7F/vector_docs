[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTMHPError.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostMHPError

# OnMostMHPError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
`OnMostMHPError` can only be used in the **Measurement Setup** and should be inserted under the item "Callback function".  
For simulation of a MOST High connection sender and receiver in CAPL, the MOST High DLL can be used. The DLL is located in the Exec32 folder of the MOST High Demos.

## Function Syntax

```plaintext
long OnMostMHPError(long sourceDevID, long destDevID, long fBlockID, long instID, long functionID, long opType);
```

## Description

The event procedure is called up as soon as a MOST High protocol violation is observed.

Within this event procedure the following functions are available:

- `long mostMHPErrorCode()`

  Indicates the MHP observer error number. See possible [MHP observer error codes](../CAPLfunctionsMOSTHighObserverErrorCodes.md).

  **Parameter**:  
  None  
  **Returns**:  
  Observer error number

- `long mostMHPErrorValue()`

  Indicates the error value. Not supported by all [error codes](../CAPLfunctionsMOSTHighObserverErrorCodes.md).

  **Parameter**:  
  None  
  **Returns**:  
  Error value or 0

- `long mostMHPErrorExpectedValue()`

  Indicates the expected value. Not supported by all [error codes](../CAPLfunctionsMOSTHighObserverErrorCodes.md).

  **Parameter**:  
  None  
  **Returns**:  
  Expected value or 0

- `long mostMHPErrorIsWarning()`

  Indicates if this is a warning. Warnings may indicate a communication problem.

  **Parameter**:  
  None  
  **Returns**:  
  Error value or 0

The functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventTimeNS](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

## Parameters

- **sourceDevID**: Address of the transmitter
- **destDevID**: Address of the receiver
- **fBlockID**: FBlockID of the receiver
- **instID**: Instance ID of the receiver
- **functionID**: FunctionID of the receiver
- **opType**: OpType of the receiver

## Return Values

The return value determines whether the MHP error event is relayed to the next function block in the Measurement Setup (e.g., a Trace Window).

- **0**: No relay
- **1**: Relay

## Example

—

[**MOST High Protocol: Simulation of Sender and Receiver**](../../../CANoeCANalyzer/MOST/MOSTHighProtocolSimulation.md) • [OnMostMHPBlock](CAPLfunctionOnMOSTMHPBlock.md) • [OnMostMHPPacket](CAPLfunctionOnMOSTMHPPacket.md) • [mostMHPErrorSetTraceColors](../Functions/CAPLfunctionMOSTMHPErrorSetTraceColors.md) • [MOST High Observer Error Codes](../CAPLfunctionsMOSTHighObserverErrorCodes.md) • [MOST High Observer and Combiner](../CAPLfunctionsMOSTHighObserverCombiner.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
