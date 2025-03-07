[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryNumRequests.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_NumRequests

# ChkQuery_NumRequests

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long ChkQuery_NumRequests (dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
check.QueryNumRequests();
```

## Check Name

[MOST Property Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTPropertyProtocolObservation.md) | [MOST Method Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTMethodProtocolObservation.md)

## Description

Returns the total number of requests that occurred during the current observation period.

## Parameters

- **aCheckId**: Reference to check context.

## Return Values

- **< 0**: Refer the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Number of requests that occurred

## Example

—

[ChkCreate_MostPropertyProtocolError, ChkStart_MostPropertyProtocolError](CAPLfunctionChkCreateMostPropertyProtocolError.md) • [ChkCreate_MostMethodProtocolError, ChkStart_MostMethodProtocolError](CAPLfunctionChkCreateMostMethodProtocolError.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)