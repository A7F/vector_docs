# ChkQuery_StatAvResponseTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long ChkQuery_StatAvResponseTime (dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
check.QueryStatAvResponseTime();
```

## Check Name

[MOST Property Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTPropertyProtocolObservation.md) | [MOST Method Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTMethodProtocolObservation.md)

## Description

Returns the average time lag between the request and corresponding response messages. Only those requests that were resolved within the specified maximum response time are taken into consideration here.

## Parameters

- **aCheckId**: Reference to check context.

## Return Values

- **\< 0**: Refer the query [error codes](../CAPLfunctionsTSLErrorCodes.md).
- **≥ 0**: Average response time during the current time period.

## Example

—

[ChkCreate_MostPropertyProtocolError, ChkStart_MostPropertyProtocolError](CAPLfunctionChkCreateMostPropertyProtocolError.md) • [ChkCreate_MostMethodProtocolError, ChkStart_MostMethodProtocolError](CAPLfunctionChkCreateMostMethodProtocolError.md)
