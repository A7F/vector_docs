[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForSysVar.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForSysVar

# TestWaitForSysVar

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestWaitForSysVar(sysvar aSysVar, dword aTimeout);
```

## Description

Waits for the next system variable **aSysVar**. Should the event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

## Parameters

- **aSysVar**: System variable that should be awaited. May also be a specific element of a variable of type struct or generic array.

  **Note**: Not available for a single element of a double or integer array.

- **aTimeout**: Maximum time that should be waited [ms]. (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation.
- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred.

## Example

```c
// waits for the occurrence of SysVar ‚MySysVar’
long result;
result = TestWaitForSysVar(sysvar::Test::MySysVar, 2000);
```

[TestJoinSysVarEvent](CAPLfunctionTestJoinSysVarEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)