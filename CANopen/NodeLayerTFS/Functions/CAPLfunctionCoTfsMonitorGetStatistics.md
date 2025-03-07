[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsMonitorGetStatistics.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsMonitorGetStatistics**

# coTfsMonitorGetStatistics (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsMonitorGetStatistics(dword nodeId, dword requestType, dword minValue[1], dword maxValue[1], dword averageValue[1], dword passedCounter[1], dword failedCounter[1]);
```

## Description

This function returns the statistics information that are monitored between [coTfsMonitorActivate](CAPLfunctionCoTfsMonitorActivate.md) and [coTfsMonitorDeactivate](CAPLfunctionCoTfsMonitorDeactivate.md).

## Parameters

- **nodeId**: Node-ID [1..127]
- **requestType**: Values to be monitored.
  - 1 - SDO time values
  - 2 - NMT time values
  - 3 - LSS time values
- **minValue[1]**: Minimum value in [ms].
- **maxValue[1]**: Maximum value in [ms].
- **averageValue[1]**: Average value in [ms].
- **passedCounter[1]**: Number of values within the allowed range.
- **failedCounter[1]**: Number of values out of the allowed range.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)