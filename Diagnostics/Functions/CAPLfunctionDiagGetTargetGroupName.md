# diagGetTargetGroupName

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `DiagGetTargetGroupName(dword bitPos, char groupNameOut[]); // form 1`
- `long DiagGetTargetGroupName(char ecuQualifier[], dword bitPos, char groupNameOut[]); // form 2`

## Description

Returns the name of the diagnostic target group for which the bit at the given position is used by [diagGetAssignedTargetGroups](CAPLfunctionDiagGetAssignedTargetGroups.md). If the target ECU is not specified explicitly, the target selected with [diagSetTarget](CAPLfunctionDiagSetTarget.md) is used.

## Parameters

- **ecuQualifier**: Use this diagnostic target, not that selected with DiagSetTarget.
- **bitPos**: Position of the bit in the bitmask returned by DiagGetAssignedTargetGroups.
- **groupNameOut**: The name of the target group is written to this field in the CAPL file's encoding.

## Return Values

- **≥ 0**: number of characters written
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [diagGetAssignedTargetGroups](CAPLfunctionDiagGetAssignedTargetGroups.md)

[diagGetAssignedTargetGroups](CAPLfunctionDiagGetAssignedTargetGroups.md)
