[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagDataCon.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diag_DataCon

# diag_DataCon

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `void diag_DataCon (long count); // form 1`
- `void diag_DataCon (char target[], dword count); // form 2`

## Description

Tells the diagnostic layer, via the **count** parameter, how many bytes of data were successfully handed over to the TP layer.

This function is typically called within a transport layer callback. Once the diagnostic layer has initiated the transmission of a message via [_Diag_DataRequest](CAPLfunctionDiagDataRequest.md) and the transport layer has sent this message in its entirety, using several message segments if needed, the transport layer uses this function to confirm to the diagnostic layer that the message was sent successfully.

**Note**: Depending on the transport layer, this confirmation might already be given when the data was handed over to the TP layer, i.e. before the data physically has been sent entirely.

## Parameters

- **count**: Number of bytes transmitted successfully.
- **target**: The qualifier of the ECU the request was sent to.

## Return Values

—

## Example

See [DoIP_DataCon](CAPLfunctionDoIPDataCon.md)

```c
// This callback shall be called by an example TP layer
TPLayer_SendConfirmation( long connectionHandle, long count)
{
  char ecuQualifier[20];
  TPLayerGetECUQualifierForHandle(connectionHandle, ecuQualifier);
  diag_DataCon(ecuQualifier, count);
}
```

[Communication Layer Connection / Reference Implementations](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)