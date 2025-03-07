[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagClosedChannelInd.md)

**CAPL Functions** » **Diagnostics** » **diag_ClosedChannelInd**

# diag_ClosedChannelInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diag_ClosedChannelInd (); // form 1
long diag_ClosedChannelInd (char target[]); // form 2
```

## Description

This function communicates to CANoe that the communication channel is no longer available, e.g., the tester closed the channel or a non-reparable error occurred.

The CAPL program first has to call [diag_SetupChannelCon](CAPLfunctionDiagSetupChannelCon.md) before further data can be sent.

## Parameters

- **target**: The qualifier of the ECU whose channel has been closed.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
// This callback shall be called by an example TP layer
TPLayer_ClosedChannel( long connectionHandle)
{
  char ecuQualifier[20];
  TPLayerGetECUQualifierForHandle(connectionHandle, ecuQualifier);
  diag_ClosedChannelInd(ecuQualifier);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)