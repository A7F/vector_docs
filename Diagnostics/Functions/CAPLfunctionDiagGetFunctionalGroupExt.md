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
