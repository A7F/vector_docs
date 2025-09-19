[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryRequestFunctionId.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_RequestFunctionId

# ChkQuery_RequestFunctionId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long ChkQuery_RequestFunctionId(dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
check.QueryRequestFunctionId();
```

## Check Name

[MOST Property Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTPropertyProtocolObservation.md) | [MOST Method Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTMethodProtocolObservation.md)

## Description

Returns the function of the request message, which last led to a protocol violation.

## Parameters

- **aCheckId**: Reference to check context.

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Id of the function.

## Available For

- [ChkCreate_MostPropertyProtocolError](CAPLfunctionChkCreateErrorFramesOccured.md)

## Example

—

[ChkCreate_MostPropertyProtocolError, ChkStart_MostPropertyProtocolError](CAPLfunctionChkCreateMostPropertyProtocolError.md) • [ChkCreate_MostMethodProtocolError, ChkStart_MostMethodProtocolError](CAPLfunctionChkCreateMostMethodProtocolError.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
