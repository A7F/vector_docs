# diag_FirstFrameInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void diag_FirstFrameInd(long source, long target, long length); // form 1
void diag_FirstFrameInd(char ecuQualifier[], dword length); // form 2
```

## Description

Indicates the start of a diagnostic data reception to the diagnostic layer.

This function is typically called from a transport layer callback. For example, the ISO TP protocol on CAN indicates the reception of a **First Frame** to the application.

In the diagnostic layer of a tester, a call to this function will stop the timer started after the request has been sent, i.e. even a very long data reception will not timeout. If the tester has called [testWaitForDiagResponseStart](../../Test/Functions/CAPLfunctionTestWaitForDiagResponseStart.md), that call will now be continued.

## Parameters

- **source**: Identifies the sender node.
- **target**: Identifies the receiver.
- **length**: Number of bytes announced.
- **ecuQualifier**: Qualifier of the ECU that has started to send a response.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

The OSEKTL API for the ISO TP on CAN implementation found in **OSEK_TP.dll** reports First Frames in the callback function `OSEKTL_FirstFrameInd` (see [OSEK TP](../../../../../Subsystems/SML/Subsystems/OsekTP/Content/Topics/OsekTP/OsekTP.md)). The arguments can simply be forwarded in this case:

```plaintext
OSEKTL_FirstFrameIndication( long source, long target, long length)
{
    diag_FirstFrameInd(source, target, length);
}
```

[Communication Layer Connection / Reference Implementations](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md)
