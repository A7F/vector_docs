# diagSetP2Timeouts

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagSetP2Timeouts( dword newP2timeout_ms, dword newP2exTimeout_ms); // form 1
long DiagSetP2Timeouts(char ecuQualifier[], dword P2Timeout_ms, dword P2exTimeout_ms); // form 2
```

## Description

Changes the P2 and P2ex timeout values at the built-in diagnostic channel.

**Note:** Use this function only for the built-in diagnostic channel. In combination with the CAPL Callback Interface use [diagSetTimeout](CAPLfunctionDiagSetTimeout.md).

**Note:** It is recommended to define the times **P2 Timeout** and **P2 Extended** as short as possible and just as long as necessary. These times should have a smaller value than the application timeout (VDSRequestApplicationTimeout in CAN.ini).

## Parameters

- **newP2timeout_ms**: The built-in diagnostic channel will use this P2 timeout (in milliseconds) from now on.
- **newP2exTimeout_ms**: New P2 extended value (in milliseconds) for the built-in diagnostic channel.
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

-1 for failed or [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—