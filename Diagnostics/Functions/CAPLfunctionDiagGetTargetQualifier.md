# diagGetTargetQualifier

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long diagGetTargetQualifier( DWORD index, char bufferOut[], DWORD bufferSize);
```

## Description

Writes the target qualifier for the diagnostic target at given index into the buffer. If successful, the qualifier can be used in [DiagSetTarget](CAPLfunctionDiagSetTarget.md).

## Parameters

- **index**: Value in 0 ≤ index ≤ n, where *n* is the number of possible targets returned by [DiagGetTargetCount](CAPLfunctionDiagGetTargetCount.md).
- **bufferOut**: Character array for the result.
- **bufferSize**: Maximum number of characters available in the buffer.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or number of characters copied into the buffer. Note that an error is returned if the buffer is too small for the qualifier.

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
