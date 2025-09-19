[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForCheckQuery.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » testWaitForCheckQuery

# testWaitForCheckQuery

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long testWaitForCheckQuery(dword aCheckId, dword aTimeout);
```

## Description

Requests status information about a check with ID **aCheckId** which is evaluated asynchronously. Waits up to **aTimeout** ms.

## Parameters

- **aCheckId**: Handle of the check to be queried.
- **aTimeout**: Maximum time that should be waited [ms].  
  (Transmission of 0: no timeout controlling)

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **0**: Resume due to timeout. No valid data was received asynchronous evaluation.
- **1**: Data received.

## Example

```c
long result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  result = ChkQuery_NumEvents_AsyncResult(checkId);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
