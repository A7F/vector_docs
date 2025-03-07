[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetFunctionalGroupExt.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetFunctionalGroupExt

# diagGetFunctionalGroupExt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagGetFunctionalGroupExt ()
long diagGetFunctionalGroupExt(char groupQualifier)
```

## Description

Returns the value of the "address extension" byte (extended address information for ISO TP "extended addressing mode").

If the functional group is not specified, the destination set with [diagSetTarget](CAPLfunctionDiagSetTarget.md) is used.

## Parameters

- **groupQualifier**: Functional group's qualifier.

## Return Values

- **-1**: Extended addressing is not used.
- **[0, 255]**: For the ID of a received CAN message to match (see [diagGetFunctionalGroupIdMask](CAPLfunctionDiagGetFunctionalGroupIdMask.md)), the value of the first data byte must correspond to this value.
- **Others**: Reserved

## Example

—

[Processing Functional Diagnostic Requests in ECU Simulations](../CAPLfunctionsDiagnosticsProcessingDiagnosticRequests.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)