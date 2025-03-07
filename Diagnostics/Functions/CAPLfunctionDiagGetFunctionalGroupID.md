[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetFunctionalGroupID.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetFunctionalGroupId

# diagGetFunctionalGroupId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword diagGetFunctionalGroupId ()
dword diagGetFunctionalGroupId (char groupQualifier)
```

## Description

Determines the CAN ID on which functional requests are sent by the diagnostic tester.

If the functional group is not specified, the destination set with [diagSetTarget](CAPLfunctionDiagSetTarget.md) is used.

## Parameters

- **groupQualifier**: Functional group's qualifier.

## Return Values

CAN ID of the requests, or 0xFFFFFFFF if no functional group has been set.

## Example

—

[Processing Functional Diagnostic Requests in ECU Simulations](../CAPLfunctionsDiagnosticsProcessingDiagnosticRequests.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)