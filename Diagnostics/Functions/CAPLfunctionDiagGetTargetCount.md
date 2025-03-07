[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetTargetCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetTargetCount

# diagGetTargetCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagGetTargetCount();
```

## Description

Returns the number /n/ of possible diagnostic targets configured. For indices /i/ with 0 ≤ i ≤ n you can retrieve the target qualifier with [DiagGetTargetQualifier](CAPLfunctionDiagGetTargetQualifier.md).

**Note**: Diagnostic descriptions that cannot work as diagnostic targets are not counted, e.g. descriptions configured as **interpretation only** are ignored.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or number of diagnostic targets.

## Example

```plaintext
long i;
char ecuQual[100];
i = diagGetTargetCount();
while( i-- > 0)
{
   diagGetTargetQualifier( i, ecuQual, elcount(ecuQual));
   write( "Target %d: %s", i, ecuQual);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)