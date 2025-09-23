# OnXcpError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnXcpError (char ecuQualifier[], byte xcpCmd, byte xcpErrorCode);
```

## Description

Whenever the XCP slaves answers with a negative response (i.e. not 0xFF) the OnXCPError callback function is called.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).
- **xcpCmd**: XCP command sent by CANoe DE Family.
- **xcpErrorCode**: Error code returned by the XCP slave.

## Return Values

—

## Example

—
