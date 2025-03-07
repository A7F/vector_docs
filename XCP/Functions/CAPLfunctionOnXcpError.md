[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionOnXcpError.md)

CAPL Functions » [XCP](../CAPLfunctionsXCPOverview.md) » OnXcpError

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)