[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryPrecision.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_Precision

# ChkQuery_Precision

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double ChkQuery_Precision (dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
check.QueryPrecision();
```

## Description

Returns a factor that can be multiplied with the return value of the statistical queries to convert the time stamp to the standard unit milliseconds.

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **double**: 100 to 10^-6

## Example

```plaintext
double result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_Precision(checkId);
```

[ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
