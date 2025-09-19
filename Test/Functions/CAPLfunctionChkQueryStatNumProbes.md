[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryStatNumProbes.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_StatNumProbes

# ChkQuery_StatNumProbes

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ChkQuery_StatNumProbes (dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryStatNumProbes();
```

## Description

Returns the number of samples (probes) that have been considered by the check. In general, this is the count of messages that have been analyzed by the check. In almost all signal/envvar/sysvar orientated checks, it is the number of changes in value of the specific signal or variable.

Deviating from the default following checks return the number of value updates:

- Fallback
- Value Dependency

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **0**: No event has occurred
- **> 0**: Number of probes

## Example

```plaintext
long result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_StatNumProbes(checkId);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
