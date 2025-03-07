[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryStatProbeIntervalMinAsyncResult.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_StatProbeIntervalMin_AsyncResult

# ChkQuery_StatProbeIntervalMin_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double ChkQuery_StatProbeIntervalMin_AsyncResult(dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
check.QueryStatProbeIntervalMinAsyncResult();
```

## Description

Returns the minimum timely distance between 2 consumed message events.

**Note**: Among other things with this function, the minimum occurred cycle time of a cyclic message can be queried.

The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
  - **Note**: There is a meaningful value available and a positive return value is supplied even if the check has not generated any event.
- **> 0**: Minimum timely distance

## Example

```plaintext
long result;
dword checkId;
double statProbe;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  statProbe = ChkQuery_StatProbeIntervalMin_AsyncResult(checkId);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)