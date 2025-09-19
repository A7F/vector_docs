[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPDeactivateAll.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpDeactivateAll

# xcpDeactivateAll

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long xcpDeactivateAll(char[] ecuQualifier);
```

## Description

Deactivates **auto read** of all configured parameters of the active measurement group.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).

## Return Values

- **0**: OK
- **-1**: Device was not found

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
