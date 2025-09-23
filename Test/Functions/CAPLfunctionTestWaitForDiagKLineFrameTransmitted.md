# TestWaitForDiagKLineFrameTransmitted

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForDiagKLineFrameTransmitted(dword timeout_ms);` // form 1
- `long TestWaitForDiagKLineFrameTransmitted(char ecuQualifier[], dword timeout_ms);` // form 2

## Description

Waits for the occurrence of a transmitted valid message. Should the message not occur before the expiration of the time **timeout_ms**, the wait condition is resolved nevertheless.

## Parameters

- **timeout_ms**: Maximum time that should be waited [ms]. (Transmission of 0: no timeout controlling)
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

—

[TestWaitForDiagKLineFrameReceived](CAPLfunctionTestWaitForDiagKLineFrameReceived.md) • [TestGetWaitKLineEventFrame](CAPLfunctionTestGetWaitEventKLineFrame.md)
