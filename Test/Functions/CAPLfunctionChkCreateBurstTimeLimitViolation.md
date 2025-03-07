[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateBurstTimeLimitViolation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_BurstTimeLimitViolation, ChkStart_BurstTimeLimitViolation

# ChkCreate_BurstTimeLimitViolation, ChkStart_BurstTimeLimitViolation

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_BurstTimeLimitViolation (char[] aBusName, duration aMaxTime);`
- `dword ChkStart_BurstTimeLimitViolation (char[] aBusName, duration aMaxTime);`

## Constructor

- `TestCheck::CreateBurstTimeLimitViolation (char[] aBusName, duration aMaxTime);`
- `TestCheck::StartBurstTimeLimit (char[] aBusName, duration aMaxTime);`

## Check Name

[Burst Time Limit](../../../TestCommands/CheckDescriptions/CDBurstTimeLimit.md)

## Description

Checks the maximum burst time on a bus.

## Parameters

- **aBusName**: Name of the bus.
- **aMaxTime**: Maximum burst time. Default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Bus name is not available for the test module.
- Maximum burst time is 0.

## Example

```plaintext
// observes the maximum burst time 3 ms
checkId = ChkStart_BurstTimeLimitViolation ("CAN", 3);
TestAddCondition(checkId);

// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)