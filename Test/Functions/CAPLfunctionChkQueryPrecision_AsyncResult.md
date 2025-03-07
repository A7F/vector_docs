[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryPrecision_AsyncResult.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_Precision_AsyncResult

# ChkQuery_Precision_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double ChkQuery_Precision_AsyncResult(dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryPrecisionAsyncResult();
```

## Description

Returns a factor that can be multiplied with the return value of the statistical queries to convert the time stamp to the standard unit milliseconds.

The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **CheckId**: Identifier of the queried Check.

## Return Values

- **double**: 100 to 10^-6

## Example

```plaintext
long result;
dword checkId;
double precision;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  precision = ChkQuery_Precision_AsyncResult(checkId);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)