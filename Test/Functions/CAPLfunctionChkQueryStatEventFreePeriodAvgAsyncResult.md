[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryStatEventFreePeriodAvgAsyncResult.md)

**CAPL Functions** » **Test Service Library** » **Status Report Functions** » **ChkQuery_StatEventFreePeriodAvg_AsyncResult**

# ChkQuery_StatEventFreePeriodAvg_AsyncResult

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
double ChkQuery_StatEventFreePeriodAvg_AsyncResult(dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryStatEventFreePeriodAvgAsyncResult();
```

## Description

Returns the average timely distance between events and check starts/stops.

**Note**: Among other things with this function the average cycle time of a cyclic message can be queried.

The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)

  **Note**: There is a meaningful value available and a positive return value is supplied even if the check has not generated any event.

- **≥ 0**: Average timely distance in the current precision

## Example

```plaintext
long result;
dword checkId;
double period;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == vg1)
  period = ChkQuery_StatEventFreePeriodAvg_AsyncResult(checkId);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)