[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryEventTimeStampInt64.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_EventTimeStampInt64

# ChkQuery_EventTimeStampInt64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`Int64 ChkQuery_EventTimestampInt64 (dword CheckId);`

## Method Syntax

`check.QueryEventTimestampInt64();`

## Description

Retrieves time stamp of last fired event.

## Parameters

- **CheckId**: Identifier of the queried Check.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **> 0**: Event time stamp in units set for the queried Check with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md)

## Example

```plaintext
Int64 result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_EventTimeStampInt64(checkId);
```

[ChkQuery_EventTimeStamp](CAPLfunctionChkQueryEventTimeStamp.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
