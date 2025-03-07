[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetAssignedTargetGroups.md)

**CAPL Functions** » **Diagnostics** » **diagGetAssignedTargetGroups**

# diagGetAssignedTargetGroups

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long DiagGetAssignedTargetGroups(DiagRequest request, dword& targetGroupFlagsOut);
long DiagGetAssignedTargetGroups(DiagResponse response, dword& targetGroupFlagsOut);
```

## Description

Returns a bitmask where each bit represents a target group. The diagnostic description defines in which target group the object may be sent, and the bit for this group is set to 1 in the mask returned.

The position of the bit in the mask (0 for least significant bit) can be used to query the qualifier and name of the target group using [DiagGetTargetGroupQualifier](CAPLfunctionDiagGetTargetGroupQualifier.md) and [DiagGetTargetGroupName](CAPLfunctionDiagGetTargetGroupName.md).

## Parameters

- **request**: Diagnostic request.
- **response**: Diagnostic response.
- **targetGroupFlagsOut**: Receives the bitmask for the target groups.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
void PrintAssignedTargetGroups(diagRequest * req)
{
  dword flags;
  long status;
  dword groupNo;
  char targetGroupQualifier[100];

  // Retrieve the target groups the request may be sent in
  flags = 0;
  status = DiagGetAssignedTargetGroups( req, flags);

  // Convert bitmask to target group qualifier and name for write window
  groupNo = 0;
  while( 0 <= DiagGetTargetGroupQualifier(groupNo, targetGroupQualifier))
  {
    char targetGroupName[100];
    DiagGetTargetGroupName(groupNo, targetGroupName);
    if( flags & (1 << groupNo))
      write( "%d. %s \"%s\": on", groupNo, targetGroupQualifier, targetGroupName);
    else
      write( "%d. %s \"%s\": off", groupNo, targetGroupQualifier, targetGroupName);
    ++groupNo;
  }
}
```

[DiagGetTargetGroupQualifier](CAPLfunctionDiagGetTargetGroupQualifier.md) • [DiagGetTargetGroupName](CAPLfunctionDiagGetTargetGroupName.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)