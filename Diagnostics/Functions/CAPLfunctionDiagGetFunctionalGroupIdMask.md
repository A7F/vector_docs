[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetFunctionalGroupIdMask.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetFunctionalGroupIdMask

# diagGetFunctionalGroupIdMask

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword diagGetFunctionalGroupIdMask ()`
- `dword diagGetFunctionalGroupIdMask (char groupQualifier)`

## Description

Determines the CAN ID mask in order to be able to filter out CAN messages sent by the diagnostic tester as functional requests. If the functional group is not specified, the destination set with [diagSetTarget](CAPLfunctionDiagSetTarget.md) is used.

## Parameters

- **groupQualifier**: Functional group's qualifier

## Return Values

The value returned must be logically ANDed with the ID of a received CAN message. If the result is the same as the [Group ID](CAPLfunctionDiagGetFunctionalGroupID.md), this is a functional request.

## Example

—

[Processing Functional Diagnostic Requests in ECU Simulations](../CAPLfunctionsDiagnosticsProcessingDiagnosticRequests.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)