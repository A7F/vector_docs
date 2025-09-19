[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryNumTimedoutRequests.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_NumTimedoutRequests

# ChkQuery_NumTimedoutRequests

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long ChkQuery_NumTimedoutRequests (dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
check.QueryNumTimedoutRequests();
```

## Check Name

[MOST Property Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTPropertyProtocolObservation.md) | [MOST Method Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTMethodProtocolObservation.md)

## Description

Returns the number of requests within the current observation period for which no corresponding response message was observed during the specified timeout.

In the context of a method protocol check, an occurred timeout of tWaitForProcessing1 or tWaitForProcessing2 will also count that request to the number returned by this function, regardless whether the final "Result"/"ResultAck" or "Error"/"ErrorAck" response is observed within tMaxDuration or not.

## Parameters

- **aCheckId**: Reference to check context.

## Return Values

- **< 0**: Refer the query [error codes](../CAPLfunctionsTSLErrorCodes.md).
- **≥ 0**: Number of requests that incurred a timeout.

## Example

—

[ChkCreate_MostPropertyProtocolError, ChkStart_MostPropertyProtocolError](CAPLfunctionChkCreateMostPropertyProtocolError.md) • [ChkCreate_MostMethodProtocolError, ChkStart_MostMethodProtocolError](CAPLfunctionChkCreateMostMethodProtocolError.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
